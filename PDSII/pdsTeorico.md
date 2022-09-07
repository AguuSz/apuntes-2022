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

# [31-ago]

Para disenar previamente hay que pensar y tomar decisiones.
Disenar se basa en **pensar la mejor solucion** para resolver un problema en cuestion. Consiste en considerar el negocio del software que estamos haciendo, y pensar que modelos nos van a aportar informacion y faciliten el coding.

Podemos disenar orientado a objetos por ejemplo. Este metodo, nos pondra a pensar en el conjunto de objetos que vamos a tener en el coding. Nos permite tener una traza directa con estos y se hace mas facil de entender para los programadores. Nos permite ver que hacen estos componentes y como se relacionan.

## Trabajar de manera iterativa

Nos permite no tener que tomar todas las decisiones enseguida, debido a que las podemos ir postergando a momentos mas oportunos. Esto es de suma utilidad cuando no tengo toda la informacion, o cuando los requerimientos cambian.
Este modo tambien esta bueno, porque el codear no es lo dificil, sino que es el problema es que es dificil.

## Proceso del diseno

Consiste en encontrar componentes en base a los requerimientos del sistema. Luego, se definen los componentes $\rightarrow$ esto va de la mano con encontrar los diagramas de como identificarlos, ya sea con diagramas de clases, objetos, etc.

## Responsabilidades de las tareas

Suelen decir:

- Costo
- Completitud
- % de completittud
- Tiempo

## Particularidades

Existen algunos componentes, que una vez diagramados como objetos, los consideraremos como interfaz. Esto quiere decir, que los objetos que marquemos como interfaz son objetos los cuales no tienen comportamiento. Si bien pueden hacer algunas acciones, no tienen ningun tipo de validacion.
