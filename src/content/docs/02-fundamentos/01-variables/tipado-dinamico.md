---
title: Tipado dinámico
description: Forma en que Python asigna tipos a los valores sin requerir una declaración previa.
slug: fundamentos/variables/tipado-dinamico
sidebar:
  label: Tipado dinámico
  order: 3
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya reconoces qué es una variable.
- Ya conoces los tipos de datos básicos en Python.
- Sabes asignar valores simples a una variable.
:::

## Objetivo

Reconocer cómo funciona el tipado dinámico en Python y observar sus implicancias en el uso de variables.

## Concepto clave

Python es un lenguaje de tipado dinámico, lo que significa que el tipo de un valor se determina automáticamente en el momento de la asignación, sin necesidad de declararlo antes.

## ¿Qué significa tipado dinámico?

En algunos lenguajes de programación, antes de usar una variable es necesario indicar explícitamente qué tipo de dato almacenará.

En Python, eso no es necesario. Cuando asignas un valor a una variable, Python reconoce automáticamente su tipo según el valor entregado. Por ejemplo:

```python
edad = 18
nombre = "Ana"
activo = True
```

En estos casos, Python identifica por sí mismo que:

- `edad` almacena un entero
- `nombre` almacena un texto
- `activo` almacena un valor lógico

Observa este ejemplo:

```python
dato = 10
print(type(dato))
```

Si luego escribes:

```python
dato = "Hola"
print(type(dato))
```

La misma variable pasa a contener un valor de otro tipo. Esto ocurre porque en Python el nombre de la variable no queda ligado de forma permanente a un único tipo de dato.

## Una misma variable para distintos valores

En Python, una variable puede cambiar de valor y también de tipo durante la ejecución del programa. Por ejemplo:

```python
valor = 25
print(type(valor))

valor = 3.14
print(type(valor))

valor = "Python"
print(type(valor))
```

En cada asignación, Python reconoce el tipo del nuevo valor. El resultado de este código sería:

```python
<class 'int'>
<class 'float'>
<class 'str'>
```

:::note[Idea clave]
En Python, el tipo se asocia al valor asignado en cada momento, no al nombre de la variable de forma permanente.
:::

### ¿Por qué esto es útil?

El tipado dinámico permite escribir programas con mayor flexibilidad, ya que no es necesario declarar tipos antes de comenzar a trabajar con variables. Esto facilita:

- Escribir código de forma más directa.
- Probar ejemplos simples con rapidez.
- Concentrarse en la lógica del problema sin agregar declaraciones adicionales.

### ¿Qué cuidado requiere?

Aunque el tipado dinámico hace que Python sea más flexible, también exige atención. Si una variable cambia de tipo y el programa espera otro tipo de valor, pueden aparecer errores o resultados no deseados. Por ejemplo:

```python
dato = "10"
print(dato + 5)
```

En este caso, Python genera un error porque `"10"` es un texto y `5` es un número entero, y no se pueden sumar directamente.

```
TypeError: can only concatenate str (not "int") to str
```

## Diferencia entre flexibilidad y desorden

El hecho de que Python permita cambiar el tipo de una variable no significa que convenga hacerlo sin una razón clara.

```python
dato = 10
dato = "Hola"
dato = True
```

Este código es válido, pero si se usa sin cuidado puede dificultar la lectura y comprensión del programa.

:::tip[Buena práctica]
Aunque Python permite cambiar el tipo de una variable, conviene usar nombres claros y mantener coherencia en los valores asignados.
:::

## Relación con `type()`

La función `type()` permite observar el tipo del valor que una variable contiene en un momento determinado.

```python
dato = 8
print(type(dato))

dato = "ocho"
print(type(dato))
```

Esto ayuda a comprobar cómo Python interpreta cada valor asignado a la variable.

```
<class 'int'>
<class 'str'>
```

:::caution[Error frecuente]
Un error frecuente es pensar que una variable conserva siempre el mismo tipo de dato. En Python, el tipo puede cambiar si se asigna un valor de otra clase.

También es frecuente suponer que la flexibilidad del lenguaje elimina la necesidad de mantener orden y coherencia al escribir código.
:::

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Crea una variable llamada `dato` y asígnale un número entero.
2. Muestra su tipo con `type()`.
3. Asigna a la misma variable un texto.
4. Vuelve a mostrar su tipo.
5. Asigna un valor lógico y vuelve a comprobar el tipo.