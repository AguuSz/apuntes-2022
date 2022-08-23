# Clase teorica [23-ago]

Las funciones hash garantizan la **integridad**.

Funciones de **HASH** $\longrightarrow$ **Integridad**
Funciones de **encripcion** $\longrightarrow$ **Confidencialidad**

Sha-2: {256, 384, 512}

Aunque hoy en dia ya existe la SHA-3.

Son funciones de **unica via** o _one way function_. Esto se debe a que dada una entrada genero una salida hasheada, pero no puedo volver para atras. Esto se lo conoce como **digesto**. Este tipo de funciones **no encriptan.**

## Funciones de encripcion

Funciones que se encargan de mantener la confidencialidad de la informacion. Se introduce lo que es conocido como una **clave.** La diferencia con las funciones de hash, es que las de encripcion son **bidireccionales**, por lo cual existe una manera para volver al mensaje original, sera necesaria la clave, pero es posible.
