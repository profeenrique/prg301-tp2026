---
title: Condicional elif
description: Evaluación de múltiples condiciones en Python mediante la estructura elif.
slug: control-de-flujo/selectivas/condicional-elif
sidebar:
  label: Condicional elif
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que comprendes la estructura `if`, sabes trabajar con comparaciones y reconoces la importancia de la indentación en Python.
:::

No todos los problemas se resuelven con una sola decisión. A veces el programa no necesita elegir entre “hacer algo” o “no hacerlo”, sino entre varias posibilidades distintas. En esos casos, una sola condición resulta insuficiente. La cláusula `elif` permite ampliar la decisión sin perder claridad, porque organiza varios casos dentro de una misma estructura.

## Objetivo

Comprender cómo `elif` permite evaluar varias condiciones en orden y seleccionar una única acción según el primer caso que resulte verdadero.

## Cuando una sola condición no basta

La estructura `if` resulta suficiente cuando el programa necesita comprobar una sola condición. Pero muchos problemas reales no tienen una única salida posible. Piensa en situaciones como estas:

- Clasificar una nota en distintos niveles
- Determinar una etapa de edad
- Mostrar un mensaje según un rango de puntaje
- Asignar una respuesta distinta según un valor ingresado

En todos esos casos, el programa no se limita a preguntar “¿se cumple esta condición?”, sino que necesita revisar varias posibilidades relacionadas entre sí. Ahí aparece `elif`.

## Qué aporta `elif`

La cláusula `elif` permite agregar nuevas condiciones a una estructura iniciada con `if`. Su función es ofrecer caminos alternativos cuando la primera condición no se cumple, pero todavía existen otros casos que deben evaluarse.

~~~python
if condicion_1:
    instruccion_1
elif condicion_2:
    instruccion_2
elif condicion_3:
    instruccion_3
~~~

Esta forma de escribir el código introduce una idea importante: el programa recorre una serie de posibilidades y se detiene en la primera que corresponde.

En esta estructura conviene reconocer lo siguiente:

- `if` abre la primera condición
- `elif` agrega condiciones adicionales dentro de la misma decisión
- cada bloque indentado representa la acción asociada a un caso posible

:::note[Idea clave]
En una estructura con `if` y `elif`, Python no ejecuta todos los bloques verdaderos. Ejecuta solo el primero cuya condición se cumple.
:::

## Una decisión con varios caminos

La diferencia principal entre `if` y `elif` no está solo en la sintaxis, sino en la lógica que permiten representar.

Con `if`, el programa decide si ejecuta o no un bloque.  
Con `elif`, en cambio, el programa puede seguir evaluando otras posibilidades cuando la primera no se cumple.

~~~mermaid
flowchart TD
    A[Inicio] --> B{¿Se cumple la primera condición?}
    B -->|Sí| C[Ejecutar bloque del if]
    B -->|No| D{¿Se cumple la siguiente condición?}
    D -->|Sí| E[Ejecutar bloque del elif]
    D -->|No| F[Seguir evaluando otros casos]
~~~

Este recorrido muestra una idea central: la estructura no revisa todos los caminos al mismo tiempo, sino uno tras otro, en el orden en que fueron escritos.

## El orden no es un detalle

En `elif`, el orden de las condiciones forma parte del significado del programa. No basta con que las comparaciones sean correctas; también importa dónde están ubicadas.

~~~python
nota = 5.8

if nota >= 6.0:
    print("Nivel destacado")
elif nota >= 4.0:
    print("Nivel suficiente")
elif nota < 4.0:
    print("Nivel insuficiente")
~~~

Aquí Python sigue esta secuencia:

1. Comprueba si `nota >= 6.0`
2. Si no se cumple, comprueba si `nota >= 4.0`
3. Si tampoco se cumple, revisa si `nota < 4.0`

Como la nota vale `5.8`, la primera condición resulta falsa y la segunda verdadera. Por eso, el programa muestra:

~~~text
Nivel suficiente
~~~

La tercera condición ya no se evalúa, porque el programa encontró un caso válido antes.

Esta es una de las ideas más importantes del tema: en una estructura con `elif`, el resultado depende tanto de las condiciones escritas como del orden en que aparecen.

:::caution[Atención al orden]
El orden de las condiciones puede cambiar el resultado del programa. Por eso, conviene escribir primero los casos más específicos, más restrictivos o más altos, según la lógica del problema.
:::

## Un mismo dato, varios rangos

Una de las aplicaciones más frecuentes de `elif` consiste en comparar un mismo dato con distintos tramos o rangos.

~~~python
temperatura = 12

if temperatura < 10:
    print("Hace mucho frío")
elif temperatura < 20:
    print("La temperatura es templada")
elif temperatura < 30:
    print("Hace calor")
~~~

Aquí todas las condiciones se construyen sobre el mismo valor: `temperatura`. Sin embargo, no todas se interpretan de forma aislada. Cada una depende de que las anteriores no se hayan cumplido.

Esa es la razón por la que `temperatura < 20` no significa simplemente “cualquier temperatura menor que 20”, sino “una temperatura menor que 20 que no entró ya en el tramo anterior”.

Ese matiz hace que `elif` resulte muy útil para clasificar datos por intervalos, siempre que el orden de los casos esté bien pensado.

## Elegir mejor la estructura

Aunque `elif` es muy útil, no conviene usarlo por costumbre en cualquier situación. Su valor aparece cuando varias condiciones forman parte de una misma decisión y solo uno de los resultados debe ejecutarse.

Por ejemplo:

- Si solo necesitas verificar una condición, basta con `if`
- Si necesitas evaluar varios caminos excluyentes, `elif` resulta apropiado
- Si necesitas comparar un mismo valor con muchos casos concretos, `match-case` puede ser una alternativa interesante

:::tip[Buena decisión]
Usa `elif` cuando varias condiciones pertenezcan a una misma clasificación o a una misma secuencia de alternativas.
:::

## Cuando la entrada cambia la decisión

En muchos programas, las condiciones no se aplican sobre valores escritos directamente en el código, sino sobre datos ingresados durante la ejecución.

~~~python
nota = float(input("Ingresa la nota final: "))

if nota >= 6.0:
    print("Rendimiento alto")
elif nota >= 4.0:
    print("Rendimiento satisfactorio")
elif nota >= 1.0:
    print("Rendimiento insuficiente")
~~~

Aquí el programa realiza varias tareas encadenadas:

1. Solicita una nota mediante `input()`
2. Convierte el dato a `float`
3. Evalúa las condiciones en orden
4. Ejecuta la acción correspondiente al primer caso verdadero

Si la estudiante ingresa `5.2`, el programa muestra:

~~~text
Rendimiento satisfactorio
~~~

Este ejemplo deja ver con claridad por qué `elif` resulta útil: permite distinguir entre varios escenarios posibles sin recurrir a decisiones separadas o anidadas innecesariamente.

:::caution[Conversión de datos]
Si el valor ingresado representa una cantidad numérica, conviene convertirlo antes de compararlo. `input()` devuelve texto.
:::

## No es lo mismo que anidar

Al comenzar, a veces se intenta resolver este tipo de problemas escribiendo varios `if` independientes o anidando estructuras sin necesidad. Sin embargo, cuando los casos son excluyentes y pertenecen a una misma clasificación, una secuencia con `if` y `elif` suele ser más clara.

La razón es que su lectura ya trae una lógica incorporada:

- Primero se revisa una posibilidad
- Si no corresponde, se revisa la siguiente
- Luego otra
- Y así sucesivamente

Esa progresión hace que la estructura sea más fácil de leer, explicar y corregir.

## Del concepto al código

Escribe un programa en Python que solicite la edad de una persona y muestre un mensaje según uno de estos casos:

- Si la edad es menor que `12`, mostrar `Eres niño/a.`
- Si la edad es menor que `18`, mostrar `Eres adolescente.`
- Si la edad es menor que `60`, mostrar `Eres adulto/a.`
- Si la edad es `60` o mayor, mostrar `Eres adulto/a mayor.`

El programa debe cumplir con los siguientes requisitos:

- Debe solicitar la edad usando `input()`
- Debe convertir el dato a `int`
- Debe usar `if`, `elif` y `else`
- Debe mostrar un solo resultado

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa tu edad: 15
Eres adoslecente.
~~~

:::tip[Antes de escribir el código]
Piensa primero en el orden de las condiciones. En ejercicios de clasificación, ese detalle suele ser más importante que la escritura misma de `elif`.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta `if`, `elif` y `else` de manera progresiva, con ejemplos y explicaciones orientadas al aprendizaje.

- [Referencia del lenguaje: sentencia `if`](https://docs.python.org/3/reference/compound_stmts.html#the-if-statement)  
  Describe con mayor precisión técnica cómo se define esta estructura dentro del lenguaje, incluyendo el uso de cláusulas `elif`.

- [Documentación oficial en español: más herramientas para control de flujo](https://docs.python.org/es/3/tutorial/controlflow.html)  
  Ofrece una versión accesible del tema en español, útil para reforzar la comprensión general de estas estructuras.