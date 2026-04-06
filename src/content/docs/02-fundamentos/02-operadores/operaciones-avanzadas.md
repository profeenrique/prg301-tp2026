---
title: Operaciones avanzadas
description: Combinación de operadores aritméticos, uso de paréntesis y evaluación de expresiones numéricas en Python.
slug: fundamentos/operadores/operaciones-avanzadas
sidebar:
  label: Operaciones avanzadas
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de conocer los operadores aritméticos básicos en Python, saber realizar sumas, restas, multiplicaciones y divisiones simples, y poder interpretar resultados numéricos en variables y expresiones.
:::

A medida que un programa resuelve problemas más interesantes, los cálculos dejan de ser operaciones aisladas. Ya no basta con sumar dos valores o multiplicar una cantidad por un precio. Muy pronto aparece la necesidad de combinar varias operaciones dentro de una misma expresión. En ese momento, no solo importan los números y los operadores: también importa el orden en que Python decide resolver el cálculo.

## Objetivo

Comprender cómo Python evalúa expresiones aritméticas con varias operaciones y aplicar paréntesis y agrupaciones para construir cálculos más claros y correctos.

## Cuando una cuenta tiene varios pasos

Una expresión aritmética puede reunir más de una operación en una misma línea. Cuando eso ocurre, el resultado no depende solo de los valores involucrados, sino también del orden en que Python resuelve cada parte.

Por ejemplo, no es lo mismo escribir:

~~~python
2 + 3 * 4
~~~

que escribir:

~~~python
(2 + 3) * 4
~~~

Aunque ambas expresiones usan los mismos números y operadores, no significan lo mismo. En una, la multiplicación ocurre antes que la suma; en la otra, los paréntesis obligan a sumar primero.

~~~python
print(2 + 3 * 4)
print((2 + 3) * 4)
~~~

En pantalla aparecen dos resultados distintos:

~~~text
14
20
~~~

Esta diferencia muestra una idea importante: en programación, una expresión no se interpreta solo por los símbolos que contiene, sino también por la forma en que esos símbolos están organizados.

## El orden también forma parte del cálculo

Cuando una expresión incluye varias operaciones, Python no las resuelve al azar ni simplemente de izquierda a derecha. El lenguaje sigue un orden de prioridad.

Esa prioridad puede resumirse así:

| Prioridad | Operación | Operadores |
| --- | --- | --- |
| 1 | Paréntesis | `()` |
| 2 | Potencia | `**` |
| 3 | Multiplicación, división, división entera y módulo | `*`, `/`, `//`, `%` |
| 4 | Suma y resta | `+`, `-` |

:::note[Idea clave]
Si una expresión tiene varios operadores, Python no resuelve todo en el orden en que aparece escrito. Primero respeta la prioridad de cada operación.
:::

Comprender esta jerarquía evita errores frecuentes y ayuda a leer mejor los cálculos. También permite anticipar el resultado sin necesidad de probar cada línea a ciegas.

## Qué cambian los paréntesis

Los paréntesis permiten indicar con claridad qué parte de una expresión debe resolverse primero. En otras palabras, permiten intervenir en el orden natural de evaluación.

~~~python
print((8 + 2) * 3)
print(8 + (2 * 3))
~~~

Estas dos expresiones no representan el mismo cálculo, aunque utilicen los mismos valores.

~~~text
30
14
~~~

En la primera, los paréntesis obligan a resolver primero `8 + 2`. En la segunda, la multiplicación ocurre antes porque ya tiene prioridad natural sobre la suma.

Los paréntesis no solo sirven para cambiar resultados. También cumplen una función importante en la lectura del código: ayudan a que una expresión sea más fácil de comprender, especialmente cuando el cálculo empieza a crecer.

## Una expresión también puede leerse

A veces un programa necesita realizar un cálculo compuesto a partir de varias variables. En esos casos, la expresión puede seguir siendo correcta, pero no siempre resulta igual de fácil de interpretar.

~~~python
precio = 1500
cantidad = 3
descuento = 500

total = precio * cantidad - descuento
print(total)
~~~

Aquí el programa calcula primero `precio * cantidad` y luego resta `descuento`. El resultado final es:

~~~text
4000
~~~

Este tipo de expresión ya muestra una idea importante de programación: el cálculo no depende de números escritos de forma aislada, sino de variables que representan partes del problema.

Sin embargo, también conviene notar algo más: una expresión correcta puede ser difícil de leer si no está bien organizada.

## Claridad y cálculo

Cuando una expresión se vuelve más larga, no basta con que funcione. También conviene que pueda leerse con facilidad.

~~~python
resultado = 10 + 5 * 2 - 4 / 2
~~~

Python puede resolver esta expresión sin problema, pero eso no significa que sea la mejor forma de escribirla. Si la idea matemática no se percibe con rapidez, conviene reorganizarla.

Una posibilidad es usar paréntesis para hacer más visible la estructura del cálculo:

~~~python
resultado = (10 + (5 * 2)) - (4 / 2)
print(resultado)
~~~

Otra posibilidad es dividir el cálculo en pasos intermedios:

~~~python
parte1 = 5 * 2
parte2 = 4 / 2
resultado = 10 + parte1 - parte2
print(resultado)
~~~

Ambas versiones pueden producir el mismo resultado, pero la segunda deja más clara la lógica del proceso. Esa claridad puede marcar una gran diferencia cuando el programa crece o cuando otra persona necesita leer el código.

:::tip[Buena práctica]
Si una expresión empieza a volverse difícil de leer, usa paréntesis o divide el cálculo en variables intermedias. Un programa claro resulta más fácil de revisar, explicar y corregir.
:::

## Potencia y prioridad

La potencia también puede formar parte de expresiones combinadas, y su presencia modifica el orden del cálculo.

~~~python
print(2 + 3 ** 2)
print((2 + 3) ** 2)
~~~

Estas dos expresiones producen resultados distintos:

~~~text
11
25
~~~

En la primera, Python resuelve primero `3 ** 2`, porque la potencia tiene prioridad sobre la suma. En la segunda, los paréntesis obligan a resolver primero `2 + 3`, y luego el resultado se eleva al cuadrado.

Este contraste muestra con claridad que los operadores no solo “hacen algo”, sino que interactúan entre sí dentro de una jerarquía. Por eso, al leer una expresión, conviene preguntarse no solo qué operaciones aparecen, sino en qué orden se resolverán.

## Pensar antes de escribir la expresión

Una parte importante de programar bien consiste en no escribir una operación solo porque “parece funcionar”. Antes de construir una expresión, conviene preguntarse:

- ¿Qué cálculo quiero representar?
- ¿Qué parte debe resolverse primero?
- ¿Conviene usar paréntesis para hacerlo explícito?
- ¿La expresión se entiende con facilidad al volver a leerla?

Estas preguntas ayudan a pasar de hacer cuentas “en código” a construir expresiones que realmente representen la lógica del problema.

## Del concepto al código

Escribe y prueba las siguientes expresiones:

1. `2 + 3 * 5`
2. `(2 + 3) * 5`
3. `10 - 4 / 2`
4. `(10 - 4) / 2`
5. `2 ** 3 + 1`
6. `(2 + 3) ** 2`

Luego responde:

- ¿En qué casos cambió el resultado?
- ¿Qué efecto tuvieron los paréntesis?
- ¿Qué expresión te pareció más fácil de leer?
- ¿En cuál se entiende mejor la intención del cálculo?

Si quieres, puedes usar este punto de partida para probarlas todas en un mismo archivo:

~~~python
print(2 + 3 * 5)
print((2 + 3) * 5)

print(10 - 4 / 2)
print((10 - 4) / 2)

print(2 ** 3 + 1)
print((2 + 3) ** 2)
~~~

:::caution[Error frecuente]
Un error frecuente es asumir que las operaciones se resuelven siempre de izquierda a derecha. En Python, el orden depende de la prioridad de los operadores y del uso de paréntesis. También es habitual escribir expresiones demasiado largas sin agrupar ni separar partes del cálculo.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta operaciones numéricas y ejemplos básicos de evaluación de expresiones.

- [Biblioteca estándar: tipos numéricos](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)  
  Describe cómo se comportan los tipos numéricos en Python.

- [Referencia del lenguaje: expresiones](https://docs.python.org/3/reference/expressions.html)  
  Explica con mayor precisión técnica cómo se interpretan los operadores y el orden de evaluación de las expresiones.