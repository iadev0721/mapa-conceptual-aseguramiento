# Tasks: Mapa Conceptual — Aseguramiento de la Calidad del Software

## Phase 1: Foundation — HTML Skeleton + Data Model

- [x] 1.1 Bootstrap `mapa-conceptual.html` — `<head>` (meta viewport, title), `<style>`, `<body>` containers (`#map-container`, `#connections` SVG, `#nodes`, `#tooltip`), `<script>` sections
- [x] 1.2 Define `data` object: `nodes[]` (70+ entries with id, label, level, branch, definition, example), `edges[]` (parent→child), `crossLinks[]` (15+ with from, to, label)

## Phase 2: Layout Algorithm

- [x] 2.1 Implement `computePositions(data)` — 5-column layout: root top-center, 4 branches as vertical columns, deterministic O(n)
- [x] 2.2 Define layout constants: columnWidth (22vw), levelHeight (100px), subNodeSpacing (8px), columnPadding
- [x] 2.3 Assign {x, y, width} to each node — level-based y-stacking, branch-indexed x, sub-node vertical packing

## Phase 3: Rendering — Nodes + SVG Connections

- [x] 3.1 Implement `renderNodes(data)` — HTML divs with inline position styles, branch background color, level-based font sizes, pill shape (border-radius 8px)
- [x] 3.2 Implement `renderConnections(data)` — SVG `<path>` hierarchy lines: cubic bezier bottom-center→top-center, solid stroke, branch color
- [x] 3.3 Implement `renderCrossLinks(data)` — SVG `<path>` cross-links: cubic bezier dashed stroke, gray, with `<text>` mid-point labels
- [x] 3.4 Add SVG `<marker>` arrow definitions for hierarchy path endpoints

## Phase 4: Interactions — Tooltips + Highlight Cascade

- [x] 4.1 Implement shared `#tooltip` div — `mouseenter` populates innerHTML with definition + example, viewport-aware repositioning, 200ms opacity fade
- [x] 4.2 Implement highlight cascade — on hover, highlight node + connected nodes + connecting edges; non-connected paths fade to opacity 0.15
- [x] 4.3 Add CSS transitions — `transform: scale(1.08)` on node hover (300ms ease), path opacity transitions, tooltip opacity

## Phase 5: Visual Polish + Responsive

- [x] 5.1 Apply color palette (blue #3B82F6, green #10B981, orange #F59E0B, purple #8B5CF6) and page background (#F8FAFC)
- [x] 5.2 Apply typography hierarchy (root 20px bold, level-1 14px bold, level-2 12px semi-bold, level-3+ 10px regular)
- [x] 5.3 Add node shadows (box-shadow), root node dark gradient, consistent border-radius
- [x] 5.4 Add `@media` query for tablet (768×1024) — adjust column widths, level height, font sizes, prevent horizontal scroll
- [x] 5.5 Add legend component showing 4 color-coded branches with labels
- [x] 5.6 Final visual polish: balanced column distribution, spacing consistency, smooth animations
