---
title: Comparación
description: Operadores de comparación en Python para relacionar valores y obtener resultados lógicos.
slug: fundamentos/operadores/comparacion
sidebar:
  label: Comparación
  order: 3
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya conoces los tipos de datos básicos en Python.
- Sabes usar variables en expresiones simples.
- Ya trabajaste con operadores aritméticos y expresiones numéricas.
:::

## Objetivo

Aplicar operadores de comparación en Python para relacionar valores y obtener resultados lógicos.

## Concepto clave

Los operadores de comparación permiten contrastar dos valores y producir un resultado lógico: `True` o `False`.

## ¿Qué son los operadores de comparación?

En programación, muchas decisiones dependen de comparar valores. Por ejemplo, podríamos querer saber:

- Si una edad es mayor que 18
- Si dos números son iguales
- Si una cantidad es distinta de otra
- Si un valor es mayor o menor que otro

Para realizar este tipo de comprobaciones, Python utiliza operadores de comparación.

## Operadores de comparación

Al igual que en matemáticas, Python tiene símbolos específicos para comparar valores. Estos operadores son:

| Operador | Significado | Ejemplo | Resultado |
|---|---|---|---|
| `==` | igual que | `5 == 5` | `True` |
| `!=` | distinto de | `5 != 3` | `True` |
| `>` | mayor que | `8 > 2` | `True` |
| `<` | menor que | `2 < 8` | `True` |
| `>=` | mayor o igual que | `5 >= 5` | `True` |
| `<=` | menor o igual que | `4 <= 7` | `True` |

```python
print(5 == 5)
print(5 != 3)
print(8 > 2)
print(2 < 8)
```

Salida esperada:

```
True
True
True
True
```

Cada comparación produce un resultado lógico:

- `True` cuando la comparación se cumple.
- `False` cuando no se cumple.

### Igualdad: `==`

El operador `==` permite comprobar si dos valores son iguales.

```python
print(10 == 10)
print(10 == 5)
```

Este operador se usa cuando queremos verificar si dos valores coinciden. Si ambos valores son iguales, el resultado es `True`. Si son distintos, el resultado es `False`. Salida esperada:

```
True
False
```

### Diferencia: `!=`

El operador `!=` permite comprobar si dos valores son distintos.

```python
print(8 != 4)
print(8 != 8)
```

Si los valores son distintos, el resultado es `True`. Si son iguales, el resultado es `False`. Salida esperada:

```
True
False
```

### Mayor que y menor que

Los operadores `>` y `<` comparan magnitudes.

```python
print(9 > 3)
print(2 < 1)
```

Cuando el primer valor es mayor que el segundo, el resultado es `True`. Cuando el primer valor es menor que el segundo, el resultado es `True`. En caso contrario, el resultado es `False`. Salida esperada:

```
True
False
```

### Mayor o igual, menor o igual

Los operadores `>=` y `<=` permiten comparar incluyendo la igualdad.

```python
print(7 >= 7)
print(4 <= 2)
```

Cuando el primer valor es mayor o igual que el segundo, el resultado es `True`. Cuando el primer valor es menor o igual que el segundo, el resultado es `True`. En caso contrario, el resultado es `False`. Salida esperada:

```
True
False
```

## Comparaciones con variables

Los operadores de comparación también pueden aplicarse a variables.

```python
edad = 18
print(edad >= 18)

puntaje = 5
print(puntaje < 4)
```

Salida esperada:

```
True
False
```

La comparación no cambia porque se use una variable. Python toma el valor almacenado y realiza la evaluación correspondiente.

En el primer caso, `edad` es igual a 18, por lo que la comparación `edad >= 18` es `True`. En el segundo caso, `puntaje` es 5, que no es menor que 4, por lo que la comparación `puntaje < 4` es `False`. Es importante considerar que:

- El resultado de una comparación no es un número ni un texto.  
- Es un valor lógico de tipo `bool`.

```python
resultado = 5 > 2
print(resultado)
print(type(resultado))
```

Salida esperada:

```
True
<class 'bool'>
```

:::note[Idea clave]
Toda comparación en Python produce un valor lógico: `True` o `False`.
:::

## Comparar números y textos

Python puede comparar números entre sí y textos entre sí, pero no siempre es correcto mezclar tipos distintos en una misma comparación.

```python
print(5 == "5")
```

Salida esperada:

```
False
```

Aunque ambos valores parecen similares, no corresponden al mismo tipo de dato.

- `5` es un número entero;
- `"5"` es un texto.

:::caution[Error frecuente]
Un error frecuente es confundir `=` con `==`. En Python, `=` se usa para asignar valores a una variable, mientras que `==` se usa para comparar si dos valores son iguales.

También es frecuente comparar un número con un texto pensando que Python los interpretará como equivalentes.
:::

## Mini práctica

Escribe y prueba las siguientes comparaciones:

1. `7 == 7`
2. `7 != 5`
3. `10 > 3`
4. `2 < 1`
5. `8 >= 8`
6. `4 <= 6`

Luego prueba con variables:

1. Crea una variable `edad` con valor `16`
2. Compara si `edad >= 18`
3. Crea una variable `precio` con valor `2500`
4. Compara si `precio < 3000`
