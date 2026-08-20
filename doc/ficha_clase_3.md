# Ficha de trabajo – Clase 3

## Identificación

- **Nombre:** Romina Vega
- **Sección:** TI3021
- **Fecha:** 18-08-2026
- **Compañero(a) de trabajo:** 
- **Repositorio individual:** https://github.com/rominavega1243/poos-p1c2-VegaRomina.git

# Parte 0. Punto de partida validado

Este caso representa el **mínimo esperado al finalizar la Clase 2**. Se utilizará como evidencia común para comenzar el diseño orientado a objetos. No reemplaza la entrega individual de la ficha anterior.

## Funcionalidad

Captura básica de una criatura.

## Actor principal

Entrenador.

## Necesidad

Capturar una criatura salvaje disponible utilizando una cápsula de su inventario.

## Entradas

- Criatura seleccionada.
- Disponibilidad de la criatura.
- Distancia entre el entrenador y la criatura.
- Cantidad de cápsulas.
- Probabilidad de captura.

## Proceso

1. Verificar que la criatura esté disponible.
2. Verificar que se encuentre dentro de la distancia permitida.
3. Verificar que el entrenador tenga cápsulas.
4. Consumir una cápsula.
5. Determinar si la captura tiene éxito.
6. Registrar la criatura si la captura es exitosa.
7. Informar el resultado.

## Salidas

- Captura exitosa.
- Captura fallida.
- Mensaje de rechazo por criatura no disponible.
- Mensaje de rechazo por distancia.
- Mensaje de rechazo por falta de cápsulas.
- Cantidad actualizada de cápsulas.

## Reglas

- Solo se puede intentar capturar una criatura por operación.
- Cada intento válido consume una cápsula.
- Un intento rechazado no consume cápsulas.
- La criatura se registra únicamente si la captura tiene éxito.
- La criatura debe estar disponible y dentro de la distancia permitida.

## Dentro del alcance

- Selección de la criatura.
- Validaciones de disponibilidad, distancia e inventario.
- Consumo de la cápsula.
- Resolución del intento.
- Registro de la criatura.
- Información del resultado.

## Fuera del alcance

- GPS real.
- Combates.
- Animaciones.
- Intercambio de criaturas.
- Funciones sociales.

## Criterios de aceptación

### Criterio 1: intento sin cápsulas

- **Dado** que el entrenador no tiene cápsulas,
- **cuando** intenta capturar una criatura,
- **entonces** el sistema rechaza la acción, no modifica el inventario e informa que no hay cápsulas disponibles.

### Criterio 2: intento válido

- **Dado** que la criatura está disponible, se encuentra dentro de la distancia permitida y el entrenador tiene cápsulas,
- **cuando** realiza un intento de captura,
- **entonces** el sistema consume exactamente una cápsula, determina el resultado e informa si la captura tuvo éxito o falló.

### Criterio 3: criatura fuera de rango

- **Dado** que la criatura se encuentra fuera de la distancia permitida,
- **cuando** el entrenador intenta capturarla,
- **entonces** el sistema rechaza la acción, no consume cápsulas e informa que la criatura está fuera de rango.

### Criterio 4: captura exitosa

- **Dado** que el entrenador realiza un intento válido,
- **cuando** el resultado de la captura es exitoso,
- **entonces** la criatura se registra en su colección y el sistema informa la captura exitosa.

---


# Tarjetas de clase y responsabilidades


## Clase 

- **Nombre:** Entrenador
- **Responsabilidad principal:**  Capturar criaturas disponible.
- **Atributos necesarios:** Posición, alias.
- **Métodos posibles:** caminar, capturar, subir niveles.
- **Clase con la que necesita colaborar:** Equipo.
- **Regla o criterio de aceptación que la justifica:** La criatura se registra únicamente si la captura tiene éxito.
- **Responsabilidad que no debería asumir:** Administrar el equipo de criaturas.


## Clase 

- **Nombre:** Inventario
- **Responsabilidad principal:** Guardar criaturas capturadas
- **Atributos necesarios:** espacio maximo , capacidad ocupada, cantidad de capsulas. 
- **Métodos posibles:** Mantener criaturas capturadas.
- **Clase con la que necesita colaborar:** Entrenador.
- **Regla o criterio de aceptación que la justifica:**  captura exitosa.
- **Responsabilidad que no debería asumir:** Capturar criaturas.


## Clase

- **Nombre:** Reserva
- **Responsabilidad principal:** Mantener el registros de la criaturas no ingresadas al equipo activo
- **Atributos necesarios:** Registro de datos , capacidad máxima  , mantener
- **Métodos posibles:** Mantener registrados criaturas no ingresadas
- **Clase con la que necesita colaborar:** Inventario
- **Regla o criterio de aceptación que la justifica:** La criatura se registra únicamente si la captura tiene éxito.
- **Responsabilidad que no debería asumir:** Capturar criaturas


## Comprobación de coherencia

1. ¿Existe una clase que concentre casi todas las acciones? ¿Cuál y qué responsabilidad debería trasladarse?

   **Respuesta:** Si, Entrenador concentra varias acciones.la responsabilidad es de mantener las criaturas capturadas debería trasladarse a inventario.

2. ¿Existe un método en una clase que no posee los datos necesarios para realizarlo?

   **Respuesta:**Si , Reserva ya que tiene el método  de mantener criaturas registradas, pero necesita información de las criaturas que maneja el Inventario.

3. ¿Existe el mismo atributo en varias clases sin una justificación clara?

   **Respuesta:** No , cada clase tiene atributos diferentes según su responsabilidad.

---

# Instancias u objetos concretos

Elige una de tus clases y crea dos objetos con estados distintos.

- **Clase seleccionada:** Criaturas

| Atributo | Objeto 1: Pikachu | Objeto 2: Golduck |
|----------|-----------------------  |-----------------------|
| Nombre   |    Pikachu              | Golduck               |
| Nivel    |      6                  |   9                   |
| Estado   | Capturado               | Capturado             |

- **Método que ambos objetos pueden ejecutar:** Subir de nivel.
- **¿Qué comparten por pertenecer a la misma clase?:** Ambas son criaturas que pueden ser capturadas y subir de nivel.
- **¿Qué cambia entre ambos objetos?:** El nombre, el nivel y las características propias de cada criaturas.

---

# Trazabilidad con los criterios de aceptación

Relaciona cada comportamiento esperado con las responsabilidades propuestas.

| Criterio | ¿Qué información se necesita? | ¿Qué clase debería conocerla? | ¿Qué acción debe realizarse? | ¿Qué clase debería realizarla? |
|----------|-------------------------------|-------------------------------|------------------------------|--------------------------------|
| Sin cápsulas | Cantidad de capsulas disponibles| Inventario | Rechazar la captura e informar que no hay capsulas | Entrenador|
| Intento válido | Disponibilidad, distancia y cantidad de capsulas. | Entrenador e Inventario | Consumir una capsula y determinar el resultado. | Entrenador |
| Fuera de rango | Distancia entre el entrenador y la criatura | Entrenador | Rechazar la captura sin consumir capsulas | Entrenador |
| Captura exitosa | Resultado de la captura y datos de la criatura | Entrenador y Criatura | Registrar la criatura capturada | Inventario|

## Pregunta de análisis

¿Existe algún criterio de aceptación que no pueda cumplirse con las clases y responsabilidades propuestas?

**Respuesta y ajuste necesario:** No. Los criterios de aceptación pueden cumplirse con las clases propuestas. Entrenador se encarga de realizar la captura, Inventario controla las cápsulas y registra las criaturas capturadas, y Reserva mantiene registradas las criaturas que no ingresan al equipo activo.
