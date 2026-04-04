---
title: ¿Qué es una variable?
description: Concepto de variable en Python y su uso para almacenar información.
slug: fundamentos/variables/que-es-una-variable
sidebar:
  label: ¿Qué es una variable?
  order: 1
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Puedes crear y ejecutar archivos `.py`.
- Ya conoces la estructura básica de una instrucción en Python.
- Sabes usar `print()` para mostrar información en pantalla.
:::

## Objetivo

Reconocer qué es una variable en Python y utilizarla para almacenar información en programas simples.

## Concepto clave

Una variable es un nombre que referencia un valor almacenado en memoria y que puede utilizarse posteriormente dentro de un programa.

## ¿Qué es una variable?

Cuando escribimos un programa, muchas veces necesitamos guardar información para usarla más adelante. Por ejemplo:

- Un nombre
- Una edad
- Un precio
- Un resultado de un cálculo

En Python, esa información puede almacenarse en **variables**.

Una variable permite asociar un nombre con un valor. Después de esa asignación, el programa puede volver a usar ese valor mediante el nombre elegido.

:::note[Idea clave]
Una variable no es el valor en sí mismo. Es el nombre que permite acceder a ese valor dentro del programa.
:::

## Ejemplo básico

Observa este ejemplo:

```python
nombre = "Ada"
```

Aquí ocurre lo siguiente:

- `nombre` es el nombre de la variable
- `=` es el operador de asignación
- `"Ada"` es el valor asignado

Después de esa línea, el programa puede usar `nombre` para referirse a ese dato.

## Explicación paso a paso

### 1. Elegir un nombre para la variable

El primer paso consiste en escribir un nombre que permita identificar la información que se almacenará.

Por ejemplo:

```python
nombre
```

### 2. Usar el operador de asignación

En Python, el símbolo `=` se utiliza para asignar un valor a una variable.

Por ejemplo:

```python
nombre = "Ada"
```

Esto no significa “igualdad” en sentido matemático.  
Significa que el valor de la derecha queda asociado al nombre de la izquierda.

### 3. Utilizar la variable

Una vez creada, la variable puede utilizarse en otras instrucciones. Por ejemplo:

```python
nombre = "Ada"
print(nombre)
```

En este caso, Python mostrará el valor almacenado en la variable.

### 4. Cambiar el valor de una variable

El valor de una variable puede reemplazarse por otro. Por ejemplo:

```python
nombre = "Ada"
nombre = "Guido"
print(nombre)
```

El programa mostrará `Guido`, porque ese fue el último valor asignado.

## Nombrar variables

En Python, conviene seguir estas reglas al nombrar variables:

- Usar nombres claros
- Evitar espacios
- No comenzar con números
- No usar caracteres especiales innecesarios
- Preferir palabras en minúscula separadas por guion bajo cuando el nombre tiene más de una palabra

Ejemplos válidos:

```python
edad
nombre_usuario
precio_final
```

Ejemplos inválidos:

```python
2nombre
nombre usuario
precio-final
```

:::tip[Buena práctica]
Elige nombres que ayuden a comprender el propósito de la variable. Un nombre claro facilita la lectura del programa.
:::

## ¿Qué significa asignar?

En programación, **asignar** significa dar un valor a una variable.

Por ejemplo:

```python
edad = 18
```

Aquí se asigna el valor `18` a la variable `edad`.

Esta idea es fundamental, porque gran parte de la programación consiste en almacenar, actualizar y reutilizar información.

## Diferencia entre variable y texto

Observa estos dos ejemplos:

```python
nombre = "Ada"
print(nombre)

print("nombre")
```

En el primer caso, Python muestra el valor almacenado en la variable `nombre`.  
En el segundo caso, Python muestra el texto literal `"nombre"`.

Esta diferencia es importante porque una variable y un texto no cumplen la misma función.

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Crea una variable llamada `nombre` y asígnale tu nombre.
2. Muestra el valor de esa variable con `print()`.
3. Crea una variable llamada `edad` y asígnale un número.
4. Muestra ambas variables en pantalla.
5. Cambia el valor de una de ellas y vuelve a ejecutar el programa.

:::caution[Error frecuente]
Un error frecuente es pensar que el símbolo `=` significa exactamente lo mismo que en matemáticas. En Python, ese símbolo se usa para asignar un valor a una variable. También es frecuente escribir nombres poco claros o intentar usar espacios dentro del nombre de una variable.
:::