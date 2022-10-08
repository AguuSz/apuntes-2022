# Diseño

El diseño es una representacion significativa de ingenieria de algo que vamos a construir.

### Pressman

- El objetivo del diseño es aplicar un conjunto de principios.
- El proceso de diseño va de una vision "panoramica" del software a una mas cercana que define el detalle requerido para implementar un sistema.
- Ademas, se diseñan las interfaces internas, externas y de usuario.

### Conceptos de diseño, ponen la necesidad en:

- Abstraccion
- Importancia en la arquitectura
- Beneficios de la ingenieria basada en patrones
- Separacion de problemas
- Modularidad eficaz
- Software entendible y de facil mantenimiento
- Reduccion de efectos colaterales cuando hay errores
- Independencia funcional para construir modulos eficaces
- Uso de refinamiento
- Aplicacion de rediseño
- Importancia de las clases orientadas a objetos

### Areas importantes del diseño

- Datos
- Arquitectura
- Interfaces
- Componentes

### Quienes diseñan?

- Ingenieros del Software
- Ingenieros en Sistema
- Cualquier otro relacionado

### Ventajas de diseñar explicitamente y documentar arquitectura

- Comunicación con los stakeholders
- Analisis del sistema
- Reutilización a gran escala

# Clase 31-ago

### Que es diseñar

Es tomar decisiones/pensar
Es modelar una solucion

### Que no es diseñar

No es hacer dibujos y cajitas
Tirar codigo solamente
Saber diseñar no es saber UML. En todo caso saber UML me permite comunicar el diseño

### Diseñar orientado a objetos

Encontrar los componentes y ver como se relacionan

### Trabajar en forma iterativa

Ventaja: No tengo que tomar las decisiones
- Porque postergo decisiones?
-No siempre tengo toda la informacion
-El usuario y el desarrollador van aprendiendo sobre el dominio mientras se contruye la aplicacion
-Los requerimientos cambian
-Hoy no es un problema la programacion, lo complejo es el problema en si

### Proceso de diseño

- Encontrando componentes
- Casos de uso / User stories / ENcontrar los requerimientos de un sistema
- Definir componentes:
  -Diagrama de clases
  -Diagrama de objetos
  -CRC Cards

### Objetos posibles

- Proyecto
- Tarea
- Complejidad
- Impuesto
- Subtarea

### Responsabilidades de las tareas

- Saben decir su costo
- Saben decir su completitud
- Las que no tienen subtareas, les puedo setear el % de completitud
- Saben su tiempo

1) Genero codigo
2) Pregunto al que entiende del negocio
3) No tomo este camino y postergo la decision

### Tipos de clasificacion de posibles tareas

- Tarea y subtarea
- Tarea simple y compuesta
- Tarea facil, media y compleja

#  Ejercicio Migraciones

1) Identificar subsistemas:
  - Subsistemas de validacion de personas
  - Subsistema de registro de entrada y salida
  - Subsistema de comunicacion: (sistema en tiempo real)

2) Identificar objetos mas relevantes del dominio
   
  Subsistema de validacion de personas:
   - Pasaporte
   - Antecedentes
   - Huella
   - Foto
   - Persona

  Subsistema de registro de entrada y salida:
   - Entrada
   - Salida
   - Comprobante de salida
   - Codigo QR
  
  Subsistema de comunicacion:
  - Mensaje
  - Puerta
  - Controlador

# Arquitectura de software

Importante a la hora de plantear la arquitectura:

- Documentarla
- Importancia de la arquitectura
- Definicion de la arquitectura
- Estilos arquitectonicos


