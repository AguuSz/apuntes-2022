# Clase [24-ago]

## Modelo OSI

Representacion **conceptual** de como se transmiten los datos.

Las capas a las que mas le damos importancia son:

- Red
- Enlace de datos
- Fisica

## Definiciones

- **Modem**: modula senales provenientes de coaxil a cable UTP. Modula y demodula.
- **NIC**: Network Interace Card $\rightarrow$ placa de red.
- **Patch cord**: cable UTP o de fibra optica.
- **Hub**: Opera en la capa 1. Aka Concentrador, es un dispositivo para la conexion de varios dipositivos entre si. Recibe las senales, las amplifica y las vuelve a enviar.
  - Divide el ancho de banda por cada una de las bocas conectadas.
  - **Broadcast**: el hub lo que tiene es que cuando enviamos un archivo de una pc a otra, el hub lo distribuye a todas las pcs, esto se conoce como Broadcast, y puede producir colisiones.
- **Switch**: Opera en la **capa 2** del modelo OSI, y esta disenado para resolver problemas de rendimiento, equilibrar el ancho de banda y acelerar la salida de paquetes reduciendo los tiempos de espera.
  - Tenemos la particularidad de que en este tipo de dipositivo existe cierta "inteligencia" y cuenta con un software donde podemos ver que dispositivos estan conectados a este, y ver sus respectivas direcciones MACs. Esto hace que cuando tengamos que enviar un archivo, no hace falta que haga _Broadcast_ sino que envia directamente a la pc que lo solicita.
  - Debido a esta particularidad con la tabla MAC, podemos decir que **CASI** logra una eficiencia perfecta, logrando que por cada boca activa se transmita el total del ancho de banda.
- **Router**: Opera en la capa 3, debido a que necesita de las IPs. No sabe hacer otra cosa mas que establecer rutas. Se utiliza para establecer rutas, y de esa manera que podamos conectarnos a internet, a pesar de que tengamos seteada una red LAN.
  - Es importante la distincion que hay con la caja que nosotros llamamos "Router". Esta caja realmente cuenta con otros dispositivos (Router, switch, access points, etc).
- **Access Point** (AP): Vendria a ser como un switch, pero inalambrico. Se coneta a un router, switch o hub, y emite una senal wifi en un area determinada.
- **Transceiver**: Convierte una senal electrica en pulsos de luz y viceversa. Similar al modem, pero para la fibra.

## Distintos tipos de cable UTP

Los cables se trenzan para aumentar la cancelacion de los campos magneticos, y que de esa manera sean mas aislantes a los campos externos. Los distintos exceptuando el UTP, cuentan con blindaje fisico para aumentar su aislabilidad.

- UTP: No tiene blindaje (aislante) para el PVC. $\rightarrow$ Impedancia 100 Ohms
- STP: Ahora cuenta con un aislante individual por cada parcito de cable. (Shielded Twisted Pair) $\rightarrow$ Impedancia Ohms
- FTP: Ahora si tine un aislante general que recubre todo el par trenzado. (Foiled Twisted Pair).
- SFTP: Cuenta tanto con aislante individual por cada parcito de cable, y uno mas de manera general
