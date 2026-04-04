---
title: ¡Hola mundo!
description: Primer programa en Python y primera ejecución desde Visual Studio Code y la terminal.
slug: introduccion/primeros-pasos/hola-mundo
sidebar:
  label: ¡Hola mundo!
  order: 1
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:
- Python ya está instalado en tu equipo.
- Visual Studio Code ya está instalado.
- Puedes abrir una carpeta de trabajo en el editor.
:::

## Objetivo

Escribir, guardar y ejecutar un primer programa en Python para reconocer la estructura mínima de un script y verificar que el entorno de trabajo funciona correctamente.

## Concepto clave

Un programa en Python es un conjunto de instrucciones escritas en un archivo con extensión `.py`. Cuando ese archivo se ejecuta, el intérprete lee sus instrucciones y produce un resultado.

## Primer programa

Una forma clásica de comenzar a trabajar con un lenguaje de programación es escribir un programa muy simple que muestre un mensaje en pantalla.

En Python, esto puede hacerse con la función `print()`.

## Ejemplo básico

Crea un archivo llamado `hola.py` y escribe lo siguiente:

```python
print("¡Hola mundo!")
```

## Explicación paso a paso

### 1. Crear el archivo

Abre tu carpeta de trabajo en Visual Studio Code y crea un archivo nuevo llamado `hola.py`.

:::tip[Buena práctica]
El nombre del archivo debe terminar en `.py`, ya que esa extensión indica que se trata de un archivo de Python.
:::

### 2. Escribir la instrucción

Dentro del archivo, escribe:

```python
print("¡Hola mundo!")
```

Esta instrucción indica que el programa debe mostrar un mensaje en pantalla.

### 3. Guardar el archivo

Guarda el archivo antes de ejecutarlo. Si el archivo no se guarda, los cambios recientes no serán considerados al momento de ejecutar el programa.

### 4. Ejecutar el programa

Abre la terminal integrada de Visual Studio Code y ejecuta uno de estos comandos, según tu sistema:

```bash
python hola.py
```

o:

```bash
python3 hola.py
```

Si todo está correcto, deberías ver el mensaje en pantalla.

[IMAGEN: Archivo `hola.py` abierto en VS Code y terminal mostrando la salida del programa]

## ¿Qué hace `print()`?

La función `print()` permite enviar texto u otros valores a la salida estándar, normalmente la terminal.

En este primer ejemplo, el programa no realiza cálculos ni toma decisiones. Solo ejecuta una instrucción y finaliza.

## ¿Por qué este programa es importante?

Aunque este programa es simple, permite comprobar que el archivo fue creado correctamente, que Python puede ejecutarlo y que el mensaje aparece en pantalla.

- Confirma que el archivo fue guardado correctamente
- Verifica que Python puede ejecutar el script
- Muestra cómo aparece la salida en la terminal
- Permite modificar el mensaje y observar el cambio en la ejecución

:::note[Idea clave]
Este programa permite verificar que el archivo, el intérprete y la terminal están funcionando correctamente.
:::

## Mini práctica

Realiza las siguientes acciones:

1. Crea el archivo `hola.py`.
2. Escribe la instrucción `print("¡Hola mundo!")`.
3. Ejecuta el programa desde la terminal.
4. Cambia el mensaje por otro texto y vuelve a ejecutarlo.
5. Verifica que el resultado cambie en pantalla.

:::caution[Error frecuente]
Un error frecuente es escribir mal el nombre del archivo al ejecutarlo desde la terminal. Si el archivo se llama `hola.py`, el comando debe coincidir exactamente con ese nombre. También es frecuente olvidar las comillas o los paréntesis en la instrucción `print()`.
:::