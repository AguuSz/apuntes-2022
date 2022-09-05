# Redes I

#### [18-08-22] Clase T

* Protocolo: Cjto de reglas, acuerdos y estandares para que los dispositivos conectados se puedan entender.
    * Define qué se comunica(Sintaxis), cómo se comunica(semantica) y cuando se comunica(temporalidad).
* Arquitectura de Redes:
    * Tolerancia a fallas(es decir, que en caso de fallas no se pierda la comunicacion). Normalmente se logra con conexiones redundantes.
    * Escalabilidad: Que la red tenga posibilidad de seguir creciendo a futuro.
    * QoS[Quality of service]: Poder dividir el ancho de banda entre distintos tipos de trafico y darles prioridad.
    * Seguridad de la Red:
        * Confidencialidad
        * Integridad de los datos
        * Disponibilidad de los datos

* Normalizacion: Busca la interoperatividad y la compatibilidad entre distintos dispositivos.
* Estandares: Resultados de un procso de normalizacion

* Modelo OSI(Open System interconection): 
    ![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202022-01-26%20a%20la%28s%29%207.18.25%20p.m.-c9668c1c-6cea-4114-a78f-a37d97f00bea.jpg)
    * Modelo abierto
    * No es un estandar:  No define "como" hacer las cosas, si no "donde".
    * Caracteristicas: 
        * Reduce la complejidad
        * Estandariza interfaces
    * Encapsulado de datos: Bits se convierten en tramas, tramas en paquetes, paquetes en segmentos y segmentos en datos.

    --- 
    * Capa Fisica: Datos Binarios
    * Capa Enlace de datos: MAC
    * Capa de red: IP

    




* ADSL: Asimetric DSL
* war-driving