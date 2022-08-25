# [16-ago]

Auditar: controlar si una actividad se cumple.

Para pode realizar una auditoria, es necesario contar con un buen background del negocio.

Uno debe preparar el sistema de antemano para ser auditado. Es decir, preparar el modulo auditario.
El enfoque que se le da es que cada uno ocupe el rol de auditor

Hay veces donde la implementacion de las mejoras es lo complicado. Ejemplo cables de racks.

## Clasificaciones

- Internas: es de algun area de la organizacion.
- Externas: no necesariamente es un ente gubernamental, sino que puede ser un agente externo.

## 3 preguntas para la autenticacion: MAF

Multiple faccion de autenticacion

- Que soy?
- Que tengo?
- Que se?

Ley 26338: ley de seguridad informatica.

## Posibles casos para mejorar

- **Filtro de mac**: ya practicamente no sirve porque existen clonadorees de MAC Address.

En una auditoria tenes que marcar el alcance y dar un tiempo de remedacion. Y se reporta al jefe maximo. Tambien debe tener en cuenta la duracion aproximada de lo que se demoraria en realizar un arreglo, esto con el proposito de dar un tiempo de remedacion adecuado.

---

# [23-ago]

Las funciones hash garantizan la **integridad**.

Funciones de **HASH** $\longrightarrow$ **Integridad**
Funciones de **encripcion** $\longrightarrow$ **Confidencialidad**

Sha-2: {256, 384, 512}

Aunque hoy en dia ya existe la SHA-3.

Son funciones de **unica via** o _one way function_. Esto se debe a que dada una entrada genero una salida hasheada, pero no puedo volver para atras. Esto se lo conoce como **digesto**. Este tipo de funciones **no encriptan.**

## Funciones de encripcion

Funciones que se encargan de mantener la confidencialidad de la informacion. Se introduce lo que es conocido como una **clave.** La diferencia con las funciones de hash, es que las de encripcion son **bidireccionales**, por lo cual existe una manera para volver al mensaje original, sera necesaria la clave, pero es posible.

---
