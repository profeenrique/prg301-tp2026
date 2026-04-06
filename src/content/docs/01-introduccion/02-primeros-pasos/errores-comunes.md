---
title: Errores comunes
description: Errores frecuentes al comenzar a programar en Python y formas básicas de identificarlos y corregirlos.
slug: introduccion/primeros-pasos/errores-comunes
sidebar:
  label: Errores comunes
  order: 4
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que Python y Visual Studio Code ya están instalados en tu equipo, y que puedes ejecutar un archivo `.py` simple con la instrucción `print()`.
:::

Al comenzar a programar, cometer errores no es una excepción: es parte normal del proceso. Un programa puede fallar porque una línea quedó mal escrita, porque falta un símbolo, porque el archivo no está donde crees o porque el resultado obtenido no coincide con la intención original. Aprender Python también implica aprender a leer esos tropiezos, interpretarlos y corregirlos con calma.

## Objetivo

Reconocer errores frecuentes al comenzar a trabajar con Python y desarrollar una forma básica y ordenada de revisarlos y corregirlos.

## Qué significa que haya un error

En programación, un error es una situación en la que el programa no puede ejecutarse correctamente o no produce el resultado esperado.

Esto puede ocurrir por distintas razones. A veces Python no logra interpretar una instrucción. En otras ocasiones, el archivo no se ejecuta porque la terminal está en una carpeta incorrecta. También puede pasar que el programa sí funcione, pero entregue un resultado equivocado.

Por eso, al hablar de errores no nos referimos a una sola clase de problema, sino a varias situaciones distintas que conviene aprender a distinguir.

:::note[Idea clave]
Encontrar un error no significa que estés “programando mal”. Significa que el programa te está mostrando un punto que necesita revisión.
:::

## Por qué aparecen errores

Cuando una persona recién comienza, es muy común que los errores no estén en la idea general del programa, sino en detalles concretos de escritura o ejecución. Por ejemplo:

- Falta una comilla
- Falta un paréntesis
- El nombre de una función está mal escrito
- El archivo no fue guardado
- La terminal está ubicada en otra carpeta
- El programa hace algo distinto de lo que se quería lograr

Estos errores son normales. De hecho, aprender a programar también consiste en desarrollar la capacidad de detectarlos y leerlos con atención.

## No todos los errores son iguales

Conviene distinguir al menos cuatro tipos de errores frecuentes en esta etapa.

| Tipo de error | Qué suele ocurrir |
|---|---|
| Error de sintaxis | La instrucción está mal escrita y Python no puede interpretarla. |
| Error de nombre | Se escribe mal el nombre de una función, variable o archivo. |
| Error de ejecución | El programa se intenta ejecutar en una condición incorrecta, por ejemplo desde una carpeta equivocada. |
| Error lógico | El programa se ejecuta, pero el resultado no es el esperado. |

Esta clasificación ayuda a mirar el problema con más precisión. No es lo mismo corregir una línea mal escrita que revisar por qué el resultado final no coincide con la intención del programa.

## Cuando falla la escritura

Los errores de sintaxis aparecen cuando la forma de la instrucción no respeta las reglas del lenguaje. Python no puede “adivinar” lo que quisiste decir: interpreta solo lo que está escrito.

### Falta una comilla

Observa este caso:

~~~python
print("Hola)
~~~

Aquí falta la comilla de cierre. Python no puede reconocer correctamente dónde termina el texto.

La forma correcta sería esta:

~~~python
print("Hola")
~~~

Este tipo de error es muy frecuente al comenzar, porque una línea puede parecer casi correcta, pero basta un símbolo ausente para que deje de ser válida.

### Falta un paréntesis

Observa este otro caso:

~~~python
print("Hola"
~~~

Aquí falta el paréntesis de cierre. La instrucción queda incompleta y Python no puede ejecutarla.

La forma correcta es:

~~~python
print("Hola")
~~~

Este ejemplo ayuda a recordar algo importante: en programación, una línea no se considera correcta solo por “parecerse” a la forma válida. Debe estar completa.

## Cuando el nombre no coincide

Otro error frecuente aparece cuando se escribe mal el nombre de una función o de un elemento del programa.

~~~python
prnt("Hola")
~~~

Aquí Python no reconoce `prnt`, porque la función correcta se llama `print`.

La forma correcta es:

~~~python
print("Hola")
~~~

Este tipo de error muestra que el intérprete trabaja con precisión exacta. Una letra faltante o cambiada basta para que el nombre deje de ser reconocido.

## Cuando el problema no está en el código

A veces el programa está bien escrito, pero el error aparece al momento de ejecutarlo. En este nivel, uno de los casos más comunes es intentar ejecutar un archivo desde una carpeta incorrecta.

Por ejemplo, si escribes en la terminal:

~~~bash
python hola.py
~~~

pero el archivo no está en la carpeta actual, la terminal indicará que no puede encontrarlo.

Esto suele ocurrir cuando:

- El archivo no fue guardado
- El nombre del archivo no coincide exactamente
- La terminal está ubicada en otra carpeta
- Se escribió mal el comando

[IMAGEN: Terminal mostrando un error por archivo no encontrado]

Este caso es importante porque muestra que no todos los problemas se corrigen dentro del archivo. A veces también hay que revisar el contexto desde el que se está ejecutando.

## Cuando el programa sí corre, pero no hace lo esperado

Hay un tipo de error que suele costar más reconocer al comienzo: el error lógico. Aquí Python no se detiene, no muestra necesariamente un mensaje de error y ejecuta el programa sin problema. Sin embargo, el resultado no coincide con lo que se quería obtener.

Por ejemplo, si una persona quiere sumar dos valores, pero el programa en realidad concatena texto, el archivo puede ejecutarse sin fallar y aun así producir un resultado incorrecto.

Esto muestra una diferencia importante:

- Algunos errores impiden que el programa se ejecute
- Otros permiten que el programa corra, pero con una lógica equivocada

Reconocer esta diferencia será cada vez más importante a medida que los programas se vuelvan más largos.

## Cómo revisar un error con más orden

Cuando aparece un error, no conviene corregir al azar. Lo más útil es seguir una revisión breve y ordenada.

### Leer el mensaje completo

Cuando Python o la terminal muestran un error, conviene leer el mensaje completo antes de cambiar algo en el código.

[IMAGEN: Terminal mostrando un mensaje de error]

Aunque al comienzo esos mensajes puedan parecer difíciles, suelen entregar pistas valiosas: indican qué tipo de problema apareció y, muchas veces, en qué línea conviene comenzar a mirar.

### Revisar la línea señalada

En muchos casos, el error está en la misma línea indicada por el sistema o muy cerca de ella.

[IMAGEN: Terminal mostrando la línea donde ocurre el error]

Esto no significa que la línea marcada siempre sea “la única culpable”, pero sí suele ser el mejor punto de partida para revisar.

### Comprobar signos y nombres

En esta etapa, conviene revisar especialmente estos elementos:

- Comillas
- Paréntesis
- Nombre de funciones
- Nombre de archivos
- Carpeta desde la que se ejecuta el programa

Muchas veces el error está en uno de estos detalles pequeños.

### Guardar y ejecutar de nuevo

Después de corregir el problema, vuelve a guardar el archivo y ejecútalo nuevamente. Así podrás comprobar si el error fue resuelto o si todavía queda algo por revisar.

:::caution[Error frecuente]
Un error frecuente es corregir el código sin leer con atención el mensaje que aparece en la terminal o en el editor. Eso puede hacer que el problema continúe aunque se hayan modificado otras partes del archivo.
:::

## Un orden útil para empezar a revisar

Cuando aparezca un error, puede ayudarte seguir este orden:

1. Revisar si el archivo fue guardado
2. Revisar si el nombre del archivo está bien escrito
3. Comprobar si la terminal está en la carpeta correcta
4. Verificar si faltan comillas o paréntesis
5. Revisar si escribiste correctamente la instrucción
6. Leer nuevamente el mensaje de error

Este orden no resuelve todos los problemas posibles, pero sí ayuda a enfrentar con más calma los errores más frecuentes de esta etapa.

:::tip[Buena práctica]
Cuando un programa no funciona, comienza revisando los detalles más simples. Muchas veces el error está en un signo, una letra o la ubicación del archivo.
:::

## Qué conviene aprender de cada error

Más que intentar “borrar el error lo antes posible”, conviene preguntarse qué está mostrando ese problema. Por ejemplo:

- Si falta una comilla, el aprendizaje es que el texto debe delimitarse con precisión
- Si el nombre está mal escrito, el aprendizaje es que Python no interpreta aproximaciones
- Si el archivo no se encuentra, el aprendizaje es que ejecutar un programa también depende de la carpeta actual
- Si el resultado es incorrecto, el aprendizaje es que la lógica del programa debe revisarse además de la sintaxis

Mirar así los errores ayuda a transformar cada fallo en una oportunidad de comprensión, no solo en una molestia técnica.

## Del concepto a la práctica

Realiza las siguientes acciones y observa qué ocurre en cada caso:

1. Escribe `print("Hola)` y observa el error
2. Corrige la línea y vuelve a ejecutar el archivo
3. Escribe `prnt("Hola")` y observa el resultado
4. Corrige el nombre y vuelve a ejecutar
5. Intenta ejecutar un archivo desde una carpeta incorrecta y revisa el mensaje que aparece

Si quieres, también puedes hacer una pequeña comparación entre:

- Un programa que no ejecuta por error de sintaxis
- Un programa que sí ejecuta, pero muestra un resultado distinto del esperado

Esa comparación ayuda a distinguir mejor entre error de escritura y error lógico.

## Para seguir observando

Mientras haces estas pruebas, intenta responder estas preguntas:

- ¿Python siempre muestra el mismo tipo de error?
- ¿El mensaje apunta a un problema del código o de la ejecución?
- ¿El archivo está bien escrito, pero mal ejecutado?
- ¿El programa corre, pero hace algo distinto de lo que querías?
