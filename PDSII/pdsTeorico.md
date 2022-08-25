# 4 Areas del diseno

En el diseno el enfasis principal es la calidad.
Es un proceso iterativo donde vamos a hace rque los requisitos se trazucan a un plano.

Factores de calidad externos son propiedades del software que pueden ser observadas por los usuarios

- Velocidad
- Fiabilidad
- Grado de correccion
- Usabilidad.

Se hace mencion de una piramide, la cual esta conformada desde arriba hacia abajo como:

- [Arquitectura](#arquitectura)
- [Datos](#datos)
- [Interfaz](#interfaz)
- [Componentes](#componentes)

## Arquitectura

Preguntas que se deberia poder responder como arquitecto $\downarrow$

- Existe una arquitectura de aplicacion generica que pueda actuar como una plantilla para el sistema que se estan disenando?
- Que estilo o estilos arquitectonicos son apropiados para el sistema?
  - Buscar utilizar un patron apropiado para el dominio.
- Cual sera la aproximacion fundamental utilizada para estructurar el sistema?
  - Habla de cuales son los componentes y como se distribuyen en la arquitectura.
- Como se descompondran en modulos las unidades estructurales del sistema?
- Como se evaluara?
- Como deberiamos documentar la arquitectura del sistema?

## Datos

Transforma el modelo de dominio de informacion que se crea durante el analisis, en las estructuras de datos que se necesitaran para implementar el software.

## Interfaz

El diseno de la interfaz describe la manera de comunicarse el software dentro de si mismo, con sistemas que interoperan dentro de el y con las personas que lo utilizan.
Implica un flujo de informacion y un tipo especifico de comportamiento.

## Componentes

Transformamos los elementos creados en la arquitectura en una descripcion paso a paso de como formar los componentes del software.
Se utilizan diagramas de **tiempo**, de **secuencia**.

---

# Diagramas estructurales

- Diagramas de clase
- De componentes
- De objetos
- De despliegue
- De artefactos: relacion con otros artefactos y con las clases a las que se implementan.

# Diagramas de comportamiento

- De casos de uso
- De secuencia
- De estados
- De actividades
