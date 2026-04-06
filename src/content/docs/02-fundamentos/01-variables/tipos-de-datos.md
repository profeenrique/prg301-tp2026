---
title: Tipos de datos
description: Tipos de datos básicos en Python y su uso en variables simples.
slug: fundamentos/variables/tipos-de-datos
sidebar:
  label: Tipos de datos
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de comprender qué son los tipos de datos básicos en Python y cómo permiten representar información de distinta naturaleza dentro de un programa.
:::

Cuando un programa trabaja con información, no todos los datos cumplen la misma función. A veces necesita guardar una cantidad entera, otras veces un número con decimales, una palabra o una respuesta lógica. Distinguir esas diferencias es parte esencial de programar, porque el tipo de dato influye en la forma en que Python interpreta un valor y en las operaciones que pueden realizarse con él.

## Objetivo

Comprender qué son los tipos de datos básicos en Python y cómo permiten representar información de distinta naturaleza dentro de un programa.

## Qué expresa un tipo

Cada vez que una variable almacena un valor, Python necesita saber de qué clase de valor se trata. No es lo mismo guardar un número entero que un texto, ni un número decimal que una respuesta lógica. Esa diferencia se expresa mediante el **tipo de dato**.

Dicho de forma simple, el tipo de dato indica qué clase de información representa un valor.

Esta distinción no es un detalle menor. El tipo influye en cómo Python almacena el dato, cómo lo muestra y qué operaciones permite realizar con él. Por eso, reconocer tipos de datos no consiste solo en memorizar nombres como `int` o `str`, sino en empezar a pensar con mayor precisión qué información maneja un programa.

:::note[Idea clave]
El tipo de dato indica qué clase de valor se está utilizando y orienta la forma en que ese valor puede emplearse dentro del programa.
:::

## Cuatro tipos básicos

En esta etapa conviene concentrarse en cuatro tipos fundamentales del lenguaje:

| Tipo | Ejemplo | Qué representa |
| --- | --- | --- |
| `int` | `18` | Números enteros, sin parte decimal |
| `float` | `3.5` | Números con parte decimal |
| `str` | `"Hola"` | Texto o cadena de caracteres |
| `bool` | `True` | Valor lógico: verdadero o falso |

Esta clasificación ayuda a leer mejor el código. También permite comprender por qué dos valores que parecen parecidos pueden comportarse de manera distinta dentro de un programa.

Una forma simple de ver esto en acción es asignar valores de distinto tipo a varias variables:

~~~python
edad = 18
estatura = 1.72
nombre = "Ada"
activo = True
~~~

Aquí ocurre algo importante:

- `edad` contiene un valor de tipo `int`
- `estatura` contiene un valor de tipo `float`
- `nombre` contiene un valor de tipo `str`
- `activo` contiene un valor de tipo `bool`

Lo relevante no es solo identificar esos nombres, sino reconocer que Python no interpreta todos los valores de la misma manera. Para el lenguaje, `18`, `"18"` y `True` no representan el mismo tipo de información, aunque puedan aparecer en un mismo programa.

## Enteros

Los valores de tipo `int` representan números enteros, es decir, números sin parte decimal.

~~~python
cantidad = 5
anio = 2026
temperatura = -3
~~~

Este tipo de dato se utiliza cuando el valor no necesita fracciones ni decimales. Aparece con frecuencia en cantidades, edades, años, posiciones y conteos.

Cuando un problema requiere trabajar con unidades completas, `int` suele ser la opción más natural.

## Decimales

Los valores de tipo `float` representan números que incluyen parte decimal.

~~~python
precio = 19.99
promedio = 5.4
pi = 3.14
~~~

Este tipo de dato se utiliza cuando el valor puede tener fracciones o decimales, como ocurre en medidas, promedios, porcentajes o precios.

Aquí conviene notar una diferencia importante: aunque `5` y `5.0` puedan parecer cercanos, Python no los interpreta exactamente del mismo modo. El primero corresponde a un entero y el segundo a un decimal.

## Texto

Los valores de tipo `str` representan cadenas de texto. Para que Python reconozca un texto, este debe escribirse entre comillas simples (`'`) o dobles (`"`).

~~~python
nombre = "Ada"
mensaje = "Hola"
ciudad = "Santiago"
~~~

En este caso, el dato no se interpreta como un número ni como una condición lógica, sino como texto.

Esto significa que Python lo tratará como una secuencia de caracteres. Más adelante, esa idea será importante al trabajar con entrada de datos, concatenación, longitud de palabras y recorrido de cadenas.

## Valores lógicos

Los valores de tipo `bool` representan una condición lógica. Solo pueden tomar dos valores: `True` y `False`.

~~~python
encendido = True
aprobado = False
~~~

Este tipo de dato se utiliza cuando el programa necesita representar una decisión o una condición: si algo está encendido o apagado, si una persona aprueba o no, si una respuesta es correcta o incorrecta.

Aunque en esta etapa su uso pueda parecer más acotado, los valores lógicos serán fundamentales al trabajar con comparaciones, condiciones y estructuras de control.

:::caution[Error frecuente]
`True` y `False` no son textos. En Python, son valores lógicos y deben escribirse sin comillas y con mayúscula inicial.
:::

## Ver el tipo de un valor

Python permite consultar el tipo de un valor mediante la función `type()`. Esta función resulta útil para confirmar cómo está interpretando un dato el lenguaje.

~~~python
print(type(18))
print(type(3.5))
print(type("Hola"))
print(type(True))
~~~

En pantalla aparecen resultados como estos:

~~~text
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
~~~

Esta función es especialmente útil al comenzar, porque permite comprobar si un valor está siendo interpretado como número, texto o valor lógico. También ayuda a detectar errores cuando un programa no se comporta como se esperaba.

## Número o texto

Una de las confusiones más frecuentes al comenzar consiste en pensar que un número y un texto que “se ven igual” son lo mismo. Sin embargo, Python los interpreta de forma distinta.

~~~python
edad = 18
edad_texto = "18"
~~~

A simple vista, ambos valores podrían parecer equivalentes, pero no lo son.

- `18` es un número entero
- `"18"` es un texto

Esa diferencia cambia la forma en que el programa puede usar cada dato. Un número puede participar directamente en cálculos aritméticos. Un texto, en cambio, se interpreta como una cadena de caracteres.

Comprender esta distinción es especialmente importante porque, más adelante, al trabajar con `input()`, los datos ingresados por el usuario se reciben inicialmente como texto.

:::caution[Error frecuente]
Si un valor está escrito entre comillas, Python lo interpreta como texto, aunque su contenido parezca numérico.
:::

## Leer una variable también implica leer su tipo

Cuando una variable aparece en un programa, no basta con mirar su nombre. También conviene pensar qué tipo de dato contiene, porque de eso depende la manera correcta de usarla.

Por ejemplo, no cumple la misma función una variable como esta:

~~~python
precio = 2500
~~~

que una como esta:

~~~python
precio = "2500"
~~~

En ambos casos el nombre es el mismo, pero el dato almacenado no tiene la misma naturaleza. En el primer fragmento, `precio` es un número entero. En el segundo, es un texto. Esa diferencia puede afectar cálculos, comparaciones y salidas del programa.

Pensar en tipos de datos, entonces, también ayuda a leer mejor lo que hace una variable dentro del código.

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Cree una variable con un número entero
2. Cree una variable con un número decimal
3. Cree una variable con un texto
4. Cree una variable con un valor lógico
5. Muestre cada variable en pantalla
6. Use `type()` para observar el tipo de cada una

Puedes tomar como punto de partida un ejemplo como este:

~~~python
edad = 16
promedio = 5.8
nombre = "Camila"
aprobado = True

print(edad)
print(type(edad))

print(promedio)
print(type(promedio))

print(nombre)
print(type(nombre))

print(aprobado)
print(type(aprobado))
~~~

Al probar este fragmento, conviene fijarse en tres ideas:

- No todos los valores representan la misma clase de información
- Python distingue esos valores según su tipo
- El tipo de dato influye en cómo el programa interpreta lo que almacena

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta variables, números, cadenas y operaciones básicas en un contexto progresivo y formativo.

- [Biblioteca estándar: función `type()`](https://docs.python.org/3/library/functions.html#type)  
  Explica cómo consultar el tipo de un objeto en Python.

- [Tipos integrados de Python](https://docs.python.org/3/library/stdtypes.html)  
  Describe con mayor precisión técnica los tipos básicos del lenguaje y su comportamiento general.