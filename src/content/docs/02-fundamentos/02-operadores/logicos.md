---
title: Lógicos
description: Operadores lógicos en Python para combinar comparaciones y construir expresiones booleanas.
slug: fundamentos/operadores/logicos
sidebar:
  label: Lógicos
  order: 4
---

:::note[Verificación previa]
Antes de continuar, asegúrate de conocer los operadores de comparación, saber que una comparación produce `True` o `False`, y poder interpretar expresiones simples con variables.
:::

En muchos problemas, comparar una sola vez no basta. Un programa puede necesitar comprobar si **dos condiciones se cumplen al mismo tiempo**, si **al menos una** de varias alternativas es válida, o si una condición debe interpretarse al revés. En ese punto, las comparaciones simples dejan de ser suficientes y aparece una nueva herramienta: los operadores lógicos.

## Objetivo

Comprender cómo los operadores lógicos permiten combinar comparaciones en Python para construir condiciones más precisas y expresivas dentro de un programa.

## Cuando una sola condición no alcanza

Hasta este punto, una comparación podía responder preguntas como estas:

- ¿La edad es mayor que 18?
- ¿Dos valores son iguales?
- ¿Una cantidad es menor que otra?

Sin embargo, muchos problemas reales no se resuelven con una sola pregunta. A veces el programa necesita evaluar relaciones como estas:

- Una persona es mayor de edad **y** además tiene autorización
- Una clave es correcta **o** existe un código alternativo
- Una condición **no** se cumple

En esos casos, el programa necesita combinar resultados booleanos para construir una condición más completa. Esa es la función de los operadores lógicos.

## Tres operadores fundamentales

Python trabaja, en esta etapa, con tres operadores lógicos principales.

| Operador | Lectura habitual | Función |
| --- | --- | --- |
| `and` | y | Devuelve `True` solo si ambas condiciones son verdaderas |
| `or` | o | Devuelve `True` si al menos una condición es verdadera |
| `not` | no | Invierte el valor lógico de una expresión |

Estos operadores no producen resultados numéricos. Trabajan sobre valores booleanos y también producen un valor booleano.

~~~python
print(True and True)
print(True and False)
print(True or False)
print(not True)
~~~

Al ejecutar este fragmento, Python entrega cuatro respuestas lógicas:

~~~text
True
False
True
False
~~~

Esto permite advertir una idea importante: los operadores lógicos no comparan cantidades por sí mismos, sino que **combinan o transforman resultados lógicos**.

:::note[Idea clave]
Los operadores lógicos permiten construir condiciones más complejas a partir de resultados booleanos como `True` y `False`.
:::

## `and`: cuando todo debe cumplirse

El operador `and` se utiliza cuando dos condiciones deben ser verdaderas al mismo tiempo.

~~~python
edad = 20
print(edad >= 18 and edad < 60)
~~~

Aquí el programa no formula una sola pregunta, sino dos:

- ¿`edad >= 18`?
- ¿`edad < 60`?

Como ambas respuestas son `True`, la expresión completa también resulta verdadera.

~~~text
True
~~~

Este operador es útil cuando una condición depende de más de un requisito. Por ejemplo, cuando una persona debe cumplir una edad mínima y además no superar cierto límite, o cuando una acción solo puede ejecutarse si dos verificaciones se cumplen de forma simultánea.

## `or`: cuando basta una posibilidad

El operador `or` se utiliza cuando no es necesario que todas las condiciones se cumplan. Basta con que al menos una sea verdadera.

~~~python
nota = 3.5
recuperacion = True

print(nota >= 4.0 or recuperacion)
~~~

En este caso, la primera comparación resulta falsa, porque `3.5` no es mayor ni igual que `4.0`. Sin embargo, `recuperacion` contiene `True`.

Como una de las dos partes de la expresión es verdadera, el resultado completo también es verdadero.

~~~text
True
~~~

Este operador aparece con frecuencia cuando un programa debe aceptar más de una posibilidad válida. Por ejemplo, una persona puede acceder con su contraseña habitual **o** con un código temporal.

## `not`: cambiar el sentido

El operador `not` invierte el valor lógico de una expresión.

~~~python
activo = True
print(not activo)
~~~

Aquí, Python toma el valor de `activo` y lo invierte.

~~~text
False
~~~

La idea puede resumirse así:

- si el valor original es `True`, `not` lo transforma en `False`
- si el valor original es `False`, `not` lo transforma en `True`

Este operador resulta útil cuando se necesita trabajar con la negación de una condición. En lugar de preguntar si algo se cumple, el programa pregunta si **no** se cumple.

## Ver cómo cambian los resultados

Una forma útil de estudiar operadores lógicos es observar cómo cambia el resultado según los valores de entrada. Las tablas de verdad ayudan precisamente a eso: muestran, de manera resumida, qué ocurre en cada caso posible.

Para `and`, el resultado solo es verdadero cuando ambas condiciones también lo son.

| A | B | A and B |
| --- | --- | --- |
| `True` | `True` | `True` |
| `True` | `False` | `False` |
| `False` | `True` | `False` |
| `False` | `False` | `False` |

Para `or`, basta con que una de las condiciones sea verdadera.

| A | B | A or B |
| --- | --- | --- |
| `True` | `True` | `True` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

En el caso de `not`, la lógica es más simple, porque trabaja sobre una sola expresión y la invierte.

| A | not A |
| --- | --- |
| `True` | `False` |
| `False` | `True` |

Estas tablas no están para memorizarse de forma mecánica. Sirven para comprender el comportamiento de cada operador y anticipar mejor lo que ocurrirá al escribir una condición.

## Comparaciones que se combinan

En programación, los operadores lógicos casi siempre aparecen junto con operadores de comparación. Esa combinación permite construir condiciones más cercanas a situaciones reales.

~~~python
edad = 17
permiso = True

print(edad >= 18 and permiso)
print(edad >= 18 or permiso)
~~~

La primera expresión exige que ambas partes sean verdaderas. Como `edad >= 18` resulta falsa, el resultado completo es `False`.

La segunda expresión, en cambio, usa `or`. En ese caso basta con que una parte sea verdadera, y como `permiso` vale `True`, el resultado final cambia.

~~~text
False
True
~~~

Este ejemplo muestra con claridad que el operador lógico modifica el sentido completo de la condición.

## Leer bien una condición lógica

Cuando una expresión lógica aparece en el código, conviene leerla como una frase completa.

Por ejemplo:

- `edad >= 18 and permiso` puede leerse como “la edad es mayor o igual a 18 y además existe permiso”
- `nota >= 4.0 or recuperacion` puede leerse como “la nota alcanza el mínimo o existe recuperación”
- `not activo` puede leerse como “no está activo”

Esta forma de lectura ayuda a comprender mejor el código y reduce errores al escribir condiciones más largas.

## Cuando los paréntesis aclaran

A medida que una condición lógica se vuelve más extensa, puede resultar más difícil leerla de un vistazo. En esos casos, los paréntesis ayudan a organizar la expresión y a mostrar con más claridad cómo está construida.

~~~python
edad = 25
estudiante = False

print((edad >= 18 and edad < 30) or estudiante)
~~~

Aquí los paréntesis agrupan una parte de la condición y permiten verla como una unidad: primero se evalúa si la edad está dentro de cierto rango, y luego se combina ese resultado con `estudiante`.

~~~text
True
~~~

Aunque Python puede evaluar muchas expresiones sin paréntesis, agrupar partes de la condición mejora bastante la legibilidad.

:::tip[Buena práctica]
Si una expresión lógica empieza a verse confusa, usa paréntesis para separar con claridad sus partes y hacer más visible la intención de la condición.
:::

## Cuando una palabra cambia todo

Una de las dificultades más comunes al comenzar es pensar que `and` y `or` cumplen funciones parecidas, cuando en realidad producen resultados muy distintos.

La diferencia puede resumirse así:

- `and` restringe la condición
- `or` amplía las posibilidades
- `not` invierte el resultado

Por eso, cambiar una sola palabra lógica puede modificar por completo el comportamiento de una expresión. Esta es una de las razones por las que conviene leer las condiciones con calma y no solo “reconocer” los símbolos rápidamente.

:::caution[Error frecuente]
Un error frecuente es confundir `and` con `or`. El primero exige que ambas condiciones se cumplan, mientras que el segundo permite que solo una sea verdadera. También es frecuente olvidar que `not` invierte el valor lógico de una variable o de una expresión completa.
:::

## Del concepto al código

Escribe y prueba las siguientes expresiones:

1. `True and False`
2. `True or False`
3. `not True`
4. `5 > 3 and 2 < 1`
5. `8 == 8 or 4 > 10`
6. `not (6 < 2)`

Luego trabaja con variables:

1. Crea una variable `edad` con valor `16`
2. Crea una variable `autorizacion` con valor `True`
3. Evalúa `edad >= 18 and autorizacion`
4. Evalúa `edad >= 18 or autorizacion`

Puedes tomar como referencia un fragmento como este:

~~~python
print(True and False)
print(True or False)
print(not True)

print(5 > 3 and 2 < 1)
print(8 == 8 or 4 > 10)
print(not (6 < 2))

edad = 16
autorizacion = True

print(edad >= 18 and autorizacion)
print(edad >= 18 or autorizacion)
~~~

Al realizar esta actividad, conviene prestar atención a estas ideas:

- Los operadores lógicos no reemplazan a las comparaciones: las combinan
- `and`, `or` y `not` no producen el mismo efecto
- Una pequeña diferencia en la expresión puede cambiar el resultado completo

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta expresiones booleanas y operadores en un contexto progresivo y formativo.

- [Tipos integrados de Python](https://docs.python.org/3/library/stdtypes.html#boolean-type-bool)  
  Describe el tipo `bool` y el comportamiento general de los valores lógicos en Python.

- [Referencia del lenguaje: expresiones](https://docs.python.org/3/reference/expressions.html)  
  Explica con mayor precisión técnica cómo Python interpreta operadores, precedencia y expresiones booleanas.