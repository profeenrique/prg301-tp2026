---
title: Conversión de tipos
description: Transformación de valores entre tipos de datos básicos en Python.
slug: fundamentos/variables/conversion-de-tipos
sidebar:
  label: Conversión de tipos
  order: 4
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya reconoces los tipos de datos básicos en Python.
- Comprendes que una variable puede almacenar valores de distinto tipo.
- Sabes usar `print()` y `type()` en ejemplos simples.
:::

## Objetivo

Aplicar conversiones básicas de tipos en Python para transformar valores según lo que el programa necesita.

## Concepto clave

La conversión de tipos consiste en transformar un valor de un tipo de dato en otro, por ejemplo de texto a número o de número a texto.

## ¿Por qué es necesaria la conversión de tipos?

En muchos programas, los datos no siempre llegan en el formato que necesitamos. Por ejemplo:

- Un número puede estar escrito como texto
- Un valor numérico puede necesitar mostrarse como texto
- Un dato ingresado por teclado puede requerir transformación antes de usarse

Por esta razón, Python permite convertir valores entre ciertos tipos de datos.

## Conversiones básicas en Python

Python dispone de funciones que permiten realizar conversiones simples entre tipos de datos.

| Función | Uso general |
|---|---|
| `int()` | Convierte un valor a número entero |
| `float()` | Convierte un valor a número decimal |
| `str()` | Convierte un valor a texto |
| `bool()` | Convierte un valor a lógico |

Observa este caso:

```python
edad = "18"
edad_numero = int(edad)

print(edad)
print(type(edad))

print(edad_numero)
print(type(edad_numero))
```

Salida esperada:

```shell
18
<class 'str'>
18
<class 'int'>
```

Podemos observar que:

- `edad` contiene el texto `"18"`
- `edad_numero` contiene el número entero `18`
- El contenido se parece, pero el tipo de dato cambia

### Conversión a entero con `int()`

La función `int()` permite transformar un valor en un número entero, siempre que el contenido sea válido para esa conversión.

```python
numero = int("25")
print(numero)
print(type(numero))
```

Esta conversión es útil cuando un valor numérico está representado como texto.

```
25
<class 'int'>
```

### Conversión a decimal con `float()`

La función `float()` permite transformar un valor en un número decimal.

```python
precio = float("19.99")
print(precio)
print(type(precio))
```

Esta conversión es útil cuando se necesita trabajar con valores que incluyen decimales.

```
19.99
<class 'float'>
```

### Conversión a texto con `str()`

La función `str()` permite transformar un valor en texto.

```python
numero = 42
texto = str(numero)

print(texto)
print(type(texto))
```

Esto es útil cuando se necesita mostrar un valor dentro de un mensaje o unirlo con otros textos.

```
42
<class 'str'>
```

### Conversión a lógico con `bool()`

La función `bool()` transforma un valor en un resultado lógico.

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("Python"))
```

Salida esperada:

```
False
True
False
True
```

Podemos observar que:

- `0` se interpreta como `False`
- `1` se interpreta como `True`
- Una cadena vacía se interpreta como `False`
- Un texto con contenido se interpreta como `True`

## Conversión y entrada de datos

La conversión de tipos será especialmente importante cuando trabajemos con `input()`. Esto ocurre porque los datos ingresados por teclado se reciben como texto, incluso cuando parecen números.

```python
edad = input("Ingresa tu edad: ")
print(type(edad))
```

Salida esperada:

```
<class 'str'>
```

Si se necesita trabajar con ese dato como número, será necesario convertirlo. Por ejemplo:

```python
edad = int(input("Ingresa tu edad: "))
print(type(edad))
```

## Cuando la conversión falla

No todos los valores pueden convertirse automáticamente.

```python
numero = int("hola")
```

Python genera un error, porque `"hola"` no puede transformarse en un número entero.

:::caution[Error frecuente]
Un error frecuente es intentar convertir a número un texto que no representa un valor numérico válido.
:::

Por ejemplo, `"25"` sí puede convertirse, pero `"veinticinco"` no.

## Diferencia entre mostrar y convertir

Observa estos casos:

```python
numero = 10
print(numero)

texto = str(numero)
print(texto)
```

Salida esperada:

```
10
10
```

En ambos casos puede aparecer `10` en pantalla, pero el tipo interno no es el mismo:

- `numero` es un entero
- `texto` es una cadena de texto

Por eso, ver el mismo contenido en pantalla no significa que el tipo de dato sea igual.

:::tip[Buena práctica]
Cuando tengas dudas sobre el tipo de un valor, utiliza `type()` para comprobarlo.
:::

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Convierte el texto `"12"` a entero.
2. Convierte el texto `"3.5"` a decimal.
3. Convierte el número `20` a texto.
4. Comprueba el tipo de cada resultado con `type()`.
5. Intenta convertir `"hola"` a entero y observa qué ocurre.
