---
title: Errores comunes
description: Errores frecuentes al comenzar a programar en Python y cómo identificarlos.
slug: introduccion/primeros-pasos/errores-comunes
sidebar:
  label: Errores comunes
  order: 4
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Python ya está instalado en tu equipo.
- Visual Studio Code ya está instalado.
- Ya lograste crear y ejecutar un archivo `.py` simple.
:::

## Objetivo

Identificar errores frecuentes al comenzar a trabajar con Python y reconocer formas básicas de revisarlos y corregirlos.

## Concepto clave

Un error es una situación en la que el programa no puede ejecutarse correctamente o no produce el resultado esperado.

## ¿Por qué aparecen errores?

Al comenzar a programar, es normal cometer errores al escribir instrucciones, guardar archivos o ejecutar comandos. En muchos casos, el problema no está en la idea general del programa, sino en pequeños detalles de escritura, ubicación del archivo o uso de la terminal.

Reconocer estos errores desde el inicio permite trabajar de forma más ordenada y comprender mejor cómo responde Python ante una instrucción incorrecta.

:::note[Idea clave]
En programación, detectar un error es parte del proceso normal de trabajo. Lo importante es aprender a leerlo y revisar su causa.
:::

## Tipos de errores frecuentes

| Tipo de error | Qué suele ocurrir |
|---|---|
| Error de sintaxis | La instrucción está mal escrita y Python no puede interpretarla. |
| Error de nombre | Se escribe mal el nombre de una función, variable o archivo. |
| Error de ejecución | El programa se intenta ejecutar en una condición incorrecta, por ejemplo desde una carpeta equivocada. |
| Error lógico | El programa se ejecuta, pero el resultado no es el esperado. |

### Falta una comilla

Observa este caso:

```bash
print("Hola)
```

Aquí falta una comilla de cierre. Python no puede interpretar correctamente el texto y genera un error.

Correcto:

```bash
print("Hola")
```

### Falta un paréntesis

Observa este caso:

```bash
print("Hola"
```

Aquí falta el paréntesis de cierre.

Correcto:

```bash
print("Hola")
```

### Nombre mal escrito

Observa este caso:

```bash
prnt("Hola")
```

Python no reconoce `prnt`, porque el nombre correcto es `print`.

Correcto:

```bash
print("Hola")
```

### Archivo no encontrado

Si escribes en la terminal:

```bash
python hola.py
```

pero el archivo no está en la carpeta actual, la terminal indicará que no puede encontrarlo.

Esto suele ocurrir cuando:

- El archivo no fue guardado
- El nombre del archivo no coincide exactamente
- La terminal está ubicada en otra carpeta

[IMAGEN: Terminal mostrando un error por archivo no encontrado]

## Cómo revisar un error

### Leer con atención el mensaje

Cuando Python o la terminal muestran un error, conviene leer el mensaje completo antes de modificar el código.

[IMAGEN: Terminal mostrando un mensaje de error]

### Revisar la línea donde ocurre el problema

En muchos casos, el error está en la misma línea indicada por el sistema o muy cerca de ella.

[IMAGEN: Terminal mostrando la línea donde ocurre el error]

### Comprobar signos y nombres

Conviene revisar especialmente:

- Comillas
- Paréntesis
- Nombre de funciones
- Nombre de archivos
- Ubicación en la terminal

### Ejecutar nuevamente

Después de corregir el problema, vuelve a ejecutar el programa para comprobar si el error fue resuelto.

:::caution[Error frecuente]
Un error frecuente es corregir el código sin leer con atención el mensaje que aparece en la terminal o en el editor. Esto puede hacer que el problema continúe aunque se cambien otras partes del archivo.
:::

## ¿Qué conviene revisar primero?

Cuando aparezca un error, revisa en este orden:

1. Si el archivo fue guardado.
2. Si el nombre del archivo está bien escrito.
3. Si la terminal está en la carpeta correcta.
4. Si faltan comillas o paréntesis.
5. Si escribiste correctamente la instrucción.

:::tip[Buena práctica]
Cuando un programa no funciona, comienza revisando los detalles más simples. Muchas veces el error está en un signo, una letra o la ubicación del archivo.
:::

## Mini práctica

Realiza las siguientes acciones:

1. Escribe `print("Hola)` y observa qué ocurre.
2. Corrige el error y vuelve a ejecutar el archivo.
3. Escribe `prnt("Hola")` y observa qué ocurre.
4. Corrige el nombre y vuelve a ejecutar.
5. Intenta ejecutar un archivo desde una carpeta incorrecta y revisa el mensaje que aparece.
