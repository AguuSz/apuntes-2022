# [18-agosto $\rightarrow$ Clase Teorica]

# Elementos de redes

Redes SAN: Storage Area Network $\rightarrow$ para los datacenter.

## Roles:

- HOST: suelen ser pcs, celulares, tablets, tvs, consolas.
- Dispositivos intermedios: routers, switches, firewalls.
- Network media: Medios LAN, Wifi, WAN.

## Topologias:

- Fisicas: cada dispositivo esta en su lugar fisico.
- Logicas: vamos a trabajar con este, que es trabajar con direcciones IPs (numeracion)

## Distintas conexiones

- Cable: de toda la vida
- DSL: falta la letra A al inicio $\rightarrow$ simboliza la asimetria.
- Moviles: la que utilizamos con los celulares.
- Satelite: como directv.

Por cada mensaje que se envia por la red, se envian una serie de reglas, acuerdos y estandares. Esto se representa mediante los **protocolos**.
Un protocolo define 3 cosas:

- Que se comunica $\rightarrow$ Sintaxis
- Como se comunica $\rightarrow$ Semantica
- Cuando se comunica $\rightarrow$ Temporizacion

La idea es que tengamos una red convergente, en la cual se compartan los mensajes de todos los dispositivos e interpretando el protocolo sepa a que dispositivo ir.
Gateway $\longrightarrow$ traduce los protocolos.

## Arquitectura de red

Toda red siempre tiene en cuenta estas 4 consideraciones:

- Tolerancia a falla
  - Que ofrezca caminos redundantes para que el servicio no se corte.
- Escalable
  - Que la red ofrezca la posibilidad de seguir creciendo a futuro.
- Calidad de servicio (QoS)
  - establece prioridades, para ciertos tipos de traficos brindarle mas prioridad. Divide el ancho de banda para streaming, juegos, y el resto de internet.
- Seguridad
  - que protejan los datos que viajan a traves de la red. Se priorizan confidencialidad, integridad y disponibilidad.
  - Herramientas que sirven para aportar a esta causa: firewalls, lista de control de acceso (ACL), VPNs, sistemas de prevencion de intrusos (IPS).

## Estandares

Se busca la compatibilidad e interoperatividad de los dispositivos. Que sea de facil mantenimiento, simple uso.

Aseguran que los materiales, productos, procesos y servicios que se ajusten a algun proposito especifico.

# Modelo OSI

> OSI: Interconexion de sistemas abiertos.

Es un modelo de red dividido en capas. Permite el **encapsulamiento**.

Las capas, vistas de abajo hacia arriba:

1. Fisica: transmision binaria
2. Enlace de datos: acceso al medio $\longrightarrow$ MAC
3. Red: direccionamiento y mejor ruta $\longrightarrow$ IP
4. Tranporte: conexiones de extremo a extremo
5. Sesion: comunicacion entre hosts
6. Presentacion: representacion de datos
7. Aplicacion: Procesos de red a aplicaciones.

El flujo de datos para comunicar A y B es el siguiente:

1. Desde A va de arriba abajo hasta llegar a la capa fisica, completando cada vez el paquete enviado con la informacion que brinda cada capa.
1. Luego, se recorre horizontalmente la capa fisica hasta llegar a B.
1. Una vez completado en B, realiza el camino inverso yendo de abajo hacia arriba en el modelo.
