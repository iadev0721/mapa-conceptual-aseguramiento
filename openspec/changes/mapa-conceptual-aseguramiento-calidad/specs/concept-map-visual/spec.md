# Concept Map Visual — Specification

## Purpose
Interactive HTML concept map visualizing ~70-80 SQA concepts across 4 color-coded branches, 3-4 hierarchical levels, 20+ cross-links with labels, and hover tooltips showing definitions and examples. Self-contained academic deliverable for a university SQA course.

## Requirements

### Requirement: Concept Coverage

The concept map MUST display all 12 primary concepts with sub-concepts across minimum 3 hierarchy levels, totaling >= 70 nodes.

#### Scenario: All primary nodes visible
- GIVEN the page loads
- WHEN the render completes
- THEN all 12 primary concept nodes are visible in the top 2 levels
- AND the total visible node count is >= 70

#### Scenario: Hierarchy depth
- GIVEN the user inspects any primary branch
- WHEN counting levels from root to deepest leaf
- THEN minimum depth is 3 levels (root → branch → sub-concept)
- AND at least one branch reaches 4 levels

### Requirement: Cross-Links

The map MUST include 15+ documented cross-links with descriptive labels, visually distinct from hierarchy connections.

#### Scenario: Cross-link visibility
- GIVEN the map is fully rendered
- WHEN inspecting connection lines
- THEN cross-links use a dashed/dotted stroke
- AND each cross-link has a visible mid-point label
- AND total cross-link count is >= 15

### Requirement: Color-Coded Branches

The map SHALL use a 4-color palette (blue, green, orange, purple) to distinguish the four branches.

#### Scenario: Branch colors applied
- GIVEN all nodes are rendered
- WHEN observing any primary branch
- THEN its nodes and hierarchy links share a consistent hue
- AND all 4 colors are present and distinguishable against the background

### Requirement: Hover Tooltips

The map MUST show a tooltip with a definition and a concrete example when the user hovers a concept node.

#### Scenario: Tooltip appears and dismisses
- GIVEN the cursor is outside any node
- WHEN the user moves the cursor over a concept node
- THEN a tooltip appears within 300ms containing both definition and example
- AND the tooltip disappears when the cursor leaves the node

### Requirement: Typography Hierarchy

The map SHALL use 3+ distinct font sizes corresponding to hierarchy levels.

#### Scenario: Font size varies by level
- GIVEN the map is rendered
- WHEN comparing nodes at different levels
- THEN root nodes use the largest size, level-2 intermediate, level-3+ the smallest
- AND all text is legible at the smallest size

### Requirement: Responsive Layout

The map SHOULD render without loss of content on desktop (1920×1080) and tablet (768×1024).

#### Scenario: Tablet viewport
- GIVEN the viewport is 768×1024
- WHEN the page loads
- THEN all primary nodes are visible without horizontal scrolling
- AND tooltips render fully within the viewport

### Requirement: Hover Animations

The map MAY include smooth transitions (scale, opacity) on node hover for visual polish.

#### Scenario: Node hover animation
- GIVEN the user hovers a concept node
- WHEN the cursor enters the node area
- THEN the node scales 1.05-1.1x over 200-400ms
- AND connected links highlight with opacity change

### Requirement: Self-Contained File

The deliverable MUST be a single self-contained HTML file named `mapa-conceptual.html` with all CSS and JS embedded.

#### Scenario: Zero external dependencies
- GIVEN the file `mapa-conceptual.html`
- WHEN opened in Chrome 90+, Firefox 88+, or Safari 14+
- THEN all content, styles, and scripts load without network requests
- AND all interactive features work offline

### Requirement: Connection Rendering

The map MUST use SVG for drawing hierarchical and cross-link connections.

#### Scenario: SVG connections rendered
- GIVEN the map is fully rendered
- WHEN inspecting the DOM
- THEN hierarchy connections are solid SVG path elements
- AND cross-links are dashed SVG path elements with mid-point label elements
