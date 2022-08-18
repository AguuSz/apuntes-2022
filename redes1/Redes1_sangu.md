# Redes I

# Clase 18-08 (T)

### Tipos de conexiones

- Cable
- DSL
- Celular
- Satelite
- Dial-up telephone (no existe mas)

Protocolo: Conjunto de reglas, acuerdos y estandares. Define 3 cosas, que se comunica (sintaxis), como se comunica (semantica) y cuando se comunica (temporizacion).

Gateway: Dispositivo que traduce protocolos, permitiendo la comunicacion de distintos clientes.

### Arquitectura de red

- Tolerante a fallas: que permita conexiones rebundantes basicamente
- Escalabilidad: que la red de la posibilidad de seguir creciendo a futuro
- Calidad del servicio: hace referencia a las prioridades, a la posibilidad de hacer un "balanceo de carga", basicamente dividir el ancho de banda en las actividades que se desee, darle mas o menos ancho de banda a la actividad que se desee (prioridad)
- Seguridad: debe garantizar la seguridad, confidencialidad, integridad y disponibilidad de los datos

### Alternativas para la seguridad

- Lista de accesos (ACL)
- VPN
- Deteccion de intrusos

## Normas estandares

- Justificacion: interoperatividad
- Son el resultado de un proceso de normalizacion
- Acuerdos documentados

#### Tipos de estandares

- De org profesionales
- De gobiernos
- Multifabricantes
- Nacionales
- Multinacionales
- Internacionales

# Modelo OSI

![](https://media.fs.com/images/community/upload/kindEditor/202106/08/siete-capas-de-modelo-osi-1623136242-cywGEI9RkM.png)

**International Standards Organization**

Es un modelo por capas:
- Aplicacion (7): Procesos de red a aplicaciones
- Presentacion (6): Representacion de datos
- Sesion (5): Comunicacion entre hosts
- Transporte (4): Conduccion de extremo a extremo
- Red (3): Capa de direccionamiento, indica la ruta para la transmision de los paquetes.
- Enlace de datos (2): Prepara el medio para poder darle los servicios a la capa superior. En esta capa esta la MAC
- Fisica (1): Transmision de los bits

### Unidades de datos

- Capa 7 - Datos
- Capa 6 - Datos
- Capa 5 - Datos
- Capa 4 - Segmentos
- Capa 3 - Paquetes
- Capa 2 - Tramas
- Capa 1 - Bits
