---
title: ¡Hola mundo!
description: Primer programa en Python y primera ejecución desde Visual Studio Code y la terminal.
slug: introduccion/primeros-pasos/hola-mundo
sidebar:
  label: ¡Hola mundo!
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que Python y Visual Studio Code ya están instalados en tu equipo, y que puedes abrir una carpeta de trabajo en el editor.
:::

Todo lenguaje de programación suele comenzar con un programa muy breve. No porque ese primer ejemplo represente la complejidad real del lenguaje, sino porque permite comprobar algo esencial: que el entorno funciona y que el código escrito puede convertirse en una acción visible. En Python, ese primer paso suele darse con el clásico **¡Hola mundo!**.

## Objetivo

Escribir, guardar y ejecutar un primer programa en Python para reconocer la estructura mínima de un script y comprobar que el entorno de trabajo está funcionando correctamente.

## Un archivo que puede ejecutarse

En Python, un programa puede escribirse en un archivo con extensión `.py`. Dentro de ese archivo se colocan instrucciones que el intérprete leerá en el orden en que fueron escritas.

Eso significa que programar, en esta etapa, consiste en algo muy concreto:

- Crear un archivo
- Escribir una instrucción válida
- Guardarla
- Ejecutarla con Python
- Observar el resultado

Aunque parezca un proceso simple, aquí ya aparecen varias piezas importantes del trabajo con código: el archivo, el editor, el intérprete y la terminal.

:::note[Idea clave]
Un programa en Python es un conjunto de instrucciones escritas en un archivo con extensión `.py`. Cuando ese archivo se ejecuta, el intérprete lee sus instrucciones y produce un resultado.
:::

## El primer programa

Una forma clásica de comenzar a trabajar con un lenguaje de programación es escribir un programa muy simple que muestre un mensaje en pantalla.

En Python, esto puede hacerse con la función `print()`.

~~~python
print("¡Hola mundo!")
~~~

Este ejemplo no realiza cálculos, no pide datos y no toma decisiones. Su función es más básica, pero también muy importante: mostrar que el entorno puede ejecutar una instrucción correcta y producir una salida visible.

## Qué representa esta instrucción

Aunque se trate de una sola línea, conviene leerla con atención.

~~~python
print("¡Hola mundo!")
~~~

Aquí ocurre lo siguiente:

- `print` es una función de Python
- Los paréntesis indican que la función está siendo llamada
- El texto entre comillas corresponde al contenido que se mostrará en pantalla

Esta instrucción puede parecer mínima, pero ya muestra una idea central: el programa contiene una orden, y Python la ejecuta.

## Crear el archivo

Abre tu carpeta de trabajo en Visual Studio Code y crea un archivo nuevo llamado `hola.py`.

:::tip[Buena práctica]
El nombre del archivo debe terminar en `.py`, ya que esa extensión indica que se trata de un archivo de Python.
:::

Este detalle importa porque Python reconocerá ese archivo como un script del lenguaje. Si el archivo se guarda con otra extensión, el entorno dejará de tratarlo como código Python de la misma manera.

## Escribir y guardar

Dentro del archivo `hola.py`, escribe esta instrucción:

~~~python
print("¡Hola mundo!")
~~~

Luego guarda el archivo.

Guardar no es un paso menor. Cuando el programa se ejecuta, Python lee el contenido que está guardado en el archivo, no necesariamente lo último que aparece escrito en pantalla si todavía no se ha guardado.

## Ejecutar desde la terminal

Una vez guardado el archivo, abre la terminal integrada de Visual Studio Code y ejecuta uno de estos comandos, según tu sistema:

~~~bash
python hola.py
~~~

o:

~~~bash
python3 hola.py
~~~

Si todo está correcto, deberías ver este resultado en pantalla:

~~~text
¡Hola mundo!
~~~

[IMAGEN: Archivo `hola.py` abierto en VS Code y terminal mostrando la salida del programa]

Este momento es importante porque confirma varias cosas al mismo tiempo:

- Que el archivo fue creado correctamente
- Que Python puede encontrarlo
- Que el intérprete puede leer la instrucción
- Que la terminal muestra la salida del programa

## Qué hace `print()`

La función `print()` permite enviar información a la salida estándar, que en este contexto suele ser la terminal.

En este primer ejemplo, `print()` recibe un texto y lo muestra tal como fue escrito. Más adelante, esta función también servirá para mostrar variables, resultados de operaciones y mensajes más complejos.

Por ahora, basta con retener esta idea: `print()` permite que el programa haga visible algo en pantalla.

## Por qué este programa sí importa

A primera vista, `¡Hola mundo!` puede parecer demasiado simple. Sin embargo, cumple una función formativa muy clara. No se usa porque sea “interesante” en sí mismo, sino porque permite verificar que la cadena básica de trabajo ya está operativa:

- Escribir código
- Guardarlo en un archivo
- Ejecutarlo
- Observar la salida

Además, permite modificar el texto y comprobar que el cambio se refleja al volver a ejecutar el archivo. Ese gesto pequeño ayuda a establecer una relación muy importante entre lo que se escribe y lo que el programa hace.

## Probar, cambiar, volver a ejecutar

Una parte esencial de aprender programación consiste en probar pequeñas variaciones y observar su efecto. Por ejemplo, después de ejecutar el programa inicial, puedes cambiar el mensaje por otro:

~~~python
print("Estoy comenzando en Python")
~~~

Si guardas el archivo y lo ejecutas nuevamente, la salida cambiará.

Este paso es útil porque muestra que el programa no es algo fijo o misterioso. Es un archivo que puede modificarse, probarse y corregirse.

## Lo que conviene observar aquí

En este primer ejercicio no solo interesa “ver el saludo”. También conviene fijarse en varios elementos del proceso:

- El archivo debe llamarse correctamente
- La instrucción debe escribirse con la sintaxis adecuada
- El archivo debe guardarse antes de ejecutarse
- El comando en la terminal debe coincidir con el nombre del archivo
- La salida debe aparecer en pantalla como resultado de la ejecución

Esa mirada más atenta ayuda a comprender que programar no es solo escribir líneas de código, sino también saber cómo se ejecutan y cómo verificar lo que producen.

## Del concepto al código

Realiza las siguientes acciones:

1. Crea el archivo `hola.py`
2. Escribe la instrucción `print("¡Hola mundo!")`
3. Ejecuta el programa desde la terminal
4. Cambia el mensaje por otro texto y vuelve a ejecutarlo
5. Verifica que el resultado cambie en pantalla

Puedes probar, por ejemplo, con uno de estos mensajes:

~~~python
print("Hola, Python")
~~~

o:

~~~python
print("Este es mi primer programa")
~~~

## Para seguir observando

Después de hacer la prueba, intenta responder mentalmente estas preguntas:

- ¿Qué parte del programa indica lo que debe mostrarse?
- ¿Qué ocurre si cambias el texto entre comillas?
- ¿Qué pasa si ejecutas el archivo sin guardarlo antes?
- ¿Qué relación hay entre el nombre del archivo y el comando que escribes en la terminal?

Estas preguntas ayudan a transformar este primer ejemplo en algo más que una tradición: lo convierten en una primera experiencia real de ejecución de código.

:::caution[Error frecuente]
Un error frecuente es escribir mal el nombre del archivo al ejecutarlo desde la terminal. Si el archivo se llama `hola.py`, el comando debe coincidir exactamente con ese nombre. También es frecuente olvidar las comillas, los paréntesis o guardar el archivo antes de ejecutarlo.
:::