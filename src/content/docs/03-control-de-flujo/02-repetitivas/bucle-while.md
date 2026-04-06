---
title: Bucle while
description: Repetición controlada en Python mediante la estructura while.
slug: control-de-flujo/repetitivas/bucle-while
sidebar:
  label: Bucle while
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que comprendes la estructura `if`, sabes trabajar con comparaciones y reconoces la importancia de la indentación en Python.
:::

No todos los problemas se resuelven con una sola secuencia de instrucciones. En muchos casos, el programa necesita **repetir una acción mientras cierta condición siga siendo válida**. Esa idea aparece, por ejemplo, cuando se cuenta, se valida un dato, se espera una respuesta correcta o se repite un proceso hasta que algo cambie. En Python, una de las estructuras que permite expresar esa lógica es `while`.

## Objetivo

Comprender cómo la estructura `while` permite repetir un bloque de instrucciones mientras una condición se mantenga verdadera, y cómo esa repetición puede utilizarse para modelar procesos, conteos y validaciones dentro de un programa.

## Repetir mientras algo siga ocurriendo

La estructura `while` permite ejecutar un bloque de instrucciones una y otra vez mientras una condición continúe siendo verdadera.

~~~python
while condicion:
    instruccion_1
    instruccion_2
~~~

Esta forma general concentra una idea muy importante: el programa no repite “porque sí”, sino **mientras una condición lo autorice**.

En esa escritura conviene reconocer tres partes:

- `while` es la palabra reservada que inicia el ciclo
- `condicion` es la expresión que Python evalúa antes de cada repetición
- el bloque indentado contiene las instrucciones que se repetirán mientras la condición resulte verdadera

:::note[Idea clave]
Un `while` no está definido por una cantidad fija de repeticiones, sino por una condición que se vuelve a comprobar una y otra vez.
:::

## La condición manda

A diferencia de otros tipos de repetición, `while` no sabe de antemano cuántas veces ejecutará su bloque. Todo depende de la condición.

Si la condición es verdadera, el ciclo continúa.  
Si la condición pasa a ser falsa, el ciclo termina y el programa sigue con la instrucción que viene después.

~~~mermaid
flowchart TD
    A[Inicio] --> B{¿La condición es verdadera?}
    B -->|Sí| C[Ejecutar bloque del while]
    C --> D[Volver a evaluar la condición]
    D --> B
    B -->|No| E[Salir del ciclo]
~~~

Este recorrido permite entender algo central: la condición no se evalúa una sola vez al comienzo, sino antes de cada nueva vuelta del ciclo.

## Contar para avanzar

Una de las formas más claras de empezar a leer un `while` consiste en trabajar con un contador.

~~~python
contador = 1

while contador <= 3:
    print(contador)
    contador = contador + 1
~~~

Aquí el programa comienza con `contador = 1`. Luego comprueba si `contador <= 3`. Como la condición es verdadera, imprime el valor y lo incrementa en una unidad.

Después vuelve a comprobar la condición:

- cuando `contador` vale `1`, imprime `1`
- cuando vale `2`, imprime `2`
- cuando vale `3`, imprime `3`
- cuando pasa a valer `4`, la condición ya no se cumple y el ciclo termina

En pantalla aparecen estos valores:

~~~text
1
2
3
~~~

Este ejemplo deja ver una idea muy importante: un `while` necesita algo que cambie dentro del ciclo. Si el estado del programa no se modifica, la condición seguirá evaluándose igual y la repetición no avanzará.

## Qué hace que el ciclo funcione

En un ciclo como el anterior conviene mirar tres piezas que trabajan juntas:

| Parte | Función | Ejemplo |
| --- | --- | --- |
| Valor inicial | Sitúa el punto de partida del ciclo | `contador = 1` |
| Condición | Decide si el ciclo continúa o termina | `contador <= 3` |
| Actualización | Modifica el valor para que el proceso avance | `contador = contador + 1` |

Esta estructura no sirve solo para contar. También aparece en muchas otras situaciones: desplazarse por un proceso, esperar una condición, validar entradas o repetir un cálculo.

## Cuando nada cambia

Uno de los errores más frecuentes al comenzar a usar `while` es olvidar la actualización de la variable que controla la condición.

~~~python
contador = 1

while contador <= 3:
    print(contador)
~~~

Aquí la condición `contador <= 3` comienza siendo verdadera y sigue siéndolo, porque `contador` nunca cambia. Como no hay nada dentro del bloque que altere ese valor, Python vuelve a evaluar siempre la misma situación.

El resultado es un ciclo que no termina por sí solo.

:::danger[Evita el bucle infinito]
Si la condición del `while` sigue siendo verdadera y nada dentro del ciclo modifica esa situación, el bucle continuará indefinidamente.
:::

Este punto merece atención porque muestra que escribir un `while` no consiste solo en poner una condición. También implica pensar **qué hará avanzar el proceso**.

## Un proceso paso a paso

El bucle `while` no sirve únicamente para contar. También permite representar procesos que cambian gradualmente.

~~~python
numero = 5

while numero > 0:
    print(f"Cuenta regresiva: {numero}")
    numero = numero - 1

print("Despegue")
~~~

Aquí el programa no repite una acción arbitraria. Modela una cuenta regresiva. Mientras `numero` sea mayor que `0`, el ciclo sigue activo. En cada vuelta, el valor disminuye en una unidad.

En pantalla se observa esta secuencia:

~~~text
Cuenta regresiva: 5
Cuenta regresiva: 4
Cuenta regresiva: 3
Cuenta regresiva: 2
Cuenta regresiva: 1
Despegue
~~~

Este ejemplo resulta interesante porque muestra que un `while` puede representar algo más que una repetición mecánica. Puede expresar el avance de un proceso, una transición o una espera hasta llegar a cierto punto.

## Repetir hasta validar

Otra aplicación muy frecuente de `while` aparece cuando el programa necesita insistir hasta recibir un dato válido.

~~~python
edad = int(input("Ingresa una edad válida: "))

while edad < 0:
    edad = int(input("La edad no puede ser negativa. Intenta nuevamente: "))

print("Edad registrada")
~~~

Aquí el programa recibe una edad y comprueba si el valor es menor que `0`. Si lo es, la condición del ciclo se cumple y el programa vuelve a pedir el dato.

La lógica del proceso puede leerse así:

- se ingresa una edad
- si el valor no es válido, el programa no avanza
- vuelve a pedir el dato
- solo sale del ciclo cuando la edad deja de ser negativa

Este patrón es muy importante en programación porque muestra que `while` no sirve únicamente para repetir “un número de veces”, sino para repetir **hasta que una situación cambie de manera satisfactoria**.

:::caution[Conversión de datos]
`input()` devuelve texto. Si necesitas comparar números dentro de un `while`, primero debes convertir el dato con `int()` o `float()`, según corresponda.
:::

## Lo que conviene preguntarse antes de escribirlo

Antes de usar un `while`, conviene formular con claridad tres preguntas:

- ¿Qué condición debe cumplirse para que el ciclo siga activo?
- ¿Qué dato o estado controla esa condición?
- ¿Qué ocurrirá dentro del bloque para que el ciclo avance y eventualmente termine?

Estas preguntas ayudan a construir ciclos más correctos y también más legibles. Un `while` mal pensado puede funcionar por accidente o volverse difícil de entender. Uno bien planteado deja claro qué se repite, por qué se repite y qué hace que esa repetición termine.

## Cuándo conviene usar `while`

El bucle `while` suele ser una buena elección cuando la repetición depende de una condición y no de una cantidad fija conocida desde el comienzo.

Suele ser apropiado cuando:

- la repetición depende de un valor que cambia
- el programa debe validar una entrada
- la acción debe continuar hasta que ocurra cierta situación
- no se conoce con anticipación cuántas repeticiones serán necesarias

Si, en cambio, el recorrido ya está determinado desde el comienzo o depende de una secuencia conocida, `for` suele resultar más adecuado.

:::tip[Lectura útil]
Piensa `while` de esta manera: “mientras esta condición siga siendo verdadera, este bloque debe seguir ejecutándose”.
:::

## Del concepto al código

Escribe un programa en Python que solicite una contraseña y no permita avanzar hasta que el usuario escriba `python123`.

El programa debe cumplir con los siguientes requisitos:

- Debe pedir la contraseña usando `input()`
- Debe usar un bucle `while`
- Debe seguir solicitando el dato mientras la contraseña sea incorrecta
- Debe mostrar un mensaje final cuando la contraseña sea correcta

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa la contraseña: hola
Contraseña incorrecta
Ingresa la contraseña: 1234
Contraseña incorrecta
Ingresa la contraseña: python123
Acceso permitido
~~~

:::tip[Antes de escribir el código]
Antes de programar, define con claridad cuál será la condición del `while`, qué dato cambiará en cada vuelta y en qué momento el ciclo deberá terminar.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta los bucles en un contexto formativo y muestra cómo se relacionan con otras estructuras de control.

- [Referencia del lenguaje: sentencia `while`](https://docs.python.org/3/reference/compound_stmts.html#the-while-statement)  
  Describe con mayor precisión técnica cómo se define `while` dentro del lenguaje.

- [Documentación oficial en español: más herramientas para control de flujo](https://docs.python.org/es/dev/tutorial/controlflow.html)  
  Ofrece una explicación accesible del tema en español y resulta útil para reforzar la comprensión general del bucle.