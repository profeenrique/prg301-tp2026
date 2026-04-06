---
title: Bucle for
description: Recorrido de secuencias en Python mediante la estructura for.
slug: control-de-flujo/repetitivas/bucle-for
sidebar:
  label: Bucle for
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que comprendes la idea de repetición en programación, sabes trabajar con variables y reconoces la importancia de la indentación en Python.
:::

No todas las repeticiones responden a la misma lógica. A veces un programa debe seguir ejecutando un bloque mientras una condición continúe siendo verdadera. En otras ocasiones, en cambio, necesita recorrer elementos que ya existen: los caracteres de una palabra, los valores de una lista o una secuencia de números. Cuando el problema tiene esa forma, el bucle `for` ofrece una manera especialmente clara de expresarlo.

## Objetivo

Comprender cómo la estructura `for` permite recorrer secuencias en Python y aplicar una misma acción a cada uno de sus elementos de forma ordenada y legible.

## Recorrer en lugar de repetir

La idea central de `for` no es simplemente “hacer algo varias veces”, sino **hacer algo con cada elemento de una secuencia**.

Esa diferencia es importante. Un `while` suele depender de una condición que cambia durante la ejecución. Un `for`, en cambio, trabaja sobre un conjunto de valores que ya puede recorrerse: una lista, una cadena de texto o una secuencia generada por `range()`.

La forma general es esta:

~~~python
for elemento in secuencia:
    instruccion_1
    instruccion_2
~~~

En esta estructura conviene reconocer tres partes:

- `for` es la palabra reservada que inicia el ciclo
- `elemento` es la variable que toma cada valor del recorrido
- `secuencia` representa el conjunto de datos que se va a recorrer

:::note[Idea clave]
Un `for` recorre una secuencia elemento por elemento. En cada vuelta, la variable del ciclo toma un nuevo valor y el bloque se ejecuta una vez más.
:::

## Cómo avanza el ciclo

Una de las ventajas de `for` es que no obliga a controlar manualmente el avance del recorrido. Python se encarga de tomar cada elemento en orden y de ejecutar el bloque correspondiente.

~~~mermaid
flowchart TD
    A[Inicio] --> B[Tomar la secuencia]
    B --> C{¿Quedan elementos?}
    C -->|Sí| D[Asignar un elemento a la variable]
    D --> E[Ejecutar el bloque del for]
    E --> C
    C -->|No| F[Continuar con el programa]
~~~

Este esquema muestra una idea importante: con `for`, el recorrido ya viene resuelto por la propia estructura. El programa no necesita preguntar “¿cuánto falta?” ni actualizar un contador manualmente en cada vuelta, como ocurre con frecuencia en `while`.

:::caution[Atención con la escritura]
En Python, la indentación forma parte de la sintaxis. Si el bloque del `for` no está correctamente indentado, el programa producirá un error o no se comportará como esperas.
:::

## Un recorrido simple

Uno de los usos más frecuentes de `for` consiste en recorrer una lista y trabajar con cada uno de sus elementos.

~~~python
frutas = ["manzana", "pera", "uva"]

for fruta in frutas:
    print(fruta)
~~~

Aquí Python toma cada elemento de la lista `frutas` y lo asigna, uno por uno, a la variable `fruta`. Luego ejecuta el bloque indentado con ese valor.

En pantalla aparece esta secuencia:

~~~text
manzana
pera
uva
~~~

Este ejemplo conviene leerlo con calma. El programa no imprime la lista completa de una sola vez. Recorre sus elementos y en cada vuelta trabaja con uno distinto.

## Qué papel cumple cada parte

Para entender mejor un `for`, conviene observar qué función cumple cada componente de la estructura.

| Parte | Función | Ejemplo |
| --- | --- | --- |
| Variable de recorrido | Guarda temporalmente el elemento actual | `fruta` |
| Secuencia | Entrega los valores que se recorrerán | `frutas` |
| Bloque indentado | Contiene la acción que se repite en cada vuelta | `print(fruta)` |

Mirado de esta manera, el ciclo se vuelve más fácil de leer: `for` toma un elemento, lo asigna a una variable, ejecuta una acción y luego continúa con el siguiente.

## Repetir con `range()`

En muchos casos no se desea recorrer una lista o una palabra, sino repetir una acción una cantidad determinada de veces. Para eso, Python ofrece la función `range()`.

~~~python
for numero in range(5):
    print(numero)
~~~

En este caso, `range(5)` genera una secuencia de números que comienza en `0` y termina justo antes de `5`.

Por eso, en pantalla aparece:

~~~text
0
1
2
3
4
~~~

Este detalle suele sorprender al comienzo, porque muchas personas esperan que el `5` también aparezca. Sin embargo, `range(5)` no incluye el valor final indicado.

:::tip[Un detalle importante]
En `range(5)`, el valor `5` no se incluye. El recorrido llega hasta `4`.
:::

## Más de una forma de usar `range()`

`range()` puede utilizarse de distintas maneras según el recorrido que se necesite.

### Solo valor final

~~~python
for numero in range(5):
    print(numero)
~~~

Aquí el recorrido comienza en `0` y avanza de uno en uno hasta antes de `5`.

### Inicio y fin

~~~python
for numero in range(1, 6):
    print(numero)
~~~

Ahora el recorrido comienza en `1` y termina antes de `6`.

~~~text
1
2
3
4
5
~~~

### Con salto

También es posible indicar un tercer valor para controlar el paso del recorrido.

~~~python
for numero in range(0, 10, 2):
    print(numero)
~~~

En este caso, el ciclo avanza de dos en dos:

~~~text
0
2
4
6
8
~~~

Esto amplía bastante las posibilidades de `for`, porque permite construir recorridos numéricos más variados sin necesidad de manejar manualmente una variable de control.

## Un texto, carácter por carácter

El bucle `for` no solo recorre listas o secuencias numéricas. También puede recorrer texto.

~~~python
palabra = "Python"

for letra in palabra:
    print(letra)
~~~

Aquí Python toma cada carácter de la cadena `"Python"` y lo asigna sucesivamente a la variable `letra`.

La salida queda así:

~~~text
P
y
t
h
o
n
~~~

Este ejemplo es especialmente útil porque ayuda a comprender que una cadena también puede verse como una secuencia. Es decir, no solo es un bloque de texto completo, sino un conjunto de caracteres que el programa puede recorrer uno a uno.

## Cuando la cantidad depende de la entrada

En muchos programas, la cantidad de repeticiones depende de un valor ingresado por la persona usuaria.

~~~python
veces = int(input("¿Cuántas veces deseas saludar? "))

for _ in range(veces):
    print("Hola")
~~~

Aquí el programa solicita un número, lo convierte a entero y luego usa ese valor para controlar cuántas veces se repetirá el saludo.

Este patrón resulta muy común: la entrada define el tamaño del recorrido y `for` se encarga de ejecutarlo.

:::note[Sobre el guion bajo]
La variable `_` suele utilizarse cuando el valor del recorrido no se necesita dentro del bloque, pero igualmente se requiere repetir la acción.
:::

:::caution[Conversión de datos]
`input()` devuelve texto. Si el valor ingresado se utilizará con `range()`, primero debe convertirse a `int`.
:::

## Pensar el problema con `for`

Antes de escribir un `for`, conviene preguntarse:

- ¿Qué secuencia voy a recorrer?
- ¿Qué representa cada elemento del recorrido?
- ¿Qué acción debe repetirse en cada vuelta?
- ¿Necesito realmente el valor actual o solo repetir una cantidad de veces?

Estas preguntas ayudan a construir ciclos más claros y también a elegir mejor entre `for` y `while`.

## Cuándo conviene usarlo

El bucle `for` suele ser una buena elección cuando el programa necesita recorrer elementos o repetir una acción un número conocido de veces.

Suele ser apropiado cuando:

- se desea recorrer una lista
- se necesita trabajar con cada carácter de una palabra
- se quiere repetir una acción una cantidad definida de veces
- el recorrido ya está determinado desde el comienzo

Si, en cambio, la repetición depende de una condición que cambia durante la ejecución y no de una secuencia ya dada, `while` suele resultar más adecuado.

:::tip[Lectura útil]
Piensa `for` de esta manera: “haz algo con cada elemento” o “repite esto siguiendo una secuencia ya definida”.
:::

## Del concepto al código

Escribe un programa en Python que solicite una palabra al usuario y luego muestre cada una de sus letras en una línea distinta.

El programa debe cumplir con los siguientes requisitos:

- Debe pedir una palabra usando `input()`
- Debe usar un bucle `for`
- Debe recorrer la palabra carácter por carácter
- Debe mostrar una letra por línea

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa una palabra: gato
g
a
t
o
~~~

:::tip[Antes de escribir el código]
Identifica primero qué dato vas a recorrer y qué variable representará cada elemento durante el ciclo.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta la estructura `for` con ejemplos progresivos y explica su relación con `range()`.

- [Referencia del lenguaje: sentencia `for`](https://docs.python.org/3/reference/compound_stmts.html#the-for-statement)  
  Describe con mayor precisión técnica cómo se define `for` dentro del lenguaje.

- [Tipos integrados: `range`](https://docs.python.org/3/library/stdtypes.html#range)  
  Explica cómo funciona `range()` y por qué resulta útil en recorridos numéricos.