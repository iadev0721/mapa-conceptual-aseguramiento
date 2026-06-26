# Exploration: Mapa Conceptual — Aseguramiento de la Calidad del Software

**Change**: mapa-conceptual-aseguramiento-calidad
**Equipo**: 2 — Ignacio Aliendres, Fernando Pérez, Víctor Serrano, Andrés Lara, Cristian Baczek
**Deadline**: 28 de junio de 2026
**Modelo**: sonnet (structural writing)

---

## 1. Contexto y Objetivo

Elaborar un **mapa conceptual** que presente una sinopsis del tema **"Aseguramiento de la Calidad del Software"**, cubriendo 12 conceptos principales con sus relaciones jerárquicas y conexiones cruzadas. El mapa debe ser visualmente atractivo, pedagógico y demostrar profundidad conceptual.

### Criterios de Evaluación

| Criterio | Peso | Implicación |
|----------|------|-------------|
| Exposición de conceptos importantes | Alto | Cada concepto debe tener definición clara + ejemplos |
| Cantidad mínima de términos | Alto | No solo los 12 principales, sino subconceptos |
| Conexiones y jerarquía + uniones cruzadas | Alto | Múltiples niveles jerárquicos + cross-links entre ramas |
| Claridad y profundidad (uso de ejemplos) | Medio-Alto | Conceptos abstractos requieren ejemplos concretos |
| Trabajo en equipo | Medio | Distribución de la carga entre 5 miembros |

---

## 2. Análisis del Dominio: Mapa de Conceptos

### 2.1. Jerarquía Conceptual Natural

```
NIVEL 0 (Superconcepto)
  └── CALIDAD DEL SOFTWARE (SQA)
        │
        ├── NIVEL 1 — FUNDAMENTOS CONCEPTUALES
        │     ├── Calidad (definiciones: Crosby, Deming, Juran, ISO 9000)
        │     ├── Aseguramiento de la Calidad (QA — preventivo, procesos)
        │     ├── Control de Calidad (QC — reactivo, producto)
        │     └── Cultura de Calidad (valores organizacionales, mejora continua)
        │
        ├── NIVEL 1 — DIMENSIONES DE CALIDAD
        │     ├── Calidad de Producto (McCall, ISO 25010, atributos)
        │     └── Calidad del Proceso (CMMI, ISO 12207, madurez)
        │
        ├── NIVEL 1 — ACTIVIDADES DE VERIFICACIÓN
        │     ├── Verificación y Validación (V&V)
        │     ├── Inspecciones y Auditorías
        │     └── Listas de Chequeo
        │
        ├── NIVEL 1 — GESTIÓN DE DEFECTOS
        │     └── Errores, Defectos y Fallas (taxonomía, ciclo de vida)
        │
        └── NIVEL 1 — MEDICIÓN
              └── Medición y Métricas (productividad, calidad, proceso)
```

### 2.2. Definiciones y Profundidad por Concepto

#### Concepto 1: Calidad (Quality)

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Grado en que un conjunto de características inherentes cumple con los requisitos (ISO 9000). No es absoluta — depende del punto de vista del stakeholder. |
| **Visiones** | **Trascendental** (excelencia innata), **Basada en producto** (cantidad de atributos), **Basada en usuario** (fitness for use — Juran), **Basada en valor** (calidad vs. costo), **Basada en proceso** (cero defectos — Crosby) |
| **Subconceptos** | Satisfacción del cliente, conformidad con requisitos, aptitud para el uso, valor por precio |
| **Ejemplo** | Un software puede tener alta calidad técnica (código limpio, tests) pero ser percibido como de baja calidad si la UI es confusa para el usuario final. |

#### Concepto 2: Aseguramiento de la Calidad (QA)

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Conjunto de actividades planificadas y sistemáticas implementadas en el Sistema de Calidad para asegurar que los requisitos de calidad se cumplen (ISO 9000). **Enfoque preventivo**. |
| **Subconceptos** | Plan de Aseguramiento de Calidad (SQAP), auditorías de proceso, definición de estándares, mejora continua (PDCA / Deming Cycle), madurez del proceso |
| **Ejemplo** | Definir una política de code reviews obligatorios antes de mergear a main — esto previene defectos antes de que lleguen a producción. |

#### Concepto 3: Control de Calidad (QC)

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Técnicas y actividades operacionales enfocadas en cumplir los requisitos de calidad (ISO 9000). **Enfoque reactivo/detectivo**. |
| **Subconceptos** | Pruebas (testing), inspección de productos, verificación de entregables, gestión de no conformidades |
| **Relación QA vs QC** | QA construye el sistema que previene defectos; QC detecta defectos en el producto terminado. QA es proactivo, QC es reactivo. Ambos son complementarios. |
| **Ejemplo** | Ejecutar pruebas de regresión automatizadas antes de un release para detectar bugs introducidos por cambios recientes. |

#### Concepto 4: Cultura de Calidad

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Conjunto de valores, creencias y comportamientos compartidos que priorizan la calidad en toda la organización. No se impone por decreto — se cultiva. |
| **Subconceptos** | Compromiso de la dirección, empowerment del equipo, comunicación abierta, aprendizaje organizacional, mentalidad de mejora continua (Kaizen) |
| **Ejemplo** | Una empresa donde cualquier desarrollador puede detener un release si encuentra un bug crítico, sin temor a represalias, tiene una cultura de calidad madura. |

#### Concepto 5: Calidad de Producto

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Conjunto de atributos internos y externos que determinan el valor del producto de software. |
| **Modelos** | **McCall** (1977): factores de revisión, transición, operación. **ISO/IEC 25010** (SQuaRE): 8 características principales (funcionalidad, confiabilidad, usabilidad, eficiencia, mantenibilidad, portabilidad, compatibilidad, seguridad) |
| **Subconceptos** | Corrección, confiabilidad (reliability), usabilidad (usability), eficiencia (performance), mantenibilidad, portabilidad, seguridad (security) |
| **Ejemplo** | Una app bancaria debe tener alta seguridad (autenticación, cifrado) y alta confiabilidad (disponibilidad 99.9%), aunque la usabilidad pueda sacrificarse ligeramente por seguridad. |

#### Concepto 6: Calidad del Proceso de Desarrollo

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Grado en que el proceso de desarrollo de software está definido, documentado, medido y mejorado continuamente. Premisa: proceso de calidad → producto de calidad. |
| **Modelos** | **CMMI** (Capability Maturity Model Integration): niveles 1-5 (Inicial → Gestionado → Definido → Cuantitativamente Gestionado → Optimizado). **ISO 12207**: estándar de procesos de ciclo de vida del software. |
| **Subconceptos** | Madurez del proceso, capacidad del proceso, definición de procesos, medición de procesos, mejora de procesos (SPI) |
| **Ejemplo** | Una empresa en CMMI Nivel 3 (Definido) tiene procesos estandarizados en toda la organización. Una en Nivel 5 (Optimizado) usa datos para mejorar continuamente sus procesos. |

#### Concepto 7: Verificación y Validación (V&V)

| Aspecto | Detalle |
|---------|---------|
| **Definición** | **Verificación**: ¿Estamos construyendo el producto correctamente? (cumple especificaciones). **Validación**: ¿Estamos construyendo el producto correcto? (satisface necesidades del cliente). |
| **Diferencia clave** | Verificación = revisión de artefactos internos (docs, código). Validación = prueba con el usuario/cliente real. |
| **Subconceptos** | Revisiones técnicas, walkthroughs, inspections, testing unitario, testing de integración, testing de sistema, testing de aceptación (UAT), prototipado |
| **Ejemplo** | Una revisión de código (code review) es verificación. Una sesión de prueba con usuarios reales usando la aplicación es validación. Ambos son necesarios. |

#### Concepto 8: Estándares

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Documentos normativos que establecen requisitos, especificaciones, directrices o características para asegurar que los materiales, productos, procesos y servicios sean adecuados para su propósito. |
| **Categorías** | **Internacionales** (ISO, IEEE), **Nacionales** (ANSI, INNOR), **Organizacionales** (estándares internos de la empresa), **De proyecto** (guías de estilo, templates) |
| **Subconceptos** | ISO 9001 (Sistemas de Gestión de Calidad), ISO/IEC 25010 (Calidad de Producto), ISO/IEC 12207 (Procesos), IEEE 829 (Documentación de pruebas), ISO/IEC 27001 (Seguridad) |
| **Ejemplo** | Adoptar ISO 9001 implica documentar procesos, realizar auditorías internas y revisar la satisfacción del cliente periódicamente. |

#### Concepto 9: Errores, Defectos y Fallas

| Aspecto | Detalle |
|---------|---------|
| **Definición** | **Error**: acción humana incorrecta (programador comete un mistake). **Defecto (bug)**: manifestación del error en el código/artefacto. **Falla (failure)**: comportamiento incorrecto observable cuando se ejecuta el defecto. |
| **Taxonomía** | Error (causa) → Defecto (estado) → Falla (efecto observable). También: **incidente** (desviación detectada), **problema** (causa raíz de múltiples incidentes) |
| **Subconceptos** | Severidad vs. Prioridad, defect leakage, densidad de defectos, root cause analysis, prevención de defectos |
| **Ejemplo** | Un programador escribe `if (x = 5)` en vez de `if (x == 5)` — eso es un **error**. El código incorrecto es un **defecto**. Cuando el usuario ejecuta el programa y asigna 5 a x sin querer, eso es una **falla**. |

#### Concepto 10: Inspecciones y Auditorías

| Aspecto | Detalle |
|---------|---------|
| **Definición** | **Inspección**: examen formal de un artefacto para detectar defectos (Fagan Inspection, 1976). **Auditoría**: evaluación independiente de conformidad con estándares, planes o procedimientos. |
| **Tipos de Inspección** | Formal (Fagan: planning, overview, preparation, meeting, rework, follow-up), Técnica (peer review), Walkthrough (autor presenta), Pair review |
| **Tipos de Auditoría** | Interna (first-party), Externa (third-party), De proceso, De producto, De sistema de calidad |
| **Subconceptos** | Checklist de inspección, roles (moderador, autor, inspector, revisor), no conformidades, acciones correctivas |
| **Ejemplo** | Una auditoría interna ISO 9001 revisa si los procesos documentados se siguen en la práctica. Una inspección Fagan de un documento de requisitos busca defectos antes de pasar a diseño. |

#### Concepto 11: Listas de Chequeo (Checklists)

| Aspecto | Detalle |
|---------|---------|
| **Definición** | Lista estructurada de ítems que se deben verificar para asegurar consistencia, completitud y cumplimiento de estándares en una actividad o artefacto. |
| **Tipos** | De proceso (pasos a seguir), De producto (atributos a verificar), De verificación (criterios de aceptación), De auditoría (evidencias requeridas) |
| **Subconceptos** | Checklist-based testing, verificación de requisitos, criterios de entrada/salida, Definition of Done (DoD) |
| **Ejemplo** | Una checklist de deploy puede incluir: "¿Se ejecutaron las migraciones?", "¿Se actualizó la documentación?", "¿Pasaron todas las pruebas de regresión?", "¿Se notificó al equipo?". |

#### Concepto 12: Medición y Métricas

| Aspecto | Detalle |
|---------|---------|
| **Definición** | **Medición**: proceso de asignar números a atributos de entidades del mundo real. **Métrica**: función de medición cuantificable. **Indicador**: métrica interpretada en contexto para la toma de decisiones. |
| **Clasificación** | **Métricas de producto**: tamaño (SLOC, puntos de función), complejidad (McCabe), acoplamiento, cohesión, cobertura de pruebas. **Métricas de proceso**: esfuerzo, tiempo de ciclo, defect leakage, productividad. **Métricas de proyecto**: avance (EVA), variación de schedule, variación de presupuesto. |
| **Subconceptos** | Línea base, objetivos medibles (SMART), análisis de tendencias, cuadro de mando (dashboard), Goal-Question-Metric (GQM) |
| **Ejemplo** | GQM: Goal (mejorar confiabilidad) → Question (¿cuántos defectos críticos llegan a producción?) → Metric (defect leakage rate = defectos en producción / defectos totales). |

---

## 3. Comparación de Enfoques para el Mapa Conceptual

### Enfoque A: Jerárquico Top-Down (Tradicional)

**Estructura**: Un concepto superordinado en la parte superior (Calidad del Software), con niveles descendentes de general a específico.

```
┌─────────────────────────────┐
│   CALIDAD DEL SOFTWARE      │
│   (SQA)                     │
└─────────────┬───────────────┘
              │
    ┌─────────┼─────────┬──────────┐
    │         │         │          │
  FUNDAM.  DIMENS.   ACTIV.    MEDICIÓN
```

| Aspecto | Evaluación |
|---------|------------|
| **Ventajas** | + Estructura familiar y fácil de leer; + Clara jerarquía de abstracción; + Fácil de explicar en clase; + Bien aceptado en ámbitos académicos |
| **Desventajas** | - Dificulta mostrar conexiones cruzadas entre ramas; - Puede resultar rígido y "cuadrado"; - No captura bien la naturaleza interconectada de SQA; - El nivel inferior puede quedar muy cargado |
| **Visual** | Diagrama de árbol con rectángulos y líneas |
| **Recomendación** | Bueno para la estructura BASE, pero necesita cross-links para ser completo |

### Enfoque B: Radial / Centrado en SQA

**Estructura**: "Aseguramiento de la Calidad del Software" en el centro, conceptos principales irradiando hacia afuera, subconceptos en anillos concéntricos.

```
           ┌───────────┐
           │   QC      │
           │           │
┌──────────┼───────────┼──────────┐
│  Proceso │  SQA      │ Producto │
│          │  (centro) │          │
└──────────┼───────────┼──────────┘
           │ Cultura   │
           │           │
           └───────────┘
```

| Aspecto | Evaluación |
|---------|------------|
| **Ventajas** | + Visualmente impactante y moderno; + SQA como centro conceptual es correcto; + Facilita conexiones radiales (cross-links); + Bueno para mostrar relaciones simétricas |
| **Desventajas** | - Puede ser confuso con muchos niveles (más de 3 anillos); - El ojo humano no lee en círculos naturalmente; - Dificultad para mostrar jerarquías de subordinación claras; - Requiere más diseño visual cuidado |
| **Visual** | Diagrama de burbujas/radial con líneas curvas |
| **Recomendación** | Excelente como COMPLEMENTO al mapa base o como diagrama de relaciones, pero no como estructura principal |

### Enfoque C: Proceso / Flujo de Ciclo de Vida

**Estructura**: Sigue el flujo del ciclo de vida del software (Requisitos → Diseño → Desarrollo → Pruebas → Operación), ubicando cada concepto en la etapa donde es más relevante.

```
Requisitos ──→ Diseño ──→ Desarrollo ──→ Pruebas ──→ Operación
    │             │            │             │            │
  Estándares    V&V        QA/QC        Defectos     Métricas
```

| Aspecto | Evaluación |
|---------|------------|
| **Ventajas** | + Muestra aplicabilidad temporal de cada concepto; + Contextualiza SQA en el ciclo de vida real; + Bueno para mostrar因果关系 (causa-efecto); + Relaciona teoría con práctica |
| **Desventajas** | - Varios conceptos (Cultura de Calidad, Estándares) son transversales y no encajan en una sola etapa; - Obliga a linealizar conceptos que no son lineales; - Puede confundir al sugerir que SQA solo aplica en ciertas fases |
| **Visual** | Diagrama de flujo horizontal con carriles |
| **Recomendación** | Bueno para un ANEXO o diagrama complementario, no como estructura principal |

### Recomendación: Enfoque HÍBRIDO

**Estructura propuesta**: Jerarquía Top-Down + Red de Conexiones Cruzadas

| Elemento | Propuesta |
|----------|-----------|
| **Estructura base** | Jerárquica top-down (3-4 niveles) — la más clara y académica |
| **Conexiones** | Cross-links entre nodos de diferentes ramas (con etiquetas descriptivas) |
| **Núcleo visual** | "Calidad del Software" como raíz superior, con 5 ramas principales |
| **Diagrama complementario** | Un diagrama radial pequeño en una esquina mostrando las relaciones entre QA, QC y V&V |
| **Estilo** | Colores por rama, iconos pequeños, líneas curvas para cross-links |
| **Herramientas sugeridas** | **XMind**, **Lucidchart**, **Canva** (mapas conceptuales), o **Draw.io**; o incluso **Mermaid.js** para versión en código |

#### Justificación

1. **Claridad académica**: La jerarquía top-down es la más reconocible para evaluadores universitarios.
2. **Profundidad evaluable**: Los niveles jerárquicos demuestran dominio del tema.
3. **Conexiones cruzadas**: Abordan el criterio de "uniones cruzadas" directamente.
4. **Flexibilidad visual**: Se puede implementar en múltiples herramientas.

---

## 4. Inventario Completo de Conceptos y Subconceptos

### 4.1. Árbol Jerárquico Completo

```
NIVEL 0: CALIDAD DEL SOFTWARE (SQA)

├── NIVEL 1: FUNDAMENTOS DE CALIDAD
│   ├── NIVEL 2: Calidad
│   │   ├── NIVEL 3: Definiciones (Crosby, Deming, Juran, ISO)
│   │   ├── NIVEL 3: Dimensiones (Garvin)
│   │   │   ├── Trascendental
│   │   │   ├── Basada en producto
│   │   │   ├── Basada en usuario
│   │   │   ├── Basada en valor
│   │   │   └── Basada en proceso
│   │   └── NIVEL 3: Principios (mejora continua, enfoque al cliente)
│   │
│   ├── NIVEL 2: Aseguramiento de Calidad (QA)
│   │   ├── NIVEL 3: Enfoque preventivo
│   │   ├── NIVEL 3: Plan de Calidad (SQAP)
│   │   ├── NIVEL 3: Auditorías de proceso
│   │   ├── NIVEL 3: Definición de estándares
│   │   └── NIVEL 3: Ciclo PDCA (Plan-Do-Check-Act)
│   │
│   ├── NIVEL 2: Control de Calidad (QC)
│   │   ├── NIVEL 3: Enfoque reactivo/detectivo
│   │   ├── NIVEL 3: Pruebas (testing)
│   │   ├── NIVEL 3: Inspección de productos
│   │   ├── NIVEL 3: Gestión de no conformidades
│   │   └── NIVEL 3: Verificación de entregables
│   │
│   └── NIVEL 2: Cultura de Calidad
│       ├── NIVEL 3: Compromiso de la dirección
│       ├── NIVEL 3: Empowerment del equipo
│       ├── NIVEL 3: Comunicación abierta
│       ├── NIVEL 3: Kaizen (mejora continua)
│       └── NIVEL 3: Aprendizaje organizacional

├── NIVEL 1: DIMENSIONES DE CALIDAD
│   ├── NIVEL 2: Calidad de Producto
│   │   ├── NIVEL 3: Modelo McCall (factores)
│   │   ├── NIVEL 3: ISO/IEC 25010 (SQuaRE)
│   │   │   ├── Funcionalidad
│   │   │   ├── Confiabilidad
│   │   │   ├── Usabilidad
│   │   │   ├── Eficiencia
│   │   │   ├── Mantenibilidad
│   │   │   ├── Portabilidad
│   │   │   ├── Compatibilidad
│   │   │   └── Seguridad
│   │   └── NIVEL 3: Atributos de calidad internos vs externos
│   │
│   └── NIVEL 2: Calidad del Proceso
│       ├── NIVEL 3: CMMI (niveles 1-5)
│       ├── NIVEL 3: ISO/IEC 12207
│       ├── NIVEL 3: Madurez vs Capacidad
│       ├── NIVEL 3: Definición de procesos
│       └── NIVEL 3: SPI (Software Process Improvement)

├── NIVEL 1: ACTIVIDADES DE VERIFICACIÓN
│   ├── NIVEL 2: Verificación y Validación
│   │   ├── NIVEL 3: Verificación (¿build correct?)
│   │   │   ├── Revisiones técnicas
│   │   │   ├── Walkthroughs
│   │   │   └── Testing de componentes
│   │   └── NIVEL 3: Validación (¿build correcto?)
│   │       ├── Pruebas de aceptación (UAT)
│   │       ├── Prototipado
│   │       └── Pruebas con usuario
│   │
│   ├── NIVEL 2: Inspecciones y Auditorías
│   │   ├── NIVEL 3: Inspección Fagan (formal)
│   │   ├── NIVEL 3: Peer Review (técnica)
│   │   ├── NIVEL 3: Auditoría interna (1ra parte)
│   │   ├── NIVEL 3: Auditoría externa (3ra parte)
│   │   └── NIVEL 3: No conformidades y AC
│   │
│   └── NIVEL 2: Listas de Chequeo
│       ├── NIVEL 3: Checklist de proceso
│       ├── NIVEL 3: Checklist de producto
│       ├── NIVEL 3: Checklist de verificación
│       ├── NIVEL 3: Definition of Done (DoD)
│       └── NIVEL 3: Criterios de entrada/salida

├── NIVEL 1: GESTIÓN DE DEFECTOS
│   └── NIVEL 2: Errores, Defectos y Fallas
│       ├── NIVEL 3: Error (causa humana)
│       ├── NIVEL 3: Defecto / Bug (manifestación)
│       ├── NIVEL 3: Falla / Failure (efecto observable)
│       ├── NIVEL 3: Severidad vs Prioridad
│       ├── NIVEL 3: Defect Leakage
│       ├── NIVEL 3: Densidad de defectos
│       └── NIVEL 3: Root Cause Analysis (RCA)

└── NIVEL 1: MEDICIÓN Y EVALUACIÓN
    └── NIVEL 2: Medición y Métricas
        ├── NIVEL 3: Métricas de Producto
        │   ├── SLOC, Puntos de Función
        │   ├── Complejidad Ciclomática (McCabe)
        │   ├── Acoplamiento y Cohesión
        │   └── Cobertura de pruebas
        ├── NIVEL 3: Métricas de Proceso
        │   ├── Esfuerzo y tiempo de ciclo
        │   ├── Defect Leakage Rate
        │   └── Productividad
        ├── NIVEL 3: Métricas de Proyecto
        │   ├── EVA (Earned Value Analysis)
        │   ├── Variación de schedule
        │   └── CPI / SPI
        ├── NIVEL 3: GQM (Goal-Question-Metric)
        └── NIVEL 3: Línea base y tendencias

Total de nodos: ~70-80 conceptos (12 principales + ~60-68 subconceptos)
```

### 4.2. Conexiones Cruzadas (Cross-Links)

| # | Nodo A | Nodo B | Relación | Etiqueta del enlace |
|---|--------|--------|----------|---------------------|
| CL1 | QA (preventivo) | QC (detectivo) | Complementariedad | "QA previene, QC detecta" |
| CL2 | QA | Estándares | Soporte | "QA define estándares" |
| CL3 | QC | Defectos | Detección | "QC identifica defectos" |
| CL4 | V&V | QC | Inclusión | "QC incluye V&V" |
| CL5 | V&V | Defectos | Descubrimiento | "V&V revela defectos" |
| CL6 | Métricas | QC | Evaluación | "Métricas miden efectividad de QC" |
| CL7 | Métricas | Calidad de Producto | Medición | "Métricas cuantifican atributos" |
| CL8 | Métricas | Calidad del Proceso | Medición | "Métricas evalúan madurez" |
| CL9 | Cultura de Calidad | Mejora Continua | Habilitador | "Cultura impulsa mejora" |
| CL10 | Estándares | Auditorías | Conformidad | "Auditorías verifican cumplimiento" |
| CL11 | Estándares | Calidad del Proceso | Marco | "Estándares definen procesos" |
| CL12 | Inspecciones | Listas de Chequeo | Herramienta | "Checklists guían inspecciones" |
| CL13 | Listas de Chequeo | V&V | Soporte | "Checklists apoyan verificación" |
| CL14 | Defectos | Métricas | Cuantificación | "Métricas miden defectos" |
| CL15 | Cultura de Calidad | QA | Fundamento | "Cultura sostiene QA" |
| CL16 | Calidad de Producto | V&V | Evaluación | "V&V evalúa producto" |
| CL17 | CMMI | Auditorías | Evaluación | "Auditorías determinan nivel CMMI" |
| CL18 | PDCA | Cultura de Calidad | Ciclo | "PDCA institucionaliza mejora" |
| CL19 | ISO 25010 | Métricas | Atributos | "Métricas miden atributos ISO" |
| CL20 | Error → Defecto → Falla | QC | Cadena | "QC interrumpe la cadena" |

---

## 5. Estructura Visual Recomendada

### 5.1. Layout Propuesto

```
                          ┌──────────────────────┐
                          │  CALIDAD DEL SOFTWARE │
                          │    (SQA)              │
                          └──────┬───────────────┘
              ┌───────────────────┼───────────────────┬────────────────────┐
              │                   │                   │                    │
     ┌────────▼────────┐ ┌───────▼────────┐ ┌────────▼───────┐  ┌─────────▼─────────┐
     │  FUNDAMENTOS    │ │  DIMENSIONES   │ │  ACTIVIDADES   │  │   MEDICIÓN Y      │
     │  DE CALIDAD     │ │  DE CALIDAD    │ │  DE V&V        │  │   DEFECTOS        │
     └────────┬────────┘ └───────┬────────┘ └────────┬───────┘  └─────────┬─────────┘
              │                  │                    │                   │
     ┌────────┼────────┐  ┌──────┴──────┐   ┌────────┼────────┐  ┌──────┴──────┐
     │        │        │  │             │   │        │        │  │             │
  ┌──▼───┐ ┌──▼───┐ ┌──▼──┐ ┌───────┐ ┌──▼──┐ ┌───▼────┐ ┌──▼──┐ ┌──────▼─────┐
  │Calid.│ │ QA   │ │ QC  │ │Prod.  │ │Proc.│ │V&V     │ │Insp.│ │Err/Def/Fall│
  │      │ │      │ │     │ │       │ │     │ │        │ │/Aud.│ │            │
  └──┬───┘ └──┬───┘ └──┬──┘ └───┬───┘ └──┬──┘ └───┬────┘ └──┬──┘ └──────┬─────┘
     │        │        │        │        │        │        │           │
  ┌──┴──┐  ┌──┴──┐  ┌──┴──┐  ┌──┴──┐  ┌──┴──┐  ┌──┴──┐  ┌──┴──┐   ┌──┴──┐
  │Sub  │  │Sub  │  │Sub  │  │Sub  │  │Sub  │  │Sub  │  │Sub  │   │Sub  │
  │conc.│  │conc.│  │conc.│  │conc.│  │conc.│  │conc.│  │conc.│   │conc.│
  └─────┘  └─────┘  └─────┘  └─────┘  └─────┘  └─────┘  └─────┘   └─────┘
```

### 5.2. Paleta de Colores Sugerida

| Rama | Color | Hex | Significado |
|------|-------|-----|-------------|
| Fundamentos | Azul profundo | #1a56db | Confianza, base |
| Dimensiones | Verde bosque | #059669 | Crecimiento, producto |
| Actividades V&V | Naranja | #ea580c | Acción, revisión |
| Medición/Defectos | Púrpura | #7c3aed | Análisis, datos |
| Cross-links | Gris / líneas punteadas | — | Conexiones secundarias |

### 5.3. Formato Visual

1. **Nivel 0**: Caja central grande, negrita, borde grueso, color distintivo
2. **Nivel 1**: Cajas medianas, color de rama, alineadas horizontalmente
3. **Nivel 2**: Cajas pequeñas, color más claro, debajo de cada N1
4. **Nivel 3+**: Texto sin caja o con bullet points (opcional, según espacio)
5. **Cross-links**: Líneas punteadas con etiqueta de texto, color gris/neutro
6. **Iconos**: Opcionales, pequeños (✅ para verificación, 🔍 para inspección, 📊 para métricas)

### 5.4. Herramientas Recomendadas

| Herramienta | Tipo | Ideal para | Licencia |
|-------------|------|------------|----------|
| **XMind** | Desktop + Web | Mapas conceptuales profesionales | Freemium |
| **Lucidchart** | Web | Diagramas colaborativos | Freemium (educación) |
| **Canva** | Web | Mapas visualmente atractivos | Freemium |
| **Draw.io / diagrams.net** | Web + Desktop | Gratuito, versátil | Gratuito |
| **Miro** | Web | Pizarrón colaborativo | Freemium (educación) |
| **CmapTools** | Desktop | Mapas conceptuales académicos | Gratuito |
| **Mermaid.js** | Código | Versión en markdown (git-friendly) | Gratuito |

---

## 6. Estrategia de Trabajo en Equipo (5 miembros)

### Distribución Sugerida

| Miembro | Responsabilidad Principal | Conceptos |
|---------|--------------------------|-----------|
| **Ignacio** | Coordinación + Núcleo | Calidad, SQA, jerarquía general, revisión final |
| **Fernando** | Rama Fundamentos | QA, QC, Cultura de Calidad, Estándares |
| **Víctor** | Rama Dimensiones | Calidad de Producto (ISO 25010), Calidad de Proceso (CMMI) |
| **Andrés** | Rama Actividades | V&V, Inspecciones y Auditorías, Listas de Chequeo |
| **Cristian** | Rama Defectos + Métricas | Errores/Defectos/Fallas, Medición y Métricas, cross-links |

### Flujo de Trabajo

1. **Investigación individual** (cada miembro profundiza sus 2-3 conceptos)
2. **Sesión de alineación** (definir estructura global, conexiones, ejemplos)
3. **Draft del mapa** (herramienta colaborativa — Lucidchart o Miro)
4. **Cross-links** (revisión de conexiones entre ramas de diferentes miembros)
5. **Revisión y pulido** (claridad, ejemplos, estética, ortografía)
6. **Entrega** (exportar a PDF/imagen + explicación escrita/grabada)

---

## 7. Riesgos y Mitigaciones

| Riesgo | Impacto | Probabilidad | Mitigación |
|--------|---------|--------------|------------|
| Mapa demasiado denso ( > 100 nodos) | Confusión visual | Alta | Limitar a 3 niveles visibles, usar colapsables si digital |
| Cross-links insuficientes | Penalización en evaluación | Media | Revisión explícita de conexiones cruzadas en sesión de alineación |
| Conceptos sin ejemplos concretos | Pérdida de claridad | Media | Cada miembro añade 1 ejemplo por concepto principal |
| Herramienta elegida no permite colaboración en tiempo real | Retrasos | Baja | Usar Miro o Lucidchart (colaborativos) |
| Diferencias de criterio entre miembros | Inconsistencias | Media | Ignacio como coordinador decide discrepancias |
| Fechas ajustadas (deadline 28 junio) | Estrés | Media | Dividir temprano, entregar borrador 26 junio |

---

## 8. Conclusión y Recomendaciones

### Resumen de la Exploración

1. **Dominio**: SQA es un campo maduro con conceptos bien definidos (ISO, CMMI, McCall, Fagan, GQM) que permiten construir un mapa conceptual rico y profundo.

2. **Estructura recomendada**: **Jerarquía Top-Down** (3-4 niveles) como base, complementada con **cross-links** entre ramas. Este enfoque maximiza los puntajes en los criterios de jerarquía y conexiones cruzadas.

3. **Inventario completo**: ~70-80 conceptos distribuidos en 12 ramas principales, cada una con 3-7 subconceptos y 20 cross-links documentados.

4. **Visual**: Paleta de 4 colores (azul, verde, naranja, púrpura), formato claro con niveles diferenciados por tamaño/estilo de caja, iconos opcionales.

5. **Equipo**: Distribución de 5 ramas entre 5 miembros, con flujo de investigación individual + sesión colaborativa + revisión.

### Ready for Proposal

**Sí**. La exploración está completa. El siguiente paso es la fase **proposal** (sdd-propose), donde se formalizará el alcance final y se definirá el plan de ejecución detallado.

---

*Fin de la exploración*
