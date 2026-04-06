---
title: Entorno de trabajo
description: Qué es un entorno de trabajo en programación y por qué conviene prepararlo antes de comenzar a desarrollar programas.
slug: introduccion/entorno
sidebar:
  label: Entorno de trabajo
  order: 1
---

:::note[Idea previa]
Antes de instalar herramientas o ejecutar programas, conviene comprender qué elementos forman parte del entorno de trabajo que utilizaremos durante el curso.
:::

Antes de escribir un programa, hace falta algo más que conocer un lenguaje. También es necesario contar con un espacio técnico que permita trabajar con cierta continuidad: escribir archivos, ejecutarlos, revisar resultados y corregir errores. A ese conjunto de herramientas y condiciones básicas lo llamamos **entorno de trabajo**.

## Objetivo

Comprender qué es un entorno de trabajo en programación e identificar las herramientas básicas necesarias para comenzar a desarrollar programas en Python.

## Qué significa trabajar con un entorno

En programación, un entorno de trabajo no es un lugar físico, sino un conjunto de herramientas que permiten desarrollar código de forma ordenada. Su función no se limita a “tener dónde escribir”, sino a facilitar un proceso completo:

- Escribir instrucciones
- Guardar archivos
- Ejecutar programas
- Observar resultados
- Corregir errores
- Mantener el trabajo organizado

Dicho de otro modo, el entorno de trabajo es el punto de partida práctico desde el cual una persona programa.

:::note[Idea clave]
Un entorno de trabajo es el conjunto de herramientas y configuraciones que permiten escribir, ejecutar, probar y corregir programas de manera ordenada.
:::

## Tres piezas básicas

En esta unidad trabajaremos con tres herramientas principales. Cada una cumple una función distinta dentro del proceso de programación.

| Herramienta | Función principal |
|---|---|
| Python | Ejecutar programas escritos en este lenguaje. |
| Visual Studio Code | Escribir, editar y organizar archivos de código. |
| Terminal | Ejecutar comandos, abrir programas y verificar instalaciones. |

Más que herramientas aisladas, conviene pensarlas como partes de un mismo flujo de trabajo.

~~~mermaid
flowchart LR
    A[Escribir código en Visual Studio Code] --> B[Guardar archivo .py]
    B --> C[Ejecutar desde Python]
    C --> D[Observar salida o errores en la terminal]
~~~

Este recorrido muestra una idea importante: programar no consiste solo en redactar código dentro de un editor. También implica ejecutarlo, interpretar su salida y volver a corregirlo cuando sea necesario.

## Por qué conviene prepararlo bien

Cuando el entorno de trabajo está bien configurado, la atención puede centrarse en el aprendizaje del lenguaje y en la resolución de problemas. En cambio, si faltan herramientas o la configuración básica no funciona, aparecen dificultades técnicas que interrumpen el proceso desde el comienzo.

Contar con un entorno preparado permite, por ejemplo:

- Escribir código con mayor orden
- Ejecutar programas y revisar sus resultados
- Detectar errores con más facilidad
- Mantener archivos y carpetas organizados
- Avanzar con menos obstáculos técnicos al comenzar

Esto no convierte al entorno en un tema secundario. Al contrario, preparar bien estas herramientas forma parte del aprendizaje inicial de programar.

:::tip[Una idea importante]
Preparar el entorno de trabajo no es un trámite externo al curso. Es parte del proceso de comenzar a programar con mayor autonomía.
:::

## Qué papel cumple cada herramienta

Conviene entender con más precisión qué aporta cada una de estas piezas.

### Python

Python es el lenguaje con el que trabajarás, pero también es la herramienta que interpreta y ejecuta los programas que escribas. Por eso no basta con conocer su nombre: debe estar instalado y disponible en el equipo.

### Visual Studio Code

Visual Studio Code será el editor principal para escribir y organizar los archivos del curso. No “ejecuta Python” por sí solo, pero facilita mucho la escritura, lectura y corrección del código.

### Terminal

La terminal permite comunicarse con el sistema mediante comandos. En esta etapa será útil para comprobar instalaciones, desplazarse entre carpetas y ejecutar scripts simples.

Miradas en conjunto, estas tres herramientas forman el núcleo del entorno de trabajo inicial.

## Qué haremos en esta unidad

A continuación, el siguiente paso será preparar este entorno según el sistema operativo disponible en tu equipo. Por eso, revisa el instructivo que corresponda y continúa con la instalación de Python:

- [Instalación en Windows](./instalacion-windows)
- [Instalación en macOS](./instalacion-macos)
- [Instalación en Ubuntu](./instalacion-ubuntu)

Después de instalar Python, continúa con la configuración de [Visual Studio Code](./vs-code).

:::tip[Recomendación]
Sigue solo el instructivo correspondiente a tu sistema operativo. No es necesario revisar los pasos de instalación de otras plataformas.
:::