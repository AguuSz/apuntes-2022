# Diseno

El diseno agrupa el conjunto de principios que llevan al desarrollo de un sistema de calidad.

## Criterios de un buen diseno:

- **Resistencia**: no tiene que tener errores que impidan su funcionamiento.
- **Funcionalidad**: cumplir los fines que persigue.
- **Belleza**: la UI/UX debe ser placentera.

> La meta es crear un modelo de software que implemente correctamente todos los requerimientos del usuario, y que a la vez cause placer a quienes lo utilicen.

El proceso comienza por centrarse en la arquitectura. Se definen los subsistemas, se establecen los mecanismos de comunicacion entre estos, se identifican los componentes y luego se desarrolla la descripcion detallada de cada uno.

## Enfasis

Se hacen enfasis en la necesidad de:

- Abstraccion: para crear componentes reutilizables
- Importancia de la arquitectura: para entender mejor la estructura general del sistema (macro).
- Aplicar ingenieria basada en patrones: como tecnica de diseno con una capacidad ya comprobada.
- Separacion de problemas
- Modularidad eficaz: permite mejor manejo de la complejidad y un mejor mantenimiento a largo plazo.
- Aplicar un resideno: consiste en optimizar el diseno obtenido en una primera instancia.
- No perder de vista nunca los requerimientos a lo largo de las iteraciones.

Para lograr un buen diseno es necesario la diversificacion y luego la convergencia.

## Conceptos y principios

El diseno se centra en cuatro areas importantes:

- Datos
- Arquitectura
- Interfaces
- Componentes

> Como puedo estar seguro de lo que he hecho esta bien? $\rightarrow$ en cada etapa revisar consistencia y calidad.

## Ventajas de la documentacion

- Comunicacion con los stakeholdes.
- Analisis del sistema: permite analizar rendimiento, fiabilidad y mantenibilidad.
- Reutilizacion a gran escala: nos permite ver como esta organizado un sistema y como interoperan sus componentes.

## Necesidades y componentes para suplirlas

1. Rendimiento $\longrightarrow$ Subsistemas
2. Proteccion $\longrightarrow$ Capas
3. Seguridad $\longrightarrow$ Unico subsistema
4. Disponibilidad $\longrightarrow$ Componentes redundantes.
5. Mantenibilidad $\longrightarrow$ Componentes independientes.

## Evaluando el diseno

Se sugieren 3 caracteristicas guias para evaluar un buen diseno:

- Debe implementar todos los requerimientos explicitos que desean los participantes.
- Debe ser una guia legible y comprensibles para los developers y los unit testers.
- Debe proporcionar el panorama completo del software.

# Diagramado

## Diagramas de bloques

Usados para describir disenos de subsistema en donde cada caja en el diagrama representa un subsistema. Las flechas significan que los datos o senales de control pasan de un subsistema a otro en la direccion dada por la cabeza de la flecha.

[Leer principios que guian el diseno.pdf]
