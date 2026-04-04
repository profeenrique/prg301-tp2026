---
title: La terminal
description: Uso básico de la terminal para ejecutar archivos de Python y trabajar con carpetas.
slug: introduccion/primeros-pasos/terminal
sidebar:
  label: La terminal
  order: 3
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Python ya está instalado en tu equipo.
- Visual Studio Code ya está instalado.
- Ya lograste crear y guardar un archivo `.py`.
:::

## Objetivo

Utilizar la terminal para ubicarse en una carpeta de trabajo y ejecutar archivos simples de Python.

## Concepto clave

La terminal es una herramienta que permite escribir comandos para interactuar directamente con el sistema operativo y ejecutar programas.

## ¿Qué es la terminal?

La terminal es una interfaz basada en texto. A través de ella es posible abrir carpetas, ejecutar programas, verificar instalaciones y trabajar con archivos sin depender únicamente de una interfaz gráfica.

En programación, la terminal es importante porque permite:

- Ejecutar scripts
- Comprobar que una herramienta está instalada
- Moverse entre carpetas
- Observar mensajes y errores del sistema

:::note[Idea clave]
La terminal no reemplaza al editor de código. Ambas herramientas se complementan.
:::

## Comandos básicos

Aunque los comandos pueden variar según el sistema operativo, hay algunas acciones que conviene reconocer desde el inicio.

| Acción | Ejemplo general |
|---|---|
| Ver la versión de Python | `python --version` o `python3 --version` |
| Ejecutar un archivo | `python hola.py` o `python3 hola.py` |
| Mostrar la carpeta actual | `pwd` o equivalente |
| Listar archivos | `ls` o equivalente |
| Cambiar de carpeta | `cd nombre_carpeta` |

Supongamos que tienes un archivo llamado `hola.py` dentro de tu carpeta de trabajo. Si abres la terminal en esa carpeta y ejecutas:

```bash
python hola.py
```

O, según tu sistema:

```bash
python3 hola.py
```

El intérprete leerá el archivo y ejecutará las instrucciones que contiene.

### Abrir la terminal

Puedes abrir la terminal desde tu sistema operativo o usar la terminal integrada de Visual Studio Code.

[IMAGEN: Terminal integrada abierta en Visual Studio Code]

### Verificar en qué carpeta estás

Antes de ejecutar un archivo, conviene comprobar que la terminal está ubicada en la carpeta correcta. En algunos sistemas puedes usar:

```bash
pwd
```

o un comando equivalente para mostrar la ruta actual.

### Revisar los archivos disponibles

También puedes listar los archivos de la carpeta actual para comprobar que `hola.py` está ahí. En algunos sistemas puedes usar:

```bash
ls
```

o un comando equivalente.

### Ejecutar el archivo

Si el archivo está en la carpeta correcta, ejecútalo con:

```bash
python hola.py
```

o:

```bash
python3 hola.py
```

Si todo está correcto, el mensaje del programa aparecerá en pantalla.

:::caution[Error frecuente]
Un error frecuente es intentar ejecutar un archivo desde una carpeta distinta a aquella donde está guardado. Cuando eso ocurre, la terminal no encuentra el archivo y muestra un mensaje de error. También es frecuente usar `python` cuando el sistema requiere `python3`, o escribir mal el nombre del archivo.
:::

### Interpretar la salida

Cuando ejecutas un script desde la terminal, la salida del programa se muestra directamente allí. Esto permite verificar rápidamente si el programa funcionó o si apareció algún error.

[IMAGEN: Terminal mostrando la ejecución correcta de `hola.py`]

## ¿Por qué es importante usar la terminal?

Trabajar con la terminal permite comprender mejor la relación entre:

- El archivo que escribes
- La carpeta donde está guardado
- El intérprete que ejecuta el programa
- Y la salida que aparece en pantalla

Esta relación es importante porque muchas tareas de programación dependen de ejecutar comandos de forma explícita.

:::tip[Buena práctica]
Antes de ejecutar un archivo, verifica siempre su nombre y la carpeta en la que te encuentras.
:::

## Mini práctica

Realiza las siguientes acciones:

1. Abre la terminal integrada de Visual Studio Code.
2. Comprueba en qué carpeta te encuentras.
3. Verifica que el archivo `hola.py` esté disponible.
4. Ejecuta el archivo con `python hola.py` o `python3 hola.py`.
5. Observa el resultado que aparece en pantalla.
