---
title: Lógicos
description: Operadores lógicos en Python para combinar comparaciones y construir expresiones booleanas.
slug: fundamentos/operadores/logicos
sidebar:
  label: Lógicos
  order: 4
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Ya conoces los operadores de comparación.
- Sabes que una comparación produce `True` o `False`.
- Puedes interpretar expresiones simples con variables.
:::

## Objetivo

Utilizar operadores lógicos en Python para combinar comparaciones y construir expresiones booleanas simples.

## Concepto clave

Los operadores lógicos permiten relacionar resultados booleanos para formar expresiones más complejas.

## ¿Qué son los operadores lógicos?

En muchos programas, una sola comparación no basta para tomar una decisión.

Por ejemplo, puede ser necesario comprobar si:

- Una edad es mayor o igual a 18 **y** menor que 60.
- Una clave es correcta **o** existe un código alternativo.
- Una condición **no** se cumple.

Para construir este tipo de expresiones, Python utiliza operadores lógicos.

| Operador | Lectura habitual | Función |
|---|---|---|
| `and` | y | Devuelve `True` solo si ambas condiciones son verdaderas |
| `or` | o | Devuelve `True` si al menos una condición es verdadera |
| `not` | no | Invierte el valor lógico de una expresión |

Un operador lógico se aplica a uno o más valores booleanos (`True` o `False`) y produce un resultado booleano. Por ejemplo:

```python
print(True and True)
print(True and False)
print(True or False)
print(not True)
```

Salida esperada:

```
True
False
True
False
```

Podemos observar que:

- `and` exige que ambas condiciones sean verdaderas
- `or` permite que una sola condición verdadera baste
- `not` invierte el valor lógico de una expresión.

### Operador `and`

El operador `and` se utiliza cuando dos condiciones deben cumplirse al mismo tiempo.

```python
edad = 20
print(edad >= 18 and edad < 60)
```

Salida esperada:

```
True
```

La expresión completa es verdadera porque:

- `edad >= 18` es `True`
- `edad < 60` también es `True`

Como ambas condiciones se cumplen, el resultado final es `True`.

### Operador `or`

El operador `or` se utiliza cuando basta con que una de las condiciones sea verdadera.

```python
nota = 3.5
recuperacion = True

print(nota >= 4.0 or recuperacion)
```

Aunque `nota >= 4.0` es `False`, la variable `recuperacion` contiene `True`.  
Por eso, la expresión completa resulta verdadera.

```
True
```

### Operador `not`

El operador `not` invierte el valor lógico de una expresión.

```python
activo = True
print(not activo)
```

Salida esperada:

```
False
```

Lo que ocurre es lo siguiente:
- Si el valor original es `True`, `not` lo transforma en `False`.  
- Si el valor original es `False`, `not` lo transforma en `True`.

## Tablas de verdad

Las tablas de verdad permiten observar cómo cambia el resultado de una expresión lógica según los valores de entrada.

### Conjunción (`and`)

La conjunción solo es verdadera cuando **ambas** expresiones son verdaderas.

| A | B | A and B |
|---|---|---|
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

### Disyunción (`or`)

La disyunción es verdadera cuando **al menos una** de las expresiones es verdadera.

| A | B | A or B |
|---|---|---|
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

### Negación (`not`)

La negación invierte el valor lógico de una expresión.

| A | not A |
|---|---|
| True | False |
| False | True |

:::note[Idea clave]
`and` restringe una condición, `or` la hace más flexible y `not` invierte su valor lógico.
:::

## Combinar comparaciones

Los operadores lógicos suelen usarse junto con operadores de comparación.

```python
edad = 17
permiso = True

print(edad >= 18 and permiso)
print(edad >= 18 or permiso)
```

Salida esperada:

```
False
True
```

Podemos observar que:

- En la primera expresión, `and` exige que ambas condiciones sean verdaderas.
- En la segunda, `or` permite que una sola condición verdadera haga verdadera toda la expresión.

:::caution[Error frecuente]
Un error frecuente es confundir `and` con `or`. El primero exige que ambas condiciones se cumplan, mientras que el segundo permite que solo una sea verdadera.

También es frecuente olvidar que `not` invierte el valor lógico de una expresión completa o de una variable.
:::

## Expresiones más claras con paréntesis

Cuando una expresión lógica combina varias comparaciones, los paréntesis pueden ayudar a leerla mejor.

```python
edad = 25
estudiante = False

print((edad >= 18 and edad < 30) or estudiante)
```

Aunque Python puede evaluar muchas expresiones sin paréntesis, agrupar partes de la condición mejora la claridad. Salida esperada

```
True
```

:::tip[Buena práctica]
Si una expresión lógica comienza a verse confusa, usa paréntesis para separar con claridad sus partes.
:::

## Mini práctica

Escribe y prueba las siguientes expresiones:

1. `True and False`
2. `True or False`
3. `not True`
4. `5 > 3 and 2 < 1`
5. `8 == 8 or 4 > 10`
6. `not (6 < 2)`

Luego prueba con variables:

1. crea una variable `edad` con valor `16`
2. crea una variable `autorizacion` con valor `True`
3. evalúa `edad >= 18 and autorizacion`
4. evalúa `edad >= 18 or autorizacion`

## Para seguir avanzando

En el siguiente bloque revisaremos la salida con `print()`, una función fundamental para mostrar información y observar resultados en pantalla.