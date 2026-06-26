# Design: Mapa Conceptual — Aseguramiento de la Calidad del Software

## Technical Approach

Single-file HTML artifact with SVG-over-HTML rendering. A JSON data model drives the entire map: positions are computed via a deterministic multi-column tree algorithm, connections drawn as SVG paths, and interactions handled through CSS transitions + JS event delegation. Zero external dependencies.

## Architecture Decisions

### Data Model — JSON source of truth

**Choice**: Flat arrays with id-references — `nodes[]`, `edges[]`, `crossLinks[]` — rendered by a single `render()` function.

| Option | Tradeoff | Decision |
|--------|----------|----------|
| Nested tree (parent contains children) | Hard to cross-reference for cross-links; awkward to traverse | ❌ Rejected |
| Flat arrays with ids | Cross-links resolved by id; render is O(n); easy to add/remove nodes | ✅ **Chosen** |

```js
const data = {
  nodes: [
    { id:"sqa", label:"Aseguramiento de la Calidad", level:0, branch:"root" },
    { id:"normas", label:"Normas y Estándares", level:1, branch:"blue",
      definition:"...", example:"ISO 9001, IEEE 730" }
  ],
  edges: [{ from:"sqa", to:"normas" }],
  crossLinks: [{ from:"normas", to:"verificacion", label:"establece criterios" }]
};
```

Every node with `level === 0` is a child of root `sqa`. Branches inherit color from the `branch` field on their level-1 node.

### Layout Algorithm — Deterministic multi-column tree

| Option | Tradeoff | Decision |
|--------|----------|----------|
| Force-directed (d3) | Non-deterministic; 70 nodes may overlap; external dep | ❌ Rejected |
| Manual absolute positions in data | Brittle, impossible to adjust | ❌ Rejected |
| Recursive column layout | Deterministic; responsive; no deps | ✅ **Chosen** |

**Algorithm**: 5 columns — root centered top, 4 branches below. Each branch is a column of nodes laid out top-to-bottom by level. Node y = `level * levelHeight + offset`. Within a level, sub-nodes are stacked vertically with `subNodeSpacing`. Column x = `branchIndex * columnWidth + padding`. The root spans all columns at the top.

Benefits: O(n) computation, predictable output, trivial to adjust spacing constants for responsive behavior.

### SVG Connection Strategy

| Option | Tradeoff | Decision |
|--------|----------|----------|
| Canvas | No DOM events per link; harder tooltips | ❌ Rejected |
| CSS borders/pseudo-elements | Cannot do curved paths or mid-point labels | ❌ Rejected |
| SVG `<path>` elements | Full control; events per path; accessible | ✅ **Chosen** |

- **Hierarchy**: Cubic bezier from source bottom-center to target top-center (`M x1,y1 C x1,cy x2,cy x2,y2`). Solid stroke, branch color.
- **Cross-links**: Same bezier formula but dashed stroke (`stroke-dasharray="6,4"`), neutral gray, with `<text>` mid-point label.
- **Arrows**: `<marker>` elements at end of hierarchy paths.

Node boundaries used as connection anchors. SVG layer sits absolutely behind the HTML node layer.

### Tooltip System

| Option | Tradeoff | Decision |
|--------|----------|----------|
| CSS `::after` pseudo-element | Cannot wrap complex HTML (definition + example) | ❌ Rejected |
| Fixed-position absolute div | Full HTML; viewport-aware repositioning | ✅ **Chosen** |

A single absolutely-positioned `<div id="tooltip">` shared across all nodes. On `mouseenter`, populate innerHTML with definition + example, compute position relative to viewport (prefer above-node, flip if near top edge), apply `200ms` opacity transition. On `mouseleave`, fade out. `z-index: 1000`.

### Interaction Model

- **Hover events**: Delegated on container via `mouseenter`/`mouseleave`.
- **Highlight cascade**: On hover, add class `highlight` to node + all connected nodes (edges + crossLinks both directions) + their connecting paths. All other paths fade to `opacity: 0.15`.
- **Node scale**: `transform: scale(1.08)` via CSS `transition: transform 300ms ease`.
- **Animation**: Pure CSS transitions for scale and opacity — no JS animation frames.

### Visual Architecture

| Element | Specification |
|---------|--------------|
| Root node font | 20px bold, white on dark gradient |
| Level 1 (branch) font | 14px bold, branch color |
| Level 2 font | 12px semi-bold |
| Level 3+ font | 10px regular |
| Node shape | Pill/rounded rectangle (`border-radius: 8px`) |
| Node padding | 10px 16px (levels 0-1), 6px 12px (levels 2+) |
| Column width | 22vw (4 columns), center column for root |
| Level height | 100px between levels |
| Sub-node spacing | 8px within same level |
| Branch colors | Blue `#3B82F6`, Green `#10B981`, Orange `#F59E0B`, Purple `#8B5CF6` |
| Page background | Off-white `#F8FAFC` |
| Shadows | `box-shadow` on nodes, subtle `drop-shadow` on paths |

### File Architecture

```
mapa-conceptual.html
├── <head>
│   ├── <meta viewport> (responsive)
│   ├── <title> (SEO/accessibility)
│   └── <style> (all CSS)
│       ├── Reset & base typography
│       ├── Layout: container, columns, node positions
│       ├── SVG: path styles, markers
│       ├── Tooltip: positioning, animations
│       └── Responsive: tablet @media query
├── <body>
│   ├── <div id="map-container">
│   │   ├── <svg id="connections"> (paths layer)
│   │   └── <div id="nodes"> (HTML node elements)
│   ├── <div id="tooltip">
│   └── <script> (all JS)
│       ├── Data: nodes, edges, crossLinks arrays
│       ├── Layout: computePositions(data)
│       ├── Render: build DOM nodes + SVG paths
│       └── Interactions: event delegation, highlight cascade
```

## Data Flow

```
computePositions(data) → node.{x, y, width}
        ↓
renderNodes(data) → build HTML elements with inline styles
        ↓
renderConnections(data) → build SVG <path> elements
        ↓
attachEvents(container) → mouseenter/mouseleave delegate
        ↓
onHover(nodeId) → highlight cascade (CSS class toggle)
```

## Testing Strategy

| Layer | What to Test | Approach |
|-------|-------------|----------|
| Visual | All 70+ nodes render, 4 colors present | Manual inspection per spec scenarios |
| Functional | Tooltip appears with definition+example on hover | Manual QA — hover each primary node |
| Responsive | No overflow at 768×1024 | Browser devtools viewport emulation |
| Offline | Zero network requests | DevTools network tab on fresh load |

## Migration / Rollout

No migration required. Single file deliverable. Use `git checkout` for version recovery.

## Open Questions

None — all decisions scoped and resolved per specs.
