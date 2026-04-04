---
title: Tipos de datos
description: Tipos de datos básicos en Python y su uso en variables simples.
slug: fundamentos/variables/tipos-de-datos
sidebar:
  label: Tipos de datos
  order: 2
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya reconoces qué es una variable.
- Sabes escribir asignaciones simples en Python.
- Puedes usar `print()` para mostrar valores en pantalla.
:::

## Objetivo

Reconocer los tipos de datos básicos en Python y utilizarlos en variables simples.

## Concepto clave

Un tipo de dato indica la clase de valor que una variable almacena y determina cómo puede usarse dentro de un programa.

## ¿Qué son los tipos de datos?

Cuando una variable almacena información, esa información no siempre tiene la misma forma.  
Por ejemplo, no es lo mismo guardar:

- Un número entero
- Un número con decimales
- Un texto
- Un valor lógico

Python distingue estas clases de valores mediante **tipos de datos**.

Reconocer el tipo de dato de un valor es importante porque permite escribir programas más claros y entender mejor qué operaciones pueden realizarse con cada variable.

## Tipos de datos básicos en Python

En esta etapa trabajaremos con cuatro tipos de datos fundamentales:

| Tipo | Ejemplo | Descripción general |
|---|---|---|
| `int` | `18` | Número entero, sin decimales |
| `float` | `3.5` | Número con parte decimal |
| `str` | `"Hola"` | Texto |
| `bool` | `True` | Valor lógico: verdadero o falso |

Observa las siguientes variables:

```python
edad = 18
estatura = 1.72
nombre = "Ada"
activo = True
```

En este ejemplo:

- `edad` almacena un valor de tipo `int`
- `estatura` almacena un valor de tipo `float`
- `nombre` almacena un valor de tipo `str`
- `activo` almacena un valor de tipo `bool`

### Números enteros: `int`

Los valores de tipo `int` representan números enteros, es decir, números sin parte decimal.

```python
cantidad = 5
anio = 2026
temperatura = -3
```

Este tipo de dato se usa cuando no se necesita representar decimales.

### Números con decimales: `float`

Los valores de tipo `float` representan números que incluyen parte decimal.

```python
precio = 19.99
promedio = 5.4
pi = 3.14
```

Este tipo de dato se usa cuando el valor puede tener fracciones o decimales.

### Texto: `str`

Los valores de tipo `str` representan cadenas de texto. Para que Python reconozca un texto, este debe escribirse entre comillas simples (`'`) o dobles (`"`).

```python
nombre = "Ada"
mensaje = "Hola"
ciudad = "Santiago"
```

Para que Python reconozca un texto, este debe escribirse entre comillas.

### Valores lógicos: `bool`

Los valores de tipo `bool` representan una condición lógica. Solo pueden tomar dos valores: `True` y `False`.

```python
encendido = True
aprobado = False
```

:::caution[Error frecuente]
Un error frecuente confundir `True` y `False` con texto. En Python, `True` y `False` son valores lógicos y deben escribirse sin comillas y con mayúscula inicial.
:::

Este tipo de dato será muy importante más adelante cuando trabajemos con condiciones y estructuras de control.

## ¿Cómo reconocer el tipo de un valor?

Python permite consultar el tipo de un valor con la función `type()`. Por ejemplo:

```python
print(type(18))
print(type(3.5))
print(type("Hola"))
print(type(True))
```

La salida mostrará el tipo correspondiente a cada valor:

```
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
```

:::note[Idea clave]
Reconocer el tipo de un dato ayuda a entender cómo puede utilizarse dentro de un programa.
:::

## Diferencia entre número y texto

Observa esta diferencia:

```python
edad = 18
edad_texto = "18"
```

Aunque ambos ejemplos parecen representar lo mismo, no corresponden al mismo tipo de dato.

- `18` es un número entero
- `"18"` es un texto

Esta diferencia es importante porque un número y un texto no se comportan igual dentro de un programa.

:::caution[Error frecuente]
Un error frecuente es pensar que un valor numérico escrito entre comillas sigue siendo un número. En Python, si un valor está entre comillas, se interpreta como texto.
:::

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Crea una variable con un número entero.
2. Crea una variable con un número decimal.
3. Crea una variable con un texto.
4. Crea una variable con un valor lógico.
5. Usa `print()` para mostrar cada variable.
6. Usa `type()` para observar el tipo de cada una.
