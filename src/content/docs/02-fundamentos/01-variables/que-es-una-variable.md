---
title: ¿Qué es una variable?
description: Concepto de variable en Python y su uso para almacenar información.
slug: fundamentos/variables/que-es-una-variable
sidebar:
  label: ¿Qué es una variable?
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de comprender qué es una variable en Python, cómo crear una variable mediante asignación y el uso de `print()` para mostrar valores en pantalla.
:::

Programar implica trabajar con información de manera constante. Un programa recibe datos, los conserva por un momento, los transforma y luego los utiliza para producir un resultado. Para que eso sea posible, el lenguaje necesita una forma de **asociar un nombre con un valor**. Esa es, precisamente, una de las funciones centrales de las variables.

## Objetivo

Comprender qué es una variable en Python y cómo permite representar, almacenar, recuperar y actualizar información durante la ejecución de un programa.

## Dar nombre a un dato

Cuando escribimos un programa, muchas veces necesitamos conservar información para usarla más adelante. Ese dato puede ser, por ejemplo:

- Un nombre
- Una edad
- Un precio
- El resultado de un cálculo
- La respuesta ingresada por una persona usuaria

Si el programa no pudiera guardar esa información, tendría que repetir valores una y otra vez, y sería mucho más difícil trabajar con datos que cambian a lo largo de la ejecución.

En Python, una variable permite justamente eso: dar un nombre a un valor para que el programa pueda volver a utilizarlo cuando lo necesite.

:::note[Idea clave]
Una variable no es el valor en sí mismo. Es el nombre que permite acceder a ese valor dentro del programa.
:::

Esta idea parece sencilla, pero marca una diferencia importante. En programación no basta con tener datos: también hay que poder referirse a ellos, actualizarlos y usarlos en distintos momentos del algoritmo.

## Cómo se crea

La forma más habitual de crear una variable en Python es mediante una asignación.

~~~python
nombre = "Ada"
~~~

Esta instrucción contiene tres elementos que conviene reconocer con claridad:

- `nombre` es el nombre elegido para la variable
- `=` es el operador de asignación
- `"Ada"` es el valor que queda asociado a ese nombre

A partir de ese momento, `nombre` deja de ser solo una palabra escrita en el código. Pasa a representar un dato que el programa puede recuperar cuando lo necesite.

~~~mermaid
flowchart LR
    A["'Ada'"] --> B["nombre"]
    B --> C["Puede reutilizarse más adelante"]
~~~

Lo importante aquí no es memorizar la forma de la instrucción, sino comprender su lógica: el programa guarda un valor y lo deja disponible bajo un nombre.

## El sentido de `=`

Uno de los primeros ajustes que conviene hacer al aprender programación es entender que el símbolo `=` no se usa aquí con el mismo sentido que en matemáticas.

En Python, `=` no expresa igualdad. Expresa asignación.

~~~python
edad = 18
~~~

Esta instrucción no afirma que `edad` “sea igual” a `18` como en una expresión matemática. Lo que hace es asociar el valor `18` al nombre `edad`.

Esta diferencia es importante porque gran parte de la programación consiste en asignar, actualizar y reutilizar valores. Comprender el papel de `=` desde el comienzo ayuda a evitar muchas confusiones posteriores.

:::caution[Atención con `=`]
En Python, `=` se usa para asignar un valor a una variable. No se utiliza para afirmar una igualdad matemática.
:::

## Recuperar un valor

Una vez creada, la variable puede utilizarse en otras instrucciones.

~~~python
nombre = "Ada"
print(nombre)
~~~

Al ejecutar este fragmento, Python muestra `Ada`, porque `print(nombre)` recupera el valor asociado a la variable y lo envía a la salida del programa.

Aquí aparece una de las ventajas más importantes de las variables: el programa ya no depende de repetir el dato literal cada vez, porque puede recuperarlo mediante un nombre.

## Cuando el valor cambia

Una variable puede recibir un nuevo valor durante la ejecución del programa. Eso significa que el nombre se mantiene, pero el dato asociado puede cambiar.

~~~python
nombre = "Ada"
nombre = "Guido"
print(nombre)
~~~

En pantalla aparece `Guido`, porque ese fue el último valor asignado a la variable `nombre`.

Este comportamiento es esencial en programación. Muchas veces un programa necesita actualizar información: aumentar un contador, reemplazar un dato, corregir un valor o almacenar un nuevo resultado. La posibilidad de reasignar valores es, por tanto, una parte natural del trabajo con variables.

## Una variable dentro del proceso

En un programa simple, una variable puede intervenir en distintos momentos del flujo de trabajo:

- Primero recibe un valor
- Después ese valor puede usarse en otra instrucción
- Más adelante puede cambiar
- Finalmente puede mostrarse o participar en un cálculo

Esa lógica convierte a la variable en una pieza central del programa. No es solo un nombre conveniente, sino una forma de representar información que participa activamente en el desarrollo del algoritmo.

## Nombrar bien importa

Elegir buenos nombres para las variables mejora la lectura del código y ayuda a entender con mayor claridad qué hace el programa.

No basta con que un nombre sea válido. También conviene que sea útil para quien lea el código, incluso si esa persona eres tú mismo unos días después.

| Tipo de nombre | Ejemplo | Qué aporta |
| --- | --- | --- |
| Claro y simple | `edad` | Permite comprender rápidamente qué dato almacena |
| Más descriptivo | `nombre_usuario` | Aporta más precisión cuando el dato lo requiere |
| Poco claro | `x` | Puede dificultar la lectura si no entrega contexto |

En Python, además, conviene respetar algunas reglas básicas:

- Usar nombres claros
- Evitar espacios
- No comenzar con números
- No usar caracteres especiales innecesarios
- Preferir palabras en minúscula separadas por guion bajo cuando el nombre tiene más de una palabra

Por ejemplo, estos nombres son válidos:

~~~python
edad
nombre_usuario
precio_final
~~~

En cambio, estos nombres no son válidos:

~~~python
2nombre
nombre usuario
precio-final
~~~

:::tip[Buena práctica]
Elige nombres que ayuden a comprender el propósito de la variable. Un nombre claro facilita la lectura, la revisión y la corrección del programa.
:::

## Variable y texto no son lo mismo

Al comenzar, es frecuente confundir una variable con un texto escrito entre comillas. Sin embargo, cumplen funciones distintas.

~~~python
nombre = "Ada"
print(nombre)

print("nombre")
~~~

En la primera instrucción de salida, Python recupera el valor almacenado en la variable `nombre` y muestra `Ada`. En la segunda, en cambio, muestra literalmente el texto `"nombre"`, porque está escrito entre comillas.

Esta diferencia es importante porque una variable representa un dato que el programa puede reutilizar, mientras que un texto entre comillas se interpreta como contenido literal.

En esta etapa conviene distinguir con claridad tres cosas:

- El nombre de la variable
- El valor almacenado
- El texto literal escrito entre comillas

Gran parte de la lectura correcta de un programa depende de no confundir esos tres niveles.

## Una idea que conviene retener

Las variables permiten que un programa trabaje con información de forma flexible. Gracias a ellas, el código puede guardar datos, reutilizarlos, modificarlos y mostrarlos cuando sea necesario.

Dicho de otro modo, una variable transforma un dato aislado en algo que el programa puede manejar como parte de un proceso.

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Cree una variable llamada `nombre` y le asigne tu nombre
2. Muestre el valor de esa variable con `print()`
3. Cree una variable llamada `edad` y le asigne un número
4. Muestre ambas variables en pantalla
5. Cambie el valor de una de ellas y vuelva a ejecutar el programa

Puedes tomar como referencia un caso como este:

~~~python
nombre = "Camila"
edad = 16

print(nombre)
print(edad)

edad = 17

print(edad)
~~~

Al probar este fragmento, conviene prestar atención a estas ideas:

- Las variables permiten guardar datos con un nombre
- Esos datos pueden mostrarse en pantalla
- El valor de una variable puede cambiar durante el programa

:::caution[Error frecuente]
Un error frecuente es pensar que el símbolo `=` significa exactamente lo mismo que en matemáticas. En Python, ese símbolo se usa para asignar un valor a una variable. También es habitual escribir nombres poco claros o intentar usar espacios dentro del nombre de una variable.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta variables, asignación y operaciones básicas en un contexto formativo y progresivo.

- [Referencia del lenguaje: asignación](https://docs.python.org/3/reference/simple_stmts.html#assignment-statements)  
  Describe con mayor precisión técnica cómo funciona la asignación en Python.

- [PEP 8: estilo para nombres en Python](https://peps.python.org/pep-0008/#function-and-variable-names)  
  Ayuda a comprender por qué conviene usar nombres claros y consistentes al escribir variables.