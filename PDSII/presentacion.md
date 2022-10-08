# Arquitectura monolitica

# Que es

Modelo tradicional de arquitectura de software, con el cual estamos acostumbrados a trabajar. Puede estar construido como una sola unidad de software o a partir de varias librerias o modulos, pero la clave esta en que al momento de compilar, todo el software se empaqueta como una sola pieza, de modo que todos los modulos y librerias se empaquetaran junto con la aplicacion principal. Esto, principalmente, es la razon que hace que las actualizaciones sean restrictivas y lentas.

Consiste en una interfaz de usuario de lado del cliente (User interface), una aplicacion del lado del servidor (Business layer) y un base de datos (Data interface).

![](![Screenshot from 2022-09-26 09-18-25](https://i.imgur.com/VvukKNM.png))

Si bien puede tener su lado negativo, la realidad es que hoy en dia las aplicaciones monoliticas siguen siendo utilizadas. Donde mas se ven, es cuando aprendemos a programar y tenemos todo el proyecto como unidad. Tambien son utilizadas para proyectos pequenos, debido a que el plantear una arquitectura monolitica lleva menos "boilerplate code", por lo que podemos lograr el objetivo mucho mas rapido.

## Ventajas

- **Facil de desarrollar y desplegar**: debido a que es intuitivo, y que solo existe un unico componente.
- **Performance**: mayor performance comparado a microservicios, debido a que operan de manera local.

## Desventajas:

- **Recompilacion**: por cada cambio que se le haga, habra que realizar una compilacion de TODO el artefacto, y con el tiempo esto demorara bastante.
- **Es facil perder el rumbo**: tener todo en un solo modulo puede ser malo, ya que se pierden las organizaciones de clase del codigo y responsabilidades.
- **Abrumador para los nuevos cambios**: en proyectos grandes, un nuevo programador se va a encontrar perdido a la hora de deployear un cambio, y va a requerir de asistencia para evitar que cometa un fallo.
- **Fiabilidad**: cuando haya un error, puede afectar a la disponibilidad de **TODA** la aplicacion.
- **Dificil incorporar nuevas tecnologias**.

Utilizar una arquitectura monolitica no es realmente malo, siempre y cuando se tenga en cuenta que tendremos que migrar a una arquitectura mas sofisticada a medida que nuestra aplicacion crece hasta determinado nivel. Tambien es muy buena opcion cuando el equipo no cuenta con la suficiente expertice o experiencia, debido de nuevo, a su simplicidad.

# Arquitectura basada en componentes

Se enfoca en descomponer el diseno en componentes logicos o funcionales que expongan interfaces de comunicacion bien definidas.

> :warning: Los componentes son las unidades de modelado, diseno e implementacion.

Cada componente tiene que ser

- Reutilizable
- Sin contexto especifico: aplicable para la reutilizacion en cualquier lado.
- Encapsulado e independiente.

Ejemplos de modulos:

- Paquete de software
- Servicio web o modulo

El estilo de arquitectura basado en componentes cumple con las siguientes caracteristicas:

- Esta disenado para aplicaciones compuestas por componentes individuales.
- Pone enfasis en la descomposicion del sistema para armar cada componente.


---------------------------------------------------------------------------------

## Ventajas

- **Facilidad de instalacion**: permite facil actualizaciones debido a que nuevas versiones no afectan al resto de componentes.
- **Costos reducidos**: al permitir la reutilizacion incluso de componentes externos
- **Facilidad de desarrollo**: al implementar una interfaz bien definida proveemos la funcionalidad definida sin impactar otras partes del sistema.
- **Reusable**: al usar componentes, podemos reutilizar aquellos que hayamos utilizado en proyectos anteriores.

## Desventajas

- **Genera mucho trabajo adicional**: debido a que tenemos que hacer los componentes confiables y personalizables.
- **Cajas negras**: el codigo de los componentes puede no estar disponible para los usuarios de dichos componentes.

## Cuando usarlo

- Cuando sea facil conseguir los componentes
- Pocos o casi ningun dato de entrada. Interfaces de usuario no nos rentaria.

---------------------------------------------------------------------

# Arquitectura basada en eventos

### Que es un evento?
Un evento se define como un cambio de estado de algún sistema. Por ejemplo, alguien compra un producto, otra persona se registra para un vuelo o un autobús llega tarde a algún lugar. (Ejemplo del bondi y la app)

### Que es?
La arquitectura basada en eventos es un patron de diseño de software que permite a una organizacion detectar "eventos" o "momentos" comerciales importantes, y actuar sobre ellos en tiempo real.
Este tipo de arquitectura, reemplaza la arquitectura tradicional de "solicitud/respuesta" donde los servicios tendrian que esperar una respuesta para poder pasar a la siguiente tarea.
La forma de comunicacion es asincronica, significa que el remitente y el destinatario no tienen que esperar el uno al otro para pasar a su siguiente tarea, ya que los sistemas no dependen de ese unico mensaje (Ejemplo de una llamada como algo sincono / Ejemplo de un mensaje como algo asincrono).

### Como funciona?
Productores de eventos -> Almacen de eventos -> Consumidor (Explicacion con la imagen)

Ejemplos:

- Solicitud para restablecer una contraseña
- Un paquete que llegó fue entregado a su destino
- Un almacén de comestibles actualiza su inventario
- Se denegó un intento de acceso no autorizado

---------------------------
- Enviar al cliente un correo electrónico para restablecer la contraseña
- Se cierra la factura
- Se realiza un pedido de más lechuga (o cualquier material que se esté agotando)
- Se bloquea una cuenta y se notifica al personal de seguridad


**Desventaja:** como se basa en eventos, requiere mucho trabajo en lograr identificar perfectamente todos los eventos que se pueden dar y su posible respuesta
**Ventaja:** permite el intercambio en tiempo real entre productores y consumidores