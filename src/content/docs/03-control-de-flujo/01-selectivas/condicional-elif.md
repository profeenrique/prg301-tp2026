---
title: Condicional elif
description: Evaluación de múltiples condiciones en Python mediante la estructura elif.
slug: control-de-flujo/selectivas/condicional-elif
sidebar:
  label: Condicional elif
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de comprender la estructura `if`, el uso de comparaciones y la importancia de la indentación en Python.
:::

En muchos problemas, una sola condición no basta. A veces el programa necesita evaluar más de una posibilidad y elegir qué acción realizar según el caso que se cumpla. En ese contexto, `elif` permite ampliar la toma de decisiones sin volver el código innecesariamente profundo o difícil de leer.

## Objetivo

Comprender cómo utilizar la estructura `elif` para evaluar varias condiciones en orden y ejecutar solo el bloque correspondiente al primer caso verdadero.

## Qué aporta `elif`

La palabra reservada `elif` permite agregar nuevas condiciones a una estructura iniciada con `if`. Su propósito es ofrecer caminos alternativos cuando la primera condición no se cumple, pero todavía existen otros casos que deben evaluarse.

En otras palabras, `elif` permite expresar algo como esto dentro del programa:

- Si ocurre la primera condición, ejecuta esta acción
- Si no ocurre, revisa esta otra
- Si tampoco ocurre, revisa una más

Esta estructura resulta especialmente útil cuando un problema tiene varios resultados posibles y cada uno depende de una condición distinta.

La forma general es la siguiente:

~~~python
if condicion_1:
    instruccion_1
elif condicion_2:
    instruccion_2
elif condicion_3:
    instruccion_3
~~~

En esta organización conviene notar algo importante: Python evalúa las condiciones **de arriba hacia abajo**. En cuanto encuentra una condición verdadera, ejecuta ese bloque y deja de revisar las demás.

:::tip[Idea clave]
En una estructura con `if` y `elif`, no se ejecutan todos los bloques verdaderos. Python ejecuta solamente el primero cuya condición se cumple.
:::

## Una decisión con varios caminos

La diferencia principal entre `if` y `elif` está en la cantidad de caminos que puede tomar el programa. Con `if`, el programa decide si ejecuta o no un bloque. Con `elif`, además puede seguir evaluando otras posibilidades cuando la primera condición no se cumple.

Esto resulta muy útil en situaciones como estas:

- Clasificar una nota
- Determinar una categoría de edad
- Mostrar un mensaje distinto según un puntaje
- Asignar una acción según el valor ingresado

Cuando un problema tiene más de dos posibles resultados, `elif` ayuda a mantener el código más claro que usar varios `if` independientes.

## El orden sí importa

Observa el siguiente ejemplo:

~~~python
nota = 5.8

if nota >= 6.0:
    print("Nivel destacado")
elif nota >= 4.0:
    print("Nivel suficiente")
elif nota < 4.0:
    print("Nivel insuficiente")
~~~

En este caso, Python sigue este orden:

1. Evalúa si `nota >= 6.0`
2. Si esa condición no se cumple, evalúa si `nota >= 4.0`
3. Si tampoco se cumple, evalúa si `nota < 4.0`

Como la nota es `5.8`, la primera condición resulta falsa y la segunda resulta verdadera. Por eso, el programa imprime:

~~~text
Nivel suficiente
~~~

No sigue evaluando la tercera condición, porque ya encontró un caso válido.

:::caution[Atención al orden]
El orden de las condiciones puede cambiar el resultado del programa. Por eso, conviene escribir primero los casos más específicos o más restrictivos.
:::

## Un mismo dato, varios resultados

Una de las aplicaciones más frecuentes de `elif` consiste en comparar un mismo dato con distintos criterios. Eso permite clasificar o interpretar un valor sin repetir estructuras separadas.

Observa este ejemplo:

~~~python
temperatura = 12

if temperatura < 10:
    print("Hace mucho frío")
elif temperatura < 20:
    print("La temperatura es templada")
elif temperatura < 30:
    print("Hace calor")
~~~

Aquí todas las condiciones se relacionan con el mismo dato: `temperatura`. Sin embargo, el resultado final depende del primer tramo que se cumpla.

Este tipo de escritura permite representar rangos de valores con bastante claridad, siempre que las condiciones estén bien ordenadas.

## `elif` no reemplaza cualquier estructura

Aunque `elif` es muy útil, no debe usarse por costumbre en cualquier situación. Su valor aparece cuando realmente existe una secuencia de casos que deben evaluarse uno tras otro.

Por ejemplo, si solo necesitas verificar una condición, basta con `if`. Si necesitas evaluar varios caminos excluyentes, `elif` resulta apropiado. Y si necesitas comparar un mismo valor con muchos casos muy concretos, más adelante puede ser conveniente explorar `match`.

:::note[Una decisión bien escrita]
Usar `elif` tiene sentido cuando las condiciones forman parte de una misma decisión y solo uno de los resultados debe ejecutarse.
:::

## Un ejemplo más cercano a un problema real

Supongamos que se desea clasificar el rendimiento de una estudiante según su nota final.

~~~python
nota = float(input("Ingresa la nota final: "))

if nota >= 6.0:
    print("Rendimiento alto")
elif nota >= 4.0:
    print("Rendimiento satisfactorio")
elif nota >= 1.0:
    print("Rendimiento insuficiente")
~~~

En este ejemplo, el programa:

1. Solicita una nota al usuario
2. Convierte el dato a `float`
3. Evalúa las condiciones en orden
4. Muestra el mensaje correspondiente al primer caso que se cumple

Si la estudiante ingresa `5.2`, el programa mostrará:

~~~text
Rendimiento satisfactorio
~~~

La utilidad de `elif` se aprecia con claridad: el programa puede distinguir entre varios escenarios sin recurrir a estructuras innecesariamente anidadas.

:::caution[Conversión de datos]
Si el valor ingresado representa una cantidad numérica, recuerda convertirlo antes de compararlo. `input()` devuelve texto.
:::

## Comparar no es lo mismo que anidar

Al comenzar, a veces se intenta resolver este tipo de problemas escribiendo varios `if` separados o anidando decisiones innecesariamente. Sin embargo, cuando los casos son excluyentes y pertenecen a una misma clasificación, una secuencia con `if` y `elif` suele ser más clara.

Compáralo con esta idea:

- Primero se revisa el caso más alto
- Si no se cumple, se revisa el siguiente
- Después se revisa otro
- Y así sucesivamente

Ese orden convierte la lectura del programa en una secuencia lógica fácil de seguir.

## Para ponerlo en práctica

Escribe un programa en Python que solicite la edad de una persona y muestre un mensaje según uno de estos casos:

- Si la edad es menor que `12`, mostrar `Niñez`
- Si la edad es menor que `18`, mostrar `Adolescencia`
- Si la edad es menor que `60`, mostrar `Adultez`
- Si la edad es `60` o mayor, mostrar `Persona mayor`

### Requisitos

- Debe solicitar la edad usando `input()`
- Debe convertir el dato a `int`
- Debe usar `if`, `elif` y `else`
- Debe mostrar un solo resultado

### Ejemplo de interacción

~~~text
Ingresa tu edad: 15
Adolescencia
~~~

:::tip[Antes de escribir el código]
Piensa primero en el orden de las condiciones. En ejercicios de clasificación, ese detalle suele ser más importante que la escritura misma del `elif`.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta `if`, `elif` y `else` de manera progresiva, con ejemplos y explicaciones orientadas al aprendizaje.

- [Referencia del lenguaje: sentencia `if`](https://docs.python.org/3/reference/compound_stmts.html#the-if-statement)  
  Describe con mayor precisión técnica cómo se define esta estructura dentro del lenguaje, incluyendo el uso de cláusulas `elif`.

- [Documentación oficial en español: más herramientas para control de flujo](https://docs.python.org/es/3/tutorial/controlflow.html)  
  Ofrece una versión accesible del tema en español, útil para reforzar la comprensión general de estas estructuras.