---
title: La terminal
description: Uso básico de la terminal para ejecutar archivos de Python y trabajar con carpetas.
slug: introduccion/primeros-pasos/terminal
sidebar:
  label: La terminal
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que Python y Visual Studio Code ya están instalados en tu equipo, y que puedes ejecutar un archivo `.py` simple con la instrucción `print()`.
:::

Hasta este punto, el trabajo con Python probablemente se ha concentrado en el editor: escribir una instrucción, guardar un archivo y observar el resultado. Sin embargo, para ejecutar programas y comprender mejor cómo se relacionan el archivo, el intérprete y el sistema operativo, es importante comenzar a usar la terminal.

## Objetivo

Comprender el papel de la terminal en el trabajo con Python y utilizar comandos básicos para ubicarse en una carpeta de trabajo y ejecutar archivos simples.

## Qué es la terminal

La terminal es una interfaz basada en texto que permite comunicarse directamente con el sistema operativo mediante comandos. A diferencia de una interfaz gráfica, aquí no se trabaja principalmente con botones o menús, sino escribiendo instrucciones que el sistema interpreta y ejecuta.

En programación, la terminal es importante porque permite:

- Ejecutar scripts
- Comprobar que una herramienta está instalada
- Moverse entre carpetas
- Revisar archivos disponibles
- Observar mensajes y errores del sistema

:::note[Idea clave]
La terminal no reemplaza al editor de código. Ambas herramientas se complementan: el editor sirve para escribir y organizar archivos, mientras que la terminal permite ejecutarlos y trabajar con el sistema de forma más directa.
:::

## Por qué conviene aprender a usarla

Cuando comienzas a programar, puede parecer que basta con escribir el archivo y presionar algún botón del editor. Sin embargo, aprender a usar la terminal ayuda a comprender mejor qué está ocurriendo realmente cuando ejecutas un programa.

Permite ver con más claridad la relación entre:

- El archivo que escribes
- La carpeta donde está guardado
- El intérprete que ejecuta el programa
- La salida o el error que aparece en pantalla

~~~mermaid
flowchart LR
    A[Archivo .py] --> B[Terminal]
    B --> C[Intérprete de Python]
    C --> D[Salida o error en pantalla]
~~~

Esta relación es importante porque muchas tareas de programación dependen de ejecutar comandos de forma explícita y no solo desde una interfaz gráfica.

## Qué tipo de acciones permite

Aunque los comandos exactos pueden variar según el sistema operativo, hay algunas acciones que conviene reconocer desde el comienzo.

| Acción | Ejemplo general |
|---|---|
| Ver la versión de Python | `python --version` o `python3 --version` |
| Ejecutar un archivo | `python hola.py` o `python3 hola.py` |
| Mostrar la carpeta actual | `pwd` o equivalente |
| Listar archivos | `ls` o equivalente |
| Cambiar de carpeta | `cd nombre_carpeta` |

Lo importante en esta etapa no es memorizar todos los comandos posibles, sino comprender qué problema resuelve cada uno dentro del flujo de trabajo.

## Abrir la terminal

Puedes abrir la terminal desde el sistema operativo o usar la terminal integrada de Visual Studio Code.

[IMAGEN: Terminal integrada abierta en Visual Studio Code]

La terminal integrada resulta especialmente útil porque permite escribir código en el editor y ejecutar comandos en el mismo entorno de trabajo, sin cambiar de aplicación.

## Saber dónde estás

Antes de ejecutar un archivo, conviene comprobar en qué carpeta se encuentra abierta la terminal. Esto importa porque Python intentará buscar el archivo en la ubicación actual.

En muchos sistemas, puedes usar:

~~~bash
pwd
~~~

o un comando equivalente para mostrar la ruta activa.

Esta verificación es importante porque un programa puede estar bien escrito y bien guardado, pero no ejecutarse si la terminal está ubicada en otra carpeta.

## Ver qué archivos hay disponibles

También conviene revisar qué archivos se encuentran en la carpeta actual. En muchos sistemas, puedes usar:

~~~bash
ls
~~~

o un comando equivalente.

Este paso ayuda a confirmar que el archivo que quieres ejecutar realmente está en esa ubicación. Si el archivo `hola.py` no aparece en la lista, entonces la terminal no podrá ejecutarlo desde ahí.

## Ejecutar un archivo Python

Supongamos que tienes un archivo llamado `hola.py` dentro de tu carpeta de trabajo. Si la terminal está ubicada correctamente, puedes ejecutarlo con uno de estos comandos:

~~~bash
python hola.py
~~~

o, según tu sistema:

~~~bash
python3 hola.py
~~~

Cuando haces eso, el intérprete lee el archivo y ejecuta las instrucciones que contiene.

Si todo está correcto, el resultado del programa aparecerá directamente en la terminal.

## Un ejemplo simple

Si `hola.py` contiene esto:

~~~python
print("¡Hola mundo!")
~~~

al ejecutarlo desde la terminal deberías ver algo como esto:

~~~text
¡Hola mundo!
~~~

[IMAGEN: Terminal mostrando la ejecución correcta de `hola.py`]

Este ejemplo, aunque simple, permite comprobar varias cosas al mismo tiempo:

- Que el archivo fue guardado correctamente
- Que la terminal está en la carpeta adecuada
- Que el comando de ejecución es válido
- Que Python puede interpretar el contenido del archivo

## Leer la salida también es parte del proceso

Cuando ejecutas un script desde la terminal, la salida del programa aparece directamente allí. Eso permite observar con rapidez si el programa funcionó o si surgió algún problema.

La terminal no solo muestra resultados correctos. También muestra errores, advertencias y mensajes del sistema. Por eso, aprender a usarla implica también acostumbrarse a leer lo que devuelve.

## Cuando algo falla

Muchos errores iniciales no se deben al contenido del programa, sino a problemas de ejecución desde la terminal. Por ejemplo:

- La terminal está abierta en una carpeta distinta
- El nombre del archivo fue escrito incorrectamente
- El sistema requiere `python3` en lugar de `python`
- El archivo no fue guardado antes de ejecutarse

:::caution[Error frecuente]
Un error frecuente es intentar ejecutar un archivo desde una carpeta distinta a aquella donde está guardado. Cuando eso ocurre, la terminal no encuentra el archivo y muestra un mensaje de error. También es frecuente usar `python` cuando el sistema requiere `python3`, o escribir mal el nombre del archivo.
:::

## Una herramienta que da autonomía

Aprender a usar la terminal desde el comienzo ayuda a construir una relación más consciente con el entorno de trabajo. Permite depender menos de botones automáticos y entender mejor cómo se ejecuta realmente un programa.

Esa autonomía será útil más adelante, porque muchas herramientas de desarrollo, instalación y prueba también se utilizan desde la terminal.

:::tip[Buena práctica]
Antes de ejecutar un archivo, verifica siempre su nombre y la carpeta en la que te encuentras.
:::

## Del concepto al código

Realiza las siguientes acciones:

1. Abre la terminal integrada de Visual Studio Code
2. Comprueba en qué carpeta te encuentras
3. Verifica que el archivo `hola.py` esté disponible
4. Ejecuta el archivo con `python hola.py` o `python3 hola.py`
5. Observa el resultado que aparece en pantalla

Si quieres, puedes probar además qué ocurre cuando:

- Ejecutas el archivo desde otra carpeta
- Escribes mal su nombre
- Modificas el mensaje dentro del archivo y vuelves a ejecutarlo

Estas pruebas ayudan a comprender que la ejecución de un programa no depende solo del código, sino también del contexto desde el cual se está trabajando.