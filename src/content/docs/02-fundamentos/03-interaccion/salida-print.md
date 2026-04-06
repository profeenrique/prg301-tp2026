---
title: Salida con print()
description: Uso de la función print() para mostrar información en pantalla.
slug: fundamentos/interaccion/salida-print
sidebar:
  label: Salida con print()
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que sabes crear variables simples en Python, reconocer tipos de datos básicos y poder ejecutar archivos `.py` desde tu entorno de trabajo.
:::

Un programa no solo necesita calcular o almacenar información. También necesita **hacer visible lo que está ocurriendo**. Mostrar un mensaje, presentar un resultado, confirmar un dato o explicar una salida forma parte del diálogo entre el programa y quien lo ejecuta. En Python, una de las herramientas más importantes para comenzar ese diálogo es `print()`.

## Objetivo

Comprender cómo utilizar `print()` para mostrar información en pantalla y construir salidas claras a partir de textos, números, variables y expresiones.

## Hacer visible un resultado

Cuando un programa se ejecuta, muchas veces produce información que debe verse en pantalla. Esa información puede ser muy simple o bastante elaborada. Por ejemplo, el programa puede mostrar:

- Un saludo
- Un número
- El contenido de una variable
- El resultado de una operación
- Un mensaje que combine texto y datos

En Python, esa tarea se realiza con la función `print()`.

~~~python
print("Hola")
~~~

Al ejecutar esta instrucción, Python envía el texto `Hola` a la salida del programa, que normalmente corresponde a la terminal o la consola.

~~~mermaid
flowchart LR
    A["Valor o mensaje"] --> B["print()"]
    B --> C["Pantalla / consola"]
~~~

Esta idea es simple, pero muy importante: `print()` permite observar lo que el programa quiere comunicar en un momento determinado.

## Qué hace realmente `print()`

La función `print()` toma uno o más valores y los envía a la salida estándar. En la práctica, eso suele significar que el resultado aparece en pantalla.

Desde el punto de vista del aprendizaje, `print()` cumple varias funciones importantes:

- Permite mostrar información a quien usa el programa
- Ayuda a comprobar si una variable contiene el valor esperado
- Facilita observar resultados parciales durante una prueba
- Hace visible el comportamiento del código mientras se desarrolla

Por eso, `print()` no es solo una herramienta para “mostrar algo bonito”. También es una forma muy útil de **entender lo que está haciendo el programa**.

## Mostrar texto

Cuando quieres mostrar texto literal, debes escribirlo entre comillas.

~~~python
print("Bienvenida")
print("Python")
print("Este es un mensaje")
~~~

En cada caso, Python interpreta el contenido entre comillas como texto y lo muestra tal como fue escrito.

~~~text
Bienvenida
Python
Este es un mensaje
~~~

Aquí conviene recordar una diferencia importante: si el contenido es texto literal, debe escribirse entre comillas. Sin ellas, Python intentará interpretarlo como otra cosa, por ejemplo como el nombre de una variable.

## Mostrar números

`print()` también puede mostrar valores numéricos.

~~~python
print(10)
print(3.14)
~~~

En este caso, los números no necesitan comillas, porque no se están tratando como texto, sino como valores numéricos.

~~~text
10
3.14
~~~

Esta diferencia entre texto y número ya debería resultarte familiar: aunque ambos puedan aparecer en pantalla, Python no los interpreta del mismo modo.

## Mostrar el contenido de una variable

Una de las funciones más útiles de `print()` es mostrar el valor almacenado en una variable.

~~~python
nombre = "Ana"
edad = 18

print(nombre)
print(edad)
~~~

Aquí `print()` no muestra los nombres `nombre` y `edad`, sino los valores asociados a esas variables en ese momento.

~~~text
Ana
18
~~~

Este punto es importante porque permite comprobar qué información está manejando el programa en cada paso. En otras palabras, `print()` ayuda a volver visible el contenido interno del código.

## Mostrar el resultado de una expresión

`print()` también puede recibir expresiones. Eso significa que no solo muestra datos ya guardados, sino también resultados que Python calcula en el momento.

~~~python
print(5 + 3)
print(10 * 2)
~~~

En este caso, Python primero resuelve la operación y luego muestra el resultado.

~~~text
8
20
~~~

Esta posibilidad es muy útil al comenzar, porque permite probar rápidamente una expresión sin necesidad de guardarla antes en una variable.

## Combinar texto y variables

Muchas veces no basta con mostrar un dato aislado. También conviene acompañarlo con un mensaje que ayude a entender qué representa.

~~~python
nombre = "Luis"
edad = 17

print("Nombre:", nombre)
print("Edad:", edad)
~~~

Aquí `print()` recibe más de un elemento. Cada uno se separa con comas, y Python los muestra en una misma línea dejando un espacio entre ellos.

~~~text
Nombre: Luis
Edad: 17
~~~

Esta forma resulta especialmente útil cuando el programa necesita ofrecer salidas más informativas y no solo valores sueltos.

## Mostrar no siempre es explicar

Piensa en esta diferencia:

~~~python
nombre = "Sofía"

print(nombre)
print("Nombre de la estudiante:", nombre)
~~~

Ambas líneas son válidas, pero no comunican lo mismo.

En la primera, el programa muestra solo el valor almacenado. En la segunda, además entrega contexto sobre lo que se está viendo. Esa diferencia importa, porque una salida clara facilita la interpretación del resultado.

~~~text
Sofía
Nombre de la estudiante: Sofía
~~~

Aquí aparece una idea importante de programación: no basta con que el programa funcione; también conviene que su salida pueda leerse con facilidad.

:::tip[Buena práctica]
Cuando el programa muestre datos, procura acompañarlos con un mensaje claro si eso ayuda a entender el resultado.
:::

## Comas y f-strings

Python ofrece más de una forma de construir una salida con texto y variables. Dos de las más comunes en esta etapa son el uso de comas y las f-strings.

~~~python
nombre = "Sofía"

print("Nombre:", nombre)
print(f"Nombre: {nombre}")
~~~

En ambos casos, la salida puede ser equivalente.

~~~text
Nombre: Sofía
Nombre: Sofía
~~~

La diferencia está en la forma de escribir el mensaje. Con comas, `print()` recibe varios elementos separados. Con una f-string, el valor de la variable se inserta directamente dentro del texto.

Esto hace que las f-strings suelan resultar más legibles cuando la salida combina varias variables o expresiones.

:::tip[Buena práctica]
Cuando necesites construir mensajes con variables, considera usar f-strings. Suelen hacer la salida más clara y la escritura más natural.
:::

## Cada `print()` crea una nueva línea

Por defecto, cada llamada a `print()` produce una salida en una nueva línea.

~~~python
print("Primera línea")
print("Segunda línea")
print("Tercera línea")
~~~

Esto hace que Python presente cada instrucción de salida por separado.

~~~text
Primera línea
Segunda línea
Tercera línea
~~~

Este comportamiento ayuda a organizar mejor la salida, especialmente cuando el programa muestra varios mensajes seguidos.

## Un detalle que conviene notar

Hay una diferencia importante entre estas dos instrucciones:

~~~python
print(nombre)
print("nombre")
~~~

La primera muestra el valor almacenado en la variable `nombre`. La segunda muestra literalmente el texto `"nombre"`.

Esta distinción ya apareció antes al trabajar con variables, pero aquí vuelve a ser fundamental: `print()` muestra exactamente aquello que recibe, y Python interpreta de manera distinta una variable y un texto literal.

:::caution[Error frecuente]
Un error frecuente es olvidar las comillas al intentar mostrar un texto con `print()`. Si el contenido es texto literal, debe escribirse entre comillas. También es habitual pensar que `print(nombre)` y `print("nombre")` hacen lo mismo, cuando en realidad uno muestra el valor de una variable y el otro muestra un texto.
:::

## `print()` también ayuda a depurar

Además de comunicar resultados a quien usa el programa, `print()` es muy útil durante el desarrollo. Mostrar temporalmente el valor de una variable o el resultado de una operación permite comprobar si el programa está avanzando como se espera.

Por eso, al comenzar a programar, `print()` no solo sirve para construir salidas finales. También funciona como una herramienta de observación: ayuda a mirar el comportamiento del código mientras se está escribiendo y corrigiendo.

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Muestre un saludo en pantalla
2. Muestre un número entero
3. Cree una variable con tu nombre y la muestre
4. Muestre el resultado de una suma
5. Combine texto y una variable en una misma salida

Puedes tomar como punto de partida un ejemplo como este:

~~~python
print("Hola")

print(10)

nombre = "Camila"
print(nombre)

print(4 + 6)

print("Nombre de la estudiante:", nombre)
print(f"Nombre de la estudiante: {nombre}")
~~~

Al probar este fragmento, conviene fijarse en estas ideas:

- `print()` puede mostrar textos, números, variables y expresiones
- La salida cambia según el tipo de valor que recibe
- Un mensaje claro ayuda a interpretar mejor lo que el programa está mostrando

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta ejemplos básicos de salida, expresiones y uso inicial del lenguaje.

- [Biblioteca estándar: función `print()`](https://docs.python.org/3/library/functions.html#print)  
  Describe con mayor precisión técnica cómo funciona `print()` y qué argumentos acepta.

- [Tutorial oficial de Python: entrada y salida](https://docs.python.org/3/tutorial/inputoutput.html)  
  Explica distintas formas de presentar información, incluyendo el uso de f-strings.