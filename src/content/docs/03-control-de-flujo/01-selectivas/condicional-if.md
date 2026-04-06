---
title: Condicional if
description: Evaluación de condiciones en Python mediante la estructura if.
slug: control-de-flujo/selectivas/condicional-if
sidebar:
  label: Condicional if
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que sabes trabajar con variables, puedes usar `input()` para capturar datos, comprendes la conversión básica con `int()` y `float()`, y sabes usar `print()` para mostrar información en pantalla. 
:::

Un programa no siempre debe hacer lo mismo en todas las situaciones. A veces necesita actuar solo si se cumple cierta condición: mostrar un mensaje, permitir el acceso, validar un dato o ejecutar un cálculo únicamente cuando corresponde. Esa capacidad de **tomar decisiones durante la ejecución** es una de las ideas que vuelve útil a la programación. En Python, una de las formas más directas de expresar esa lógica es mediante la estructura `if`.

## Objetivo

Comprender cómo la estructura `if` permite evaluar una condición y ejecutar instrucciones solo cuando esa condición resulta verdadera.

## Cuando el programa debe decidir

Hasta este punto, es probable que hayas trabajado con programas donde las instrucciones se ejecutan una tras otra, en el orden en que fueron escritas. Ese comportamiento corresponde a un flujo secuencial. Sin embargo, muchos problemas no pueden resolverse únicamente siguiendo una secuencia fija de pasos.

Piensa en situaciones como estas:

- Mostrar un mensaje solo si la asistencia es perfecta
- Permitir el acceso únicamente si la edad cumple un mínimo
- Indicar aprobación solo cuando la nota alcanza el valor requerido
- Validar un dato solo si su contenido cumple cierta regla

En todos estos casos, el programa necesita evaluar una situación antes de actuar. No basta con ejecutar instrucciones de forma lineal, sino que es necesario incorporar una verificación que determine si se debe o no ejecutar cierto bloque de código.

## La idea detrás de `if`

La estructura `if` permite indicar que un bloque de instrucciones debe ejecutarse solo cuando se cumple una condición.

~~~python
if condicion:
    instruccion_1
    instruccion_2
~~~

Esta forma breve concentra una idea muy importante de la programación: no toda instrucción debe ejecutarse siempre. Algunas acciones dependen del resultado de una verificación previa.

En esta estructura conviene distinguir tres partes:

- `if` es una palabra reservada del lenguaje
- `condicion` es una expresión que Python puede evaluar
- El bloque indentado contiene las instrucciones que solo se ejecutan si la condición es verdadera

:::note[Idea clave]
La estructura `if` no pregunta “qué valor tiene este dato”, sino “¿se cumple esta condición?”. Solo si la respuesta es afirmativa, el bloque se ejecuta.
:::

## Cómo cambia el flujo

Una forma útil de comprender `if` es pensar que introduce una bifurcación en el recorrido del programa. A partir de ese punto, el código ya no sigue una única ruta obligatoria, sino que puede ejecutar o no cierto bloque según el resultado de la condición.

~~~mermaid
flowchart TD
    A[Programa en ejecución] --> B{¿La condición se cumple?}
    B -->|Sí| C[Ejecutar bloque del if]
    B -->|No| D[Omitir bloque]
    C --> E[Continuar programa]
    D --> E
~~~

Este esquema resume la función central de `if`: incorporar una decisión dentro del flujo del programa sin interrumpir su continuidad.

## Cómo se lee una condición

Una condición es una expresión cuyo resultado puede interpretarse como verdadero o falso. En muchos casos, esa evaluación se construye mediante comparaciones.

~~~python
edad = 18

if edad >= 18:
    print("Cumple el requisito de edad.")
~~~

Aquí, Python evalúa la expresión `edad >= 18`. Esa comparación produce un valor booleano.

- Si el resultado es `True`, se ejecuta la instrucción indentada
- Si el resultado es `False`, esa instrucción se omite

Lo importante no es memorizar la sintaxis, sino aprender a leer la lógica de la condición. En este caso, la expresión puede leerse así: “si la edad es mayor o igual a 18, entonces muestra el mensaje”.

Esa forma de lectura ayuda mucho al construir condiciones más adelante, porque obliga a pensar primero en la regla y después en el código que la representa.

## Más allá de `True` y `False`

Aunque muchas condiciones se escriben a partir de comparaciones que producen `True` o `False`, Python también puede evaluar otros valores según su **valor de verdad**. Eso significa que ciertos datos se interpretan como verdaderos y otros como falsos cuando aparecen dentro de una condición.

| Expresión | Interpretación | Comentario |
| --- | --- | --- |
| `True` | Verdadera | Valor booleano explícito |
| `8 > 3` | Verdadera | La comparación produce `True` |
| `1` | Verdadera | Todo número distinto de `0` se interpreta como verdadero |
| `"Python"` | Verdadera | Una cadena con contenido se interpreta como verdadera |
| `False` | Falsa | Valor booleano explícito |
| `0` | Falsa | El valor `0` se interpreta como falso |
| `""` | Falsa | Una cadena vacía se interpreta como falsa |
| `[]` | Falsa | Una lista vacía se interpreta como falsa |

Este punto es especialmente importante porque muestra que una condición no se limita a las palabras `True` y `False`. Python puede evaluar expresiones, números, cadenas y otros valores según su comportamiento lógico.

:::tip[Lectura útil]
Pensar en el valor de verdad de una expresión ayuda a escribir condiciones con más precisión y también a entender mejor por qué un bloque se ejecuta o no.
:::

## La indentación delimita el bloque

Una de las características más distintivas de Python es que la indentación no cumple solo una función visual. También define la estructura del programa.

~~~python
temperatura = 31

if temperatura > 30:
    print("Hace calor.")
    print("Recuerda hidratarte.")

print("Fin del programa.")
~~~

En este fragmento, las dos instrucciones indentadas pertenecen al bloque del `if`. En cambio, `print("Fin del programa.")` queda fuera de la condición, por lo que se ejecuta siempre.

Esto significa que la sangría no se usa solo para “ordenar bonito” el código. Sirve para delimitar con claridad qué instrucciones dependen de la condición y cuáles continúan después de ella.

:::caution[Atención con la escritura]
En Python, la indentación forma parte de la sintaxis del lenguaje. Si el bloque del `if` no está correctamente indentado, el programa producirá un error o no se comportará como esperas.
:::

## Una decisión concreta

Supongamos que se desea informar si una estudiante tiene asistencia perfecta.

~~~python
asistencia = 100

if asistencia == 100:
    print("Cumples con asistencia perfecta.")
~~~

Aquí el programa compara el valor almacenado en `asistencia` con `100`. Si ambos valores coinciden, la condición se cumple y el mensaje se muestra en pantalla.

~~~text
Cumples con asistencia perfecta.
~~~

Este ejemplo permite ver con claridad la lógica de `if`: la acción no ocurre siempre, sino solo cuando la verificación resulta verdadera.

## Cuando la condición depende de la entrada

En muchos programas, la condición no se construye con un valor fijo escrito directamente en el código, sino con un dato proporcionado durante la ejecución.

~~~python
edad = int(input("Ingresa tu edad: "))

if edad >= 12:
    print("Puedes ingresar a la actividad.")
~~~

Aquí ocurre una secuencia muy representativa de la programación básica:

1. El programa solicita un dato mediante `input()`
2. El dato ingresado se convierte a entero con `int()`
3. Se evalúa una condición sobre ese valor
4. Si la condición se cumple, se ejecuta la acción correspondiente

Esta estructura aparece una y otra vez en programas reales: pedir información, interpretarla y decidir qué hacer con ella.

:::caution[Conversión de datos]
`input()` devuelve texto. Si necesitas comparar cantidades numéricas, primero debes convertir el dato con `int()` o `float()`, según corresponda.
:::

## Pensar antes de escribir la condición

Al comenzar, es común concentrarse demasiado en la sintaxis y olvidar la parte más importante: la lógica que la condición representa. Antes de escribir un `if`, conviene preguntarse:

- ¿Qué situación quiero comprobar?
- ¿Qué dato participa en esa decisión?
- ¿Qué debe ocurrir si la condición se cumple?
- ¿Qué parte del programa depende realmente de esa verificación?

Estas preguntas ayudan a evitar condiciones confusas o mal planteadas. En el fondo, escribir un `if` no consiste solo en usar una estructura del lenguaje, sino en traducir una regla del problema a una forma que Python pueda evaluar.

## Del concepto al código

Escribe un programa en Python que solicite la nota final de una estudiante e informe si está aprobada, considerando que la aprobación se obtiene con nota mayor o igual a `4.0`. 

El programa debe cumplir con los siguientes requisitos:

- Debe pedir la nota usando `input()`
- Debe convertir el dato a `float`
- Debe usar una estructura `if`
- Debe mostrar el mensaje solo cuando la condición se cumpla

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa la nota final: 4.5
La estudiante está aprobada.
~~~

:::tip[Antes de escribir el código]
Identifica con claridad cuál es la entrada, qué condición debe evaluarse y qué acción se ejecutará si esa condición resulta verdadera.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta la estructura `if` de manera progresiva, con ejemplos y explicaciones orientadas al aprendizaje.

- [Referencia del lenguaje: sentencia `if`](https://docs.python.org/3/reference/compound_stmts.html#the-if-statement)  
  Describe con mayor precisión técnica cómo se define esta estructura dentro del lenguaje.

- [Tipos integrados: truth value testing](https://docs.python.org/3/library/stdtypes.html#truth-value-testing)  
  Explica por qué ciertos valores y expresiones se interpretan como verdaderos o falsos en una condición.