# Ficha de trabajo - Clase 2

## Comprensión del problema y alcance

**Asignatura:** Programación Orientada a Objeto Seguro (TI3021)  
**Unidad:** 1  
**Modalidad:** Parejas  
**Tipo de actividad:** Formativa  

| Identificación | Información |
|---|---|
| Integrante 1 | Romina vega |
| Integrante 2 | Natalia Gonzalez |
| TI3021  17-08-2026 |  |
| URL del repositorio |                    |

## Propósito

Analizar y delimitar una funcionalidad antes de diseñar clases o escribir código. La ficha final debe permitir que otra persona comprenda qué necesita el sistema, qué reglas debe respetar y cómo comprobar si responde correctamente.

> **Regla de trabajo:** en esta clase no se diseñan clases, atributos ni métodos. Primero se justifica qué se necesita; la solución técnica comenzará en la Clase 3.

## Situación inicial

> Un entrenador se encuentra con una criatura salvaje cercana e intenta capturarla utilizando una cápsula de su inventario.

## 1. Lectura activa: hechos, dudas y supuestos

### 1.1 Tres hechos explícitos

1. Entrenador
2. Criatura salvaje
3. Capsula

### 1.2 Tres ambigüedades convertidas en preguntas

| N.º | Expresión ambigua | Pregunta que debe responder el cliente |
|---:|---|---|
| 1 | Criatura salvaje crecana | ¿existe distancia minima que debe estar para la capturar? |
| 2 | El entrenador intenta capturar usando la capsula | ¿la captura siempre tiene éxito o existe una posibilidad de fallar? |
| 3 | Capsula en el inventario | ¿que ocurre si el entrenador no tiene capsulas disponibles al momneto de capturar? |

### 1.3 Supuesto provisional

**Supuesto:** El entrenador debe tener al menos una capsula disponible, para intentar realizar una captura.
**Por qué es provisional:** El enunciado menciona que utiliza una capsula, pero no indica que ocurre si no tiene ninguna.
**Cómo podría confirmarse:** Consultando al cliente o mediante una regla oficial del sistema.

Un supuesto no es una verdad del caso. Debe quedar marcado hasta que el cliente, una regla oficial o una evidencia lo confirme.

## 2. Del enunciado a una necesidad clara

Fórmula orientadora:

> Permitir que **[actor]** realice **[acción]** sobre **[elemento]**, bajo **[condición]**, y obtenga **[resultado observable]**.

### 2.1 Actor, necesidad y objetivo

**Actor principal:** Entrenador  
**Necesidad:** Capturar una criatura salvaje cercana utilizando la capsula de su inventario.
**Objetivo reescrito:** Permitir que el entrenador cuando intente capturar una criatura salvaje cerca con una capsula disponible y obtener un resultado de captura.

### 2.2 Entrada, proceso y salida (EPS)

#### Entradas necesarias

1. Verificar que la criatura correspnde al escenario de captura.
2. Comprobar que el entrenador dispone con capsula para realizar la captura.
3. Proceso al intento de captura según las reglas definidas.
4. Determinar si la  criatura fue capturada.
5. Actualizar la cantidad de capsulas cuando corresponda.
6. Registrar el destino de la criatura después de la captura exitosa.

#### Proceso observable

1. El sistema identifica la criatura como el objetivo de la captura.
2. Se permite continuar o se informa que no hay capsulas disponibles.
3. Resultados observables si la captura exitosa o fallida.
4. Mensaje indicando exito fracaso.
5. Inventario actualizado según el éxito según del resultado de la captura
6. Criatura incorporada al equipo activo o enviado a reserva  si el equipo esta completo.

#### Salidas esperadas

1. Criatura como objetivo disponible para capturar.
2. Confirmacion de que la capsula esta disponible o mensajen indicicando que no hay capsulas disponinnbles.
3. Resultados de captura: exitosa o fallida.
4. Mensaje que informa si la criatura fue capturada correctamente o si la captura fallo.
5. Cantidad de capsulas actualizadas correctamene.
6. Criatura incorporada al equipo actual o enviado a la reserva.

**Prueba de coherencia:** cada salida debe poder explicarse a partir de una entrada, una regla conocida y un paso del proceso.

## 3. Reglas, restricciones y alcance

Una **regla** define qué comportamiento es válido. Una **restricción** limita la solución posible. Un **supuesto** es una condición aceptada temporalmente.

### 3.1 Reglas del problema

1. La captura se inicia por un entrenador.
2. La criatura objetivo debe ser una criatura salvaje cercana.
3. La captura utiliza una capsula del inventario del entrenador.
4. El resultado del intento de captura debe ser informado de una forma observable.

### 3.2 Restricciones

1. En esta versión no se defnine clases, atributos ni métodos 
2. La ficha se limita  a definir alcances, reglas, entradas, procesos, salidas y los criterios de aceptacion.
3. Las condicione de exito,consumo de capsula y de comportamiento de la criatura deben ser confirmada anntes de implemnetarse al inventario.

### 3.3 Delimitación de la primera versión

#### Dentro del alcance

1. Intentar captura una criatura salvaje cercana.
2. Validar disponibilidad de las capsulas.
3. Informar el resultado y actualizar el destino de la criatura.
   

#### Fuera del alcance

1. Sistema de combate o daño a criaturas.
2. Compra, venta o la fabricación de las capsulas.
3. Gestión completa del equipo, y las estadísticas o su evolucion.

#### Supuestos por confirmar

1. Probilidad o que mecanismo exacto que determina que capturaste exitosamente.
2. Capsula si se consume en todo los intentos o solo un uso.
3. Regla exacta para el destino cuando si el equipo esta completo.

### 3.4 Preguntas pendientes

1. ¿Qué condiciones exactas determinan que una criatura sea considerada "cercana"?
2. ¿Qué regla determina si la captura es exitosa y como se consume la capsula?

## 4. Criterios de aceptación y revisión entre pares

Un **criterio de aceptación** es una condición concreta y comprobable que permite decidir si una necesidad fue resuelta correctamente.

Estructura sugerida:

> Dado **[contexto]**, cuando **[acción]**, entonces **[resultado observable]**.

**Criterio 1:** Dado...cuando...entonces 
Dado que el entrenador tiene al menos una capsula y una criatura salvaje cercana, cuando intenta capturarla , entonces el sistema procesa el intento e informa si la captura es exitosa o fallida.

**Criterio 2:** Dado...cuando...entonces
Dado que el entrenador no tiene capsulas disponibles , cuando intenta capturar una criatura,  entonces el sistema impide el intento, no modifica el inventario informa que no hay capsulas.

### 4.1 Intercambio con otra pareja

La pareja revisora debe leer la ficha sin una explicación oral y detectar una ambigüedad que obligaría a inventar una regla al diseñar la solución.

**Pareja revisora:** Romina Vega 
**Ambigüedad detectada:** No se define que significa exactamente que una criatura este "cercana".
**Pregunta sugerida:** ¿ Que condición concreta debe cumplirse para considerar que una criatura esta cercana? 
**Decisión del equipo:** ACEPTAR / AJUSTAR / RECHAZAR  
**Justificación:** Aceptar la observación: la pregunta evita inventar una regla durante el diseño y mantiene el punto 
como pendiente

## 5. IA como auditora de requisitos

Primero guarden la ficha original. La IA puede detectar vacíos y formular preguntas, pero el equipo conserva la responsabilidad de decidir y justificar cada cambio.

### 5.1 Registro de la consulta

**Herramienta y fecha:** ChatGPT, 17-08-2026
**Versión original guardada:** SÍ

**Prompt sugerido:**

> Actúa como revisor de requisitos. Analiza esta ficha de captura sin diseñar clases ni escribir código. Detecta ambigüedades o contradicciones; formula cinco preguntas; señala reglas no verificables; no inventes respuestas y marca cada supuesto.

### 5.2 Evaluación de observaciones

| Observación de la IA | Decisión | Justificación del equipo | Cambio realizado |
|---|---|---|---|
| Ambigüedad en el consumo de cápsulas | Aceptar | Para definir las reglas de negocio es fundamental saber cómo interactúa el inventario con cada intento fallido o exitoso. | Se añadiria un supuesto en la Sección 3.3 indicando que la cápsula se consume en cada intento independientemente del resultado, a la espera de confirmación del cliente. |
| Indefinición sobre qué ocurre tras un intento fallido | Aceptar | Es un vacío importante en el flujo observable del proceso. | Se aclararia en el proceso que un fallo solo genera la notificación de fracaso, manteniendo la criatura disponible para un nuevo intento. |
| Presunción de que siempre existe la probabilidad de fallo. | ajustar | No debemos de asumir mecánicas complejas si no han sido especificadas por el cliente.| Se dejaria como un supuesto etiquetado de [PENDIENTE CONFIRMACIÓN] en el algoritmo de probabilidad de captura. |

### 5.3 Pregunta de autoría

**¿Qué sugerencia rechazaron?** La sugerencia de definir la reacción de la criatura tras un intento fallido, dando por ejemplo el si la criatura huye del encuentro o si ataca al entrenador.
**¿Por qué no correspondía?** Porque el comportamiento posterior de la criatura o el combate forman parte del sistema de batalla. 
**¿Qué decisión fue exclusivamente del equipo?** Solo mantener la cápsula como un recurso que se consume en cualquier intento (exitoso o fallido).

> No publiquen contraseñas, correos personales, claves, tokens ni información sensible en la consulta o en el repositorio.

## 6. Mini desafío: cambia una condición

> Cada entrenador puede llevar como máximo seis criaturas activas. Si su equipo está completo, una captura exitosa debe enviarse a la reserva.

### 6.1 Análisis del impacto

**Qué cambió:** Se agregó una condición sobre el estado del equipo activo de la capacidad máxima de 6 criaturas, que determina el destino final de la criatura tras una captura exitosa.
**Secciones afectadas:** ENTRADA / PROCESO / SALIDA / REGLA / ALCANCE / SUPUESTO  
**Nueva decisión:** Se acepta el cambio y se incorpora la validación del tamaño del equipo activo como paso previo a definir el destino final de la criatura. 
**Justificación:** La decisión garantiza la coherencia con la regla de negocio del cliente sin extender el alcance a un sistema completo de gestión de reserva.

### 6.2 Actualización

| Elemento | Antes | Después del cambio |
|---|---|---|
| Entrada/EPS | Se verifica la disponibilidad de la cápsula y el estado de la criatura. | Se agrega como entrada la cantidad actual de criaturas en el equipo activo. |
| Proceso | La Criatura es incorporada al equipo activo o es enviada a reserva sin un criterio explícito de límite. | Se evalúa el tamaño del equipo activo: si es menor a 6, la criatura va al equipo, de otra forma, si es igual a 6, se redirige a la reserva.|
| Regla | La criatura capturada se incorpora al equipo. | Según la regla 3.1.5: El equipo activo no puede superar las 6 criaturas. Si el equipo tiene 6, la captura exitosa debe enviarse a la reserva. |
| Alcance | Gestión completa del equipo fuera del alcance. | Se mantiene fuera de alcance la gestión del almacenamiento, limitándose únicamente a registrar el evento de envío a la reserva. |

### 6.3 Nuevo criterio de aceptación

**Criterio:** Dado que el entrenador tiene 6 criaturas en su equipo activo, una cápsula disponible y una criatura salvaje cercana, cuando este realiza una captura exitosa, entonces el sistema asigna la criatura a la reserva e informa que fue enviada a la reserva por tener el equipo completo.  
**Evidencia esperada:** Un mensaje o confirmación observable del sistema indicando que la captura fue exitosa y que el destino de la criatura es la reserva.

## 7. Ticket de salida

**Resumen en una frase con actor, necesidad, regla principal y resultado:** Permitir que el Entrenador intente capturar una criatura salvaje cercana utilizando una cápsula de su inventario, respetandose el límite de 6 criaturas en el equipo activo, para obtener como resultado observable la actualización de sus recursos y la confirmación del destino de la criatura (permaneciendo en el equipo o yendo a la reserva). 
**Evidencia más clara:** Un mensaje del sistema que confirme explícitamente el resultado de la captura (éxito o fallo), el descuento correspondiente de la cápsula en el inventario y la ubicación final de la criatura (en el equipo activo o en la reserva)
**Ambigüedad pendiente:** La definición exacta de las condiciones para considerar a una criatura como "cercana" (distancia o rango numérico) y la regla/probabilidad explícita que determina si el intento de captura tiene éxito o falla.
**Mejora concreta:** La incorporación precisa de la regla del equipo lleno con máximo de 6 criaturas y la redirección a reserva en el alcance.

## 8. Comprobación final

- [x] Conservamos una versión anterior a la auditoría con IA.
- [x] Actor, necesidad, entradas, proceso y salidas son coherentes.
- [x] Reglas, restricciones, supuestos y alcance están diferenciados.
- [x] Los criterios de aceptación son observables y verificables.
- [x] El cambio del cliente quedó incorporado y justificado.
- [x] No diseñamos clases ni escribimos código antes de tiempo.



## 9. Entrega

1. Crear un repositorio privado por pareja y agregar al docente como colaborador.
2. Guardar este archivo como `docs/ficha_clase_2.md`.
3. Realizar commits con mensajes claros. Se espera al menos un aporte identificable de cada integrante.
4. Cada estudiante debe pegar el mismo enlace del repositorio en AAI/Intranet e identificar a su pareja.
5. Incluir el identificador del commit final en la entrega.

Convención sugerida para el repositorio:

```text
  poos-p1c2-apellido-nombre
```

Primer flujo Git:

```bash
git clone URL_DEL_REPOSITORIO
cd NOMBRE_DEL_REPOSITORIO
git status
git add docs/ficha_clase_2.md
git commit -m "Completa ficha de alcance de captura"
git push
```

Si existe un bloqueo real de cuenta, autenticación o conectividad, cada integrante debe subir temporalmente la ficha en DOCX o PDF a AAI/Intranet y regularizar el repositorio en la clase siguiente. En esta primera práctica, el dominio técnico de Git no modifica la valoración conceptual de la ficha.
