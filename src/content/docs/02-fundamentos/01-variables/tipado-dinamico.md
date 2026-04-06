---
title: Tipado dinámico
description: Forma en que Python asigna tipos a los valores sin requerir una declaración previa.
slug: fundamentos/variables/tipado-dinamico
sidebar:
  label: Tipado dinámico
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de reconocer qué es una variable, conocer los tipos de datos básicos en Python y saber asignar valores simples a una variable.
:::

En Python, una variable no necesita declarar por adelantado qué tipo de dato almacenará. El lenguaje identifica ese tipo automáticamente a partir del valor que se asigna en cada momento. Esa característica se conoce como **tipado dinámico** y forma parte de la manera en que Python simplifica la escritura de programas.

## Objetivo

Comprender cómo funciona el tipado dinámico en Python y analizar sus efectos al crear, reutilizar y actualizar variables dentro de un programa.

## Qué significa

En algunos lenguajes de programación, antes de usar una variable es necesario indicar explícitamente qué tipo de dato almacenará. En Python, eso no ocurre. El tipo se reconoce automáticamente cuando el valor es asignado.

~~~python
edad = 18
nombre = "Ana"
activo = True
~~~

En estas tres asignaciones, Python identifica por sí mismo que:

- `edad` contiene un entero
- `nombre` contiene un texto
- `activo` contiene un valor lógico

Lo importante aquí es notar que el programa no tuvo que declarar antes si la variable sería `int`, `str` o `bool`. El lenguaje lo determina a partir del valor entregado.

:::note[Idea clave]
En Python, el tipo no se declara antes de usar la variable. Se reconoce automáticamente en el momento de la asignación.
:::

## El tipo sigue al valor

Una de las ideas más importantes del tipado dinámico es esta: en Python, el tipo no queda fijado para siempre al nombre de la variable. Lo que ocurre, en realidad, es que la variable pasa a referirse a un valor, y ese valor tiene un tipo determinado.

~~~python
dato = 10
print(type(dato))
~~~

En este momento, `dato` se refiere a un entero. Pero si más adelante se asigna otro valor:

~~~python
dato = "Hola"
print(type(dato))
~~~

la misma variable pasa a referirse ahora a un texto.

~~~mermaid
flowchart LR
    A["dato"] --> B["10  -> int"]
    A -. nueva asignación .-> C["'Hola'  -> str"]
~~~

Este cambio muestra algo central: el nombre de la variable puede mantenerse, pero el tipo del valor asociado puede cambiar si la nueva asignación pertenece a otra clase de dato.

## Cuando el valor cambia, el tipo también

Una misma variable puede almacenar distintos tipos de valores en distintos momentos del programa.

~~~python
valor = 25
print(type(valor))

valor = 3.14
print(type(valor))

valor = "Python"
print(type(valor))
~~~

Al ejecutar este fragmento, Python va reconociendo el tipo del valor asignado en cada paso. Primero interpreta `25` como entero, luego `3.14` como decimal y finalmente `"Python"` como texto.

~~~text
<class 'int'>
<class 'float'>
<class 'str'>
~~~

Esta flexibilidad explica por qué se habla de tipado dinámico: el tipo no se fija de una vez para siempre al crear la variable, sino que puede variar según el valor que se le asigne más adelante.

## Por qué esta idea importa

El tipado dinámico hace que Python resulte más directo de escribir, especialmente en etapas iniciales de aprendizaje. No obliga a agregar declaraciones previas de tipo, por lo que permite concentrarse antes en la lógica del problema que en formalidades del lenguaje.

Esa flexibilidad, por ejemplo, facilita:

- Escribir código de manera más directa
- Probar ejemplos simples con rapidez
- Experimentar con valores distintos sin reescribir la definición de la variable

En un lenguaje como Python, esto favorece una forma de programar más ágil, especialmente en ejercicios cortos, pruebas y prototipos iniciales.

## Flexibilidad no significa desorden

Que Python permita cambiar el tipo de una variable no significa que convenga hacerlo sin una razón clara.

~~~python
dato = 10
dato = "Hola"
dato = True
~~~

Este código es válido, pero su lectura puede resultar confusa si el cambio de tipo no responde a una necesidad concreta del problema. En programas más largos, esa práctica puede volver el código más difícil de entender, revisar o corregir.

Por eso, una parte importante de programar bien no consiste solo en escribir código que funcione, sino también en mantener cierta coherencia en la forma de representar la información.

:::tip[Buena práctica]
Aunque Python permite cambiar el tipo de una variable, conviene mantener coherencia en los valores asignados y elegir nombres que ayuden a entender qué representa cada dato.
:::

## Cuando la flexibilidad produce errores

El tipado dinámico vuelve al lenguaje más flexible, pero también exige atención. Si una variable contiene un tipo distinto del que el programa esperaba, pueden aparecer errores o resultados no deseados.

~~~python
dato = "10"
print(dato + 5)
~~~

Aquí el problema no está en el nombre de la variable, sino en el tipo del valor almacenado. `"10"` es un texto y `5` es un número entero. Python no puede sumarlos directamente porque pertenecen a categorías distintas.

~~~text
TypeError: can only concatenate str (not "int") to str
~~~

Este ejemplo ayuda a comprender que el tipado dinámico no elimina la necesidad de pensar con precisión. La flexibilidad del lenguaje no reemplaza la responsabilidad de distinguir qué tipo de dato está circulando por el programa.

## Comprobar el tipo con `type()`

La función `type()` permite consultar el tipo del valor que una variable contiene en un momento determinado.

~~~python
dato = 8
print(type(dato))

dato = "ocho"
print(type(dato))
~~~

En la primera llamada, Python informa que el valor es un entero. En la segunda, informa que ahora se trata de un texto.

~~~text
<class 'int'>
<class 'str'>
~~~

Esta función resulta especialmente útil al comenzar, porque permite confirmar cómo está interpretando Python un valor y ayuda a detectar errores cuando una variable no contiene lo que se pensaba.

## Una forma útil de leer una variable

Al trabajar con variables, no basta con mirar el nombre. También conviene preguntarse qué tipo de valor contiene en ese momento.

Por ejemplo, una variable llamada `dato` podría almacenar:

- Un entero
- Un texto
- Un valor lógico

El nombre, por sí solo, no resuelve esa diferencia. Por eso, al leer o escribir código, es importante considerar no solo cómo se llama una variable, sino también qué tipo de información está representando realmente.

Esa costumbre mejora mucho la comprensión del programa y prepara mejor el trabajo con operaciones, conversiones y validaciones.

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Cree una variable llamada `dato` y le asigne un número entero
2. Muestre su tipo con `type()`
3. Asigne a la misma variable un texto
4. Vuelva a mostrar su tipo
5. Asigne un valor lógico y vuelva a comprobar el tipo

Puedes tomar como referencia un ejemplo como este:

~~~python
dato = 12
print(type(dato))

dato = "doce"
print(type(dato))

dato = False
print(type(dato))
~~~

Al probar este fragmento, conviene prestar atención a estas ideas:

- Una misma variable puede referirse a valores de distinto tipo
- Python reconoce automáticamente el tipo del valor asignado
- El tipo puede cambiar si cambia el valor asociado a la variable

:::caution[Error frecuente]
Un error frecuente es pensar que una variable conserva siempre el mismo tipo de dato. En Python, el tipo puede cambiar si se asigna un valor de otra clase. También es habitual confundir la flexibilidad del lenguaje con la idea de que ya no importa mantener orden y coherencia en el código.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta variables, asignación y tipos básicos en un contexto progresivo y formativo.

- [Biblioteca estándar: función `type()`](https://docs.python.org/3/library/functions.html#type)  
  Explica cómo consultar el tipo de un objeto en Python.

- [Tipos integrados de Python](https://docs.python.org/3/library/stdtypes.html)  
  Describe con mayor precisión técnica los tipos básicos del lenguaje y su comportamiento general.