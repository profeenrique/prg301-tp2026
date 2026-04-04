---
title: Aritméticos
description: Operadores aritméticos básicos en Python para realizar cálculos simples.
slug: fundamentos/operadores/aritmeticos
sidebar:
  label: Aritméticos
  order: 1
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya reconoces los tipos de datos numéricos básicos en Python.
- Sabes crear variables y asignarles valores.
- Ya conoces la conversión de tipos en ejemplos simples.
:::

## Objetivo

Aplicar operadores aritméticos básicos en Python para realizar cálculos simples con variables y valores numéricos.

## Concepto clave

Los operadores aritméticos permiten realizar operaciones matemáticas con números dentro de un programa.

## Operadores aritméticos en Python

Cuando un programa necesita calcular un resultado, comparar cantidades o transformar datos numéricos, utiliza operadores. En Python, los operadores aritméticos permiten trabajar con:

| Operador | Nombre | Ejemplo | Resultado |
|---|---|---|---|
| `+` | Suma | `4 + 2` | `6` |
| `-` | Resta | `4 - 2` | `2` |
| `*` | Multiplicación | `4 * 2` | `8` |
| `/` | División | `4 / 2` | `2.0` |
| `//` | División entera | `5 // 2` | `2` |
| `%` | Módulo o resto | `5 % 2` | `1` |
| `**` | Potencia | `2 ** 3` | `8` |

En Python, estos operadores pueden aplicarse tanto a valores literales como a variables que almacenan números.

```python
a = 10
b = 3 
print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

En este ejemplo, se aplican los operadores aritméticos sobre las variables `a` y `b`, que contienen números enteros. Salida esperada:

```
13
7
30
3.3333333333333335
```

Podemos observar que:

- `+` suma los valores
- `-` calcula la diferencia
- `*` multiplica
- `/` divide y devuelve un resultado decimal

### Suma y resta

La suma y la resta permiten combinar o comparar cantidades.

```python
precio = 1200
descuento = 300
print(precio - descuento)
print(precio + descuento)
```

Estas operaciones son útiles cuando se quiere calcular totales, diferencias o acumulaciones simples. Salida esperada:

```
900
1500
```

### Multiplicación

La multiplicación permite repetir una cantidad varias veces o calcular productos entre valores.

```python
cantidad = 4
precio_unitario = 2500

print(cantidad * precio_unitario)
```

Salida esperada:

```
10000
```

### División

La división con `/` siempre devuelve un resultado decimal, aunque la división sea exacta.

```python
print(8 / 2)
print(7 / 2)
```

Salida esperada:

```
4.0
3.5
```

:::note[Idea clave]
En Python, el operador `/` devuelve un valor de tipo `float`.
:::

### División entera

La división entera con `//` devuelve solo la parte entera del resultado.

```python
print(7 // 2)
print(9 // 4)
```

Esto puede ser útil cuando interesa trabajar con la parte entera de un cociente. Salida esperada:

```
3
2
```

### Resto o módulo

El operador `%` devuelve el resto de una división.

```python
print(7 % 2)
print(10 % 3)
```

Este operador es útil, por ejemplo, para saber si un número es par o impar. Salida esperada:

```
1
1
```

### Potencia

El operador `**` permite elevar un número a una potencia.

```python
print(2 ** 3)
print(5 ** 2)
```

Salida esperada:

```
8
25
```

## Operadores con variables

Los operadores aritméticos también pueden aplicarse directamente sobre variables.

```python
base = 5
altura = 3
area = base * altura

print(area)
```

Esto permite construir programas donde los cálculos dependen de los valores almacenados previamente. Salida esperada:

```
15
```

:::caution[Error frecuente]
Un error frecuente es confundir `/` con `//`. El primero devuelve un resultado decimal, mientras que el segundo devuelve solo la parte entera del cociente.

También es frecuente intentar operar con textos cuando el programa espera números.
:::

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Calcula la suma de dos números.
2. Calcula la resta entre dos valores.
3. Calcula el producto de dos números.
4. Divide dos valores con `/`.
5. Divide dos valores con `//`.
6. Calcula el resto de una división con `%`.
7. Eleva un número a una potencia con `**`.
