# Simulador Skylark

> ⚠️ **Versión de prueba (beta) · Código abierto · Uso exclusivamente académico**
>
> Lee este documento antes de utilizar el simulador.

**Abrir el simulador:** (https://janthce.github.io/simulador-skylark/)

---

## ¿Qué es?

El Simulador Skylark es una herramienta web para estimar, en etapa temprana, la fabricación digital de una vivienda modular basada en el sistema constructivo abierto **WikiHouse Skylark**. Con las dimensiones del edificio y la ubicación de las aberturas, calcula:

- Área útil, área construida y perímetro, en grilla modular de 0,60 m.
- Cantidad y tipos de bloques (piso, muros, frontones, cubierta, esquinas y aberturas).
- Despiece aproximado de piezas para corte CNC.
- Nesting simplificado en tableros y porcentaje de aprovechamiento o merma.
- Tiempo estimado de mecanizado CNC, costo de tableros, peso de la estructura, porcentaje de vanos vidriados y superficie de membrana.
- Vista 3D, planta y elevaciones interactivas.
- Comparación de escenarios (por ejemplo, distintos espesores de tablero, luces o sistemas).

Fue desarrollada como apoyo al trabajo de título *"Cuantificación de beneficios del diseño paramétrico DfMA en fabricación digital: reducción de tiempo de preparación y desperdicio de material en sistemas modulares CNC"*, de la carrera de Ingeniería en Construcción de la Universidad de Valparaíso.

## Estado del proyecto: versión de prueba

Esta es una **versión de prueba en desarrollo**. Puede contener errores, cambiar sin previo aviso o entregar resultados distintos entre versiones.

## Advertencias importantes

1. **No es un archivo de corte.** La geometría de las piezas es una **aproximación simplificada** para comparar alternativas. No corresponde al despiece oficial de WikiHouse ni genera archivos para máquinas CNC.
2. **No reemplaza el cálculo estructural.** Los resultados no validan la resistencia, estabilidad ni el cumplimiento normativo (OGUC, reglamentación térmica, NCh u otras). Todo proyecto real debe ser revisado por un profesional competente.
3. **Las cantidades son estimaciones.** El número de tableros, el tiempo de corte, los costos y los pesos dependen de supuestos simplificados. Sirven para comparar escenarios entre sí, no como presupuesto ni cubicación final.
4. **Los valores por defecto son de ejemplo.** El precio del tablero, la densidad, el avance de la fresa y otros parámetros deben ajustarse a cada caso.
5. **Uso bajo tu propia responsabilidad.** El autor no se hace responsable por decisiones de diseño, compra, fabricación o construcción basadas en esta herramienta.

## Principales supuestos del modelo

| Parámetro | Supuesto |
|---|---|
| Grilla modular | 0,60 m en largo y ancho |
| Bloques tipo cassette | 2 costillas, travesaños cada ~600 mm, 2 pieles y conectores tipo mariposa |
| Módulos de esquina | El primer y el último módulo de cada muro no admiten aberturas |
| Dintel mínimo | 0,15 m de bloque sobre cada abertura |
| Cubierta a dos aguas | Pendiente de 42° |
| Piezas mayores al tablero | Se dividen en tramos con empalme |
| Nesting | Empaquetado por franjas, 5 mm de borde y separación igual al diámetro de la fresa |
| Tiempo CNC | Longitud de corte × número de pasadas ÷ avance + tiempo de cambio de tablero |

## Cómo usarlo

1. **Dimensión del edificio:** ingresa el ancho y el largo (interiores o exteriores). El simulador los ajusta a la grilla de 0,60 m y calcula el área.
2. **Sistema y forma:** elige Skylark 150, 200 o 250, la altura de los muros, el tipo de cubierta y la cantidad de frontones en tablero.
3. **Aberturas:** en la pestaña *Planta y aberturas*, elige un tipo (puerta, ventana, ventana alta o ventanal) y haz clic sobre un muro. Arrástralas para moverlas y edita sus medidas en el panel lateral.
4. **Fabricación:** ajusta las medidas del tablero, el espesor nominal y real, la holgura de las uniones y los datos del router CNC.
5. **Resultados:** revisa las pestañas *Vista 3D*, *Despiece*, *Nesting* y *Bloques*.
6. **Escenarios:** guarda configuraciones y compáralas en la pestaña *Escenarios*.

## Privacidad y datos

- El simulador funciona completamente en tu navegador. **No envía ni almacena datos en ningún servidor.**
- Tu configuración y tus escenarios se guardan solo en tu navegador. Si borras los datos de navegación, se pierden.
- Para guardar o compartir un proyecto, usa **Copiar proyecto (JSON)** y pégalo en un archivo `.json`. Después se carga con **Cargar archivo JSON**.
- Se necesita conexión a internet para cargar la vista 3D (biblioteca three.js) y las tipografías.

## Código abierto

El código fuente está disponible en este repositorio. Puedes revisarlo, copiarlo, modificarlo y reutilizarlo con fines académicos y de investigación, según la licencia del repositorio.

Los comentarios, reportes de errores y sugerencias son bienvenidos en la sección **Issues** del repositorio.

## Relación con WikiHouse

Este es un **proyecto independiente** de carácter académico. No está afiliado, patrocinado ni respaldado por WikiHouse Foundation. "WikiHouse" y "Skylark" se mencionan solo como referencia al sistema constructivo abierto en que se inspira el modelo. Para la información oficial del sistema, visita [wikihouse.cc](https://www.wikihouse.cc).

## Autor

**Janth Celedón Miranda**
Tesista de Ingeniería en Construcción, Universidad de Valparaíso, Chile.

## Cómo citar

> Celedón Miranda, J. (2026). *Simulador Skylark: herramienta de estimación de fabricación digital para el sistema WikiHouse* (versión de prueba) [Software]. GitHub.(https://janthce.github.io/simulador-skylark/)

## Historial de versiones

| Versión | Fecha | Cambios |
|---|---|---|
| 0.2 (beta) | Octubre 2026 | Entrada por ancho × largo, planta y elevaciones interactivas, escenarios, peso y vanos |
| 0.1 (beta) | Octubre 2026 | Primera versión: módulos, despiece, nesting y vista 3D |
