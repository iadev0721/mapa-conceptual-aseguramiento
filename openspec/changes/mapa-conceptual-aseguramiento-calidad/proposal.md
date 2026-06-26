# Proposal: Mapa Conceptual — Aseguramiento de la Calidad del Software

## Intent
Crear un mapa conceptual visualmente atractivo que sintetice los conceptos clave de Aseguramiento de la Calidad del Software (SQA), demostrando profundidad conceptual, organización jerárquica y conexiones cruzadas entre temas. Entregable académico para el curso de Aseguramiento de la Calidad, Equipo 2.

## Scope
### In Scope
- ~70-80 conceptos organizados en 3-4 niveles jerárquicos (12 principales + subconceptos)
- 20+ cross-links entre ramas con etiquetas descriptivas
- Ejemplos concretos por cada concepto principal
- Implementación HTML/CSS/JS auto-contenido e interactivo
- Paleta de 4 colores por rama (azul, verde, naranja, púrpura)
- Efectos hover/click para definiciones y ejemplos

### Out of Scope
- Explicación audio/video (entregable separado de la asignación)
- Código fuente detallado del proyecto (enfoque puramente conceptual)
- Versión física impresa

## Capabilities
### New Capabilities
- `concept-map-visual`: Mapa conceptual HTML interactivo del dominio SQA con layout jerárquico top-down, cross-links, ramas codificadas por color e interacciones hover/click para mostrar definiciones y ejemplos

### Modified Capabilities
None — artifact completamente nuevo, no modifica capacidades existentes.

## Approach
Generar un archivo HTML auto-contenido con CSS y JavaScript embebidos. Layout jerárquico top-down (3-4 niveles) con SVG para dibujar conexiones jerárquicas y cross-links punteados. 4 ramas principales distinguidas por color con degradados. Tooltips emergentes con definiciones y ejemplos al hacer hover. Diseño responsive. En la fase apply se usará el skill frontend-design para pulido visual profesional.

## Affected Areas
| Area | Impact | Description |
|------|--------|-------------|
| `openspec/changes/mapa-conceptual-aseguramiento-calidad/` | New | Carpeta del cambio con todos los artifacts |
| `mapa-conceptual.html` | New | Entregable final — mapa conceptual visual interactivo |

## Risks
| Risk | Likelihood | Mitigation |
|------|------------|------------|
| Densidad visual excesiva | Medium | Limitar a 3 niveles visibles, usar tooltips expandibles |
| Cross-links insuficientes para evaluación | Medium | Documentar 20+ de antemano, verificar en apply |
| Responsive en mobile | Low | CSS responsive y viewport meta desde el inicio |

## Rollback Plan
El mapa es un HTML auto-contenido — versiones previas se recuperan con `git checkout`. Sin operaciones destructivas ni dependencias externas.

## Dependencies
Ninguna externa. Todos los conceptos pertenecen al cuerpo de conocimiento estándar de SQA (ISO, IEEE, CMMI).

## Success Criteria
- [ ] Los 12 conceptos requeridos están presentes con definiciones claras
- [ ] Mínimo 3 niveles jerárquicos visibles en el mapa
- [ ] 15+ cross-links documentados y visualmente identificables
- [ ] Ejemplos concretos por cada rama principal
- [ ] Visualmente atractivo (paleta coherente, tipografía legible, layout balanceado)
