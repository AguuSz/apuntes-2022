# Clase [01-sep]

## Direccionamiento IP v.4 aka Subunetting

Existen 2 esquemas:

- MAC $\rightarrow$ direccion fisica o rigida $\rightarrow$ capa fisica modelo OSI. (capa 2)
- IP $\rightarrow$ direcciones logica $\rightarrow$ capa de red modelo OSI. (capa 3)

Solapamiento de IP: cuando 2 redes IP coinciden.

Sistemas NAT $\rightarrow$ te traduce una ipv6 a una ipv4. Es por esto que vemos las direcciones ipv4 todavia, a pesar de que ya se hayan acabado.

> :warning: Una direccion IP es una direccion de 32 bits de extension separados por puntos por cada octeto de bits (1 byte).

Se puede identificar

- N de red $\rightarrow$ se utiliza para el enrutamiento
- N host / cliente $\rightarrow$ se utiliza para el enrutamiento
- N **opcional** de subred $\rightarrow$ se utiliza para el direccionamiento.

Se utilizan 1, 2 o 3 octetos para generar hosts o redes/subredes.

## Tipos de IPS

- Clase A:
  - El primer bit es 0.
  - En decimal, va desde 0 hasta 127.
- Clase B:
  - Lo 2 primeros bits son el 1 0.
  - En decimal, va desde 128 hasta 191.
- Clase C:
  - Los 3 primeros bits son 1 1 0
  - En decimal, va desde 192 hasta 223.
- Clase D:
  - Los 4 primeros bits son 1 1 1 0 .
  - En decimal, va desde 224 hasta 239.
- Clase E:
  - Los 4 primeros bits son 1 1 1 1.
  - En decimal, va desde 240 hasta 255.

## Restricciones de las direcciones IPs

1. La primera restriccion: el primer octeto no puede valer 0.
   1. Una direccion que empieza por 0, es nula.
2. El primer octeto no puede valer 127.
   1. Es una direccion de prueba que sirve para hacerte ping a vos mismo. Se denomina **IP loopback**.
3. El primer octeto no puede valer 255.
   1. Direccion de broadcast o multidifusion.
4. El ultimo octeto tampoco puede valer 0.
   1. Estaria diciendo que nuestro dispositivo es el 0, es decir que no hay dispositivo.
5. El ultimo octeto tampoco puede valer 255.
   1. De nuevo, por broadcast.
6. Direccion IP debe ser unica en internet, y una direccon de host tiene que ser unica en la red o subred.

Las direcciones IP pueden ser

- Publicas: la que te da el proveedor de internet.
- Privada: del router para abajo, todas esas son privadas porque solo se conocen dentro de la red.
- Estatica: son fijas.
- Dinamica: (DHCP) $\rightarrow$ se encarga de brindar distintas IPs.

Una mascara de subred es una direccion que le permite a la direccion ip ocultarse de internet.

Mascaras default:

- Clase A: 255.0.0.0 $\rightarrow$ Red.Host.Host.Host
- Clase B: 255.255.0.0 $\rightarrow$ Red.Red.Host.Host
- Clase C: 255.255.255.0 $\rightarrow$ Red.Red.Red.Host

Redes y hosts:

- Clase A: Maximo $2^7=$ 128 redes $\rightarrow$ $2^{24} - 2= 16,777,214$ hosts
- Clase B: Maximo $2^{14}=$ 16,384 redes $\rightarrow$ $2^{16} - 2= 65,534$ hosts
- Clase C: Maximo $2^{21}=$ 2,097,152 redes $\rightarrow$ $2^{8} - 2= 254$ hosts

## Ejemplo

Nos dan la IP: `192.10.10.0`. Queremos dividir en 14 subredes con 14 nodos/hosts por cada subred. Identificar numero de subred, **primera** direccion IP utilizable, **ultima** direccion IP utilizable y la division de broadcast.
