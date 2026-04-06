---
title: Entrada con input()
description: Uso de la función input() para capturar datos desde el teclado.
slug: fundamentos/interaccion/entrada-input
sidebar:
  label: Entrada con input()
  order: 2
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que sabes utilizar `print()` para mostrar información en pantalla, puedes crear variables simples en Python y ya conoces la conversión básica de tipos.
:::

Hasta ahora, los programas han mostrado información, pero todavía no han recibido datos desde quien los usa. Eso significa que el flujo ha ido en una sola dirección: el programa calcula o muestra, y la persona observa. La función `input()` cambia esa relación, porque permite que el programa espere una respuesta y la incorpore a su ejecución.

## Objetivo

Comprender cómo `input()` permite capturar información escrita desde el teclado y cómo integrar esos datos en variables y operaciones simples dentro de un programa.

## Cuando el programa necesita preguntar

Muchos programas no pueden resolver su tarea con valores escritos de antemano. Necesitan recibir información durante la ejecución. Por ejemplo:

- Un nombre
- Una edad
- Una nota
- Una cantidad
- Una respuesta breve

En esas situaciones, el programa debe detenerse, pedir un dato y esperar a que la persona usuaria lo escriba. En Python, esa tarea se realiza con `input()`.

## Qué hace `input()`

La función `input()` muestra un mensaje en pantalla, espera una respuesta escrita desde el teclado y devuelve ese valor al programa.

~~~python
nombre = input("Escribe tu nombre: ")
print(nombre)
~~~

Si la persona escribe `Ana`, el programa primero muestra el mensaje y luego guarda esa respuesta en la variable `nombre`. Después, al ejecutar `print(nombre)`, vuelve a mostrar el dato ingresado.

~~~text
Escribe tu nombre: Ana
Ana
~~~

Aquí ya aparece una idea importante: `input()` no solo pide información. También conecta la ejecución del programa con una respuesta externa.

~~~mermaid
flowchart LR
    A["Programa muestra un mensaje"] --> B["La persona escribe un dato"]
    B --> C["input() recibe la respuesta"]
    C --> D["El valor se guarda en una variable"]
~~~

Esa secuencia convierte al programa en algo más interactivo: ya no trabaja únicamente con valores escritos por quien programó, sino también con datos ingresados durante la ejecución.

## La estructura más común

La forma más habitual de usar `input()` es esta:

~~~python
variable = input("Mensaje: ")
~~~

En esa instrucción ocurren varias cosas al mismo tiempo:

- El mensaje entre comillas se muestra en pantalla
- El programa queda a la espera de una respuesta
- La persona usuaria escribe un valor y presiona Enter
- Ese valor se guarda en la variable indicada

Lo importante es notar que `input()` no deja el dato “en el aire”. Lo devuelve, y por eso normalmente se usa junto a una asignación.

## Pedir texto

Una de las aplicaciones más directas de `input()` consiste en capturar texto: nombres, ciudades, respuestas breves o palabras clave.

~~~python
ciudad = input("Escribe tu ciudad: ")
print(f"Ciudad ingresada: {ciudad}")
~~~

Si la persona escribe `Valparaíso`, el programa puede recuperar ese contenido y utilizarlo más adelante.

~~~text
Escribe tu ciudad: Valparaíso
Ciudad ingresada: Valparaíso
~~~

Este tipo de interacción es simple, pero ya muestra algo esencial: el programa puede recibir información nueva en el momento en que se ejecuta.

## Lo que `input()` devuelve siempre

Aquí conviene detenerse en una idea fundamental: `input()` siempre devuelve texto.

Eso significa que, aunque la persona escriba algo que parece un número, Python lo recibe primero como una cadena de caracteres.

~~~python
edad = input("Escribe tu edad: ")
print(type(edad))
~~~

Si se escribe `18`, Python informa que el valor almacenado pertenece al tipo `str`.

~~~text
Escribe tu edad: 18
<class 'str'>
~~~

:::note[Idea clave]
Aunque la persona usuaria escriba `18`, `input()` lo recibe primero como texto.
:::

Esta idea es decisiva, porque explica muchos errores frecuentes al comenzar. El programa no “adivina” que un dato debe tratarse como entero o decimal solo porque se ve como número.

## Cuando hay que convertir

Si el dato ingresado debe usarse como número, es necesario convertirlo. Esa conversión suele hacerse inmediatamente después de la entrada.

~~~python
edad = int(input("Escribe tu edad: "))

print(edad)
print(type(edad))
~~~

Aquí ocurre una secuencia muy importante:

- `input()` recibe el dato como texto
- `int()` transforma ese texto en un entero
- El valor convertido se guarda en la variable `edad`

Si la persona escribe `18`, el programa ya no conserva `"18"` como texto, sino `18` como número entero.

~~~text
Escribe tu edad: 18
18
<class 'int'>
~~~

Esta combinación es muy frecuente en programación básica, porque muchas entradas del usuario deben transformarse antes de participar en un cálculo o una comparación.

## Convertir a decimal

La misma lógica se aplica cuando el dato debe interpretarse como número decimal.

~~~python
estatura = float(input("Escribe tu estatura: "))
print(estatura)
print(type(estatura))
~~~

Si la persona escribe `1.72`, Python recibe primero el texto y luego lo convierte a un valor decimal.

~~~text
Escribe tu estatura: 1.72
1.72
<class 'float'>
~~~

Esto permite trabajar correctamente con promedios, medidas, precios o cualquier dato que incluya parte decimal.

## Pedir y responder

Una de las formas más naturales de usar `input()` consiste en capturar un dato y luego incorporarlo a un mensaje de salida.

~~~python
nombre = input("Escribe tu nombre: ")
print(f"Hola, {nombre}")
~~~

Aquí el programa no solo recibe información. También la reutiliza para construir una respuesta.

~~~text
Escribe tu nombre: Camila
Hola, Camila
~~~

Este patrón resulta muy útil porque hace visible la relación entre entrada y salida: el programa recibe un dato, lo almacena y luego actúa con él.

## Más de un dato

Un mismo programa puede pedir varios datos, siempre que los guarde en variables distintas.

~~~python
nombre = input("Escribe tu nombre: ")
edad = input("Escribe tu edad: ")

print(f"Nombre: {nombre}")
print(f"Edad: {edad}")
~~~

Si la persona escribe `Diego` y luego `17`, el programa conserva ambos valores por separado.

~~~text
Escribe tu nombre: Diego
Escribe tu edad: 17
Nombre: Diego
Edad: 17
~~~

Este tipo de estructura ya permite construir programas más ricos, porque trabaja con más de una pieza de información al mismo tiempo.

## Cuando no conviertes

Uno de los errores más frecuentes con `input()` aparece cuando el programa recibe un valor que parece numérico, pero sigue siendo texto porque no fue convertido.

~~~python
numero = input("Escribe un número: ")
print(numero + numero)
~~~

Si la persona escribe `5`, el resultado no será `10`, sino:

~~~text
Escribe un número: 5
55
~~~

Esto ocurre porque Python no está sumando números. Está uniendo dos textos.

Si el dato se convierte antes de usarlo, el comportamiento cambia:

~~~python
numero = int(input("Escribe un número: "))
print(numero + numero)
~~~

Ahora, si la persona escribe `5`, el programa sí realiza una suma numérica.

~~~text
Escribe un número: 5
10
~~~

Este contraste es muy útil para comprender por qué la conversión no es un detalle opcional, sino una decisión necesaria cuando el programa debe operar con la entrada recibida.

## Cuando la entrada no sirve para convertir

No siempre es posible transformar cualquier texto en número. Si la persona escribe un valor que no tiene formato numérico válido, la conversión falla.

~~~python
edad = int(input("Escribe tu edad: "))
~~~

Si en lugar de un número se escribe `hola`, Python genera un error, porque ese contenido no puede interpretarse como entero.

:::caution[Error frecuente]
Un error frecuente es pensar que `input()` devuelve números cuando la persona usuaria escribe cifras. En Python, `input()` devuelve texto, por lo que muchas veces es necesario convertir el valor antes de usarlo. También es frecuente intentar convertir a número un texto que no corresponde a un valor numérico válido.
:::

Este punto es importante porque muestra que trabajar con entrada de datos no consiste solo en pedir información, sino también en pensar si esa información tiene la forma adecuada para lo que el programa necesita hacer.

## Leer mejor la interacción

A esta altura conviene observar que `input()` participa en una lógica bastante completa:

- El programa plantea una pregunta
- La persona responde
- El dato se guarda
- Ese dato puede mostrarse, convertirse o usarse en un cálculo

Dicho de otro modo, `input()` no es solo una función para “leer desde teclado”. Es una puerta de entrada para incorporar datos reales a la ejecución del programa.

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Pida el nombre de una persona y lo muestre en pantalla
2. Pida la edad de una persona y la muestre
3. Pida un número entero, lo convierta con `int()` y lo muestre
4. Pida un número decimal, lo convierta con `float()` y lo muestre
5. Pida dos números enteros, los convierta y muestre su suma

Puedes tomar como punto de partida un ejemplo como este:

~~~python
nombre = input("Escribe tu nombre: ")
print(f"Nombre ingresado: {nombre}")

edad = int(input("Escribe tu edad: "))
print(f"Edad: {edad}")

numero1 = int(input("Escribe el primer número: "))
numero2 = int(input("Escribe el segundo número: "))
print(f"Suma: {numero1 + numero2}")
~~~

Al probar este fragmento, conviene prestar atención a estas ideas:

- `input()` recibe datos durante la ejecución del programa
- El valor ingresado se guarda en una variable
- Si se necesita operar con números, normalmente hay que convertir el dato antes de usarlo

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Biblioteca estándar: función `input()`](https://docs.python.org/3/library/functions.html#input)  
  Describe con precisión cómo funciona `input()` y qué valor devuelve.

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta ejemplos básicos de interacción, variables y uso inicial del lenguaje.

- [Biblioteca estándar: funciones integradas](https://docs.python.org/3/library/functions.html)  
  Explica funciones como `input()`, `print()`, `int()` y `float()`, que suelen aparecer juntas en programas interactivos.