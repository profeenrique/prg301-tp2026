---
title: Sintaxis básica
description: Elementos básicos de la sintaxis de Python para escribir instrucciones correctas.
slug: introduccion/primeros-pasos/sintaxis-basica
sidebar:
  label: Sintaxis básica
  order: 2
---

:::note[Verificación previa]
Antes de continuar, comprueba lo siguiente:

- Python ya está instalado en tu equipo.
- Visual Studio Code ya está instalado.
- Ya lograste ejecutar un archivo `.py` simple.
:::

## Objetivo

Reconocer elementos básicos de la sintaxis de Python y escribir instrucciones simples de forma correcta.

## Concepto clave

La sintaxis es el conjunto de reglas que indica cómo debe escribirse un programa para que el intérprete pueda leerlo y ejecutarlo correctamente.

## ¿Qué significa sintaxis?

Cuando escribimos un programa, no basta con tener una idea clara de lo que queremos hacer. También es necesario escribir las instrucciones con una forma válida.

En Python, la sintaxis define aspectos como:

- El uso de paréntesis
- El uso de comillas para escribir texto
- La forma correcta de llamar funciones
- La escritura ordenada de las instrucciones
- La indentación en los bloques de código

Si una instrucción no respeta estas reglas, el programa puede producir un error. Observa esta instrucción:

```python
print("Hola")
```

Esta línea es válida porque:

- La función `print` está escrito correctamente
- Los paréntesis están completos
- El texto está entre comillas

### La instrucción debe estar bien escrita

Python distingue entre nombres correctos e incorrectos. Por ejemplo:

```python
print("Hola")
```

no es lo mismo que:

```python
prnt("Hola")
```

Si el nombre está mal escrito, Python no reconocerá la instrucción.

### Los paréntesis deben abrirse y cerrarse

En Python, muchas funciones utilizan paréntesis. Si falta uno, la instrucción queda incompleta.

Correcto:

```python
print("Hola")
```

Incorrecto:

```python
print("Hola"
```

### El texto debe ir entre comillas

Cuando queremos mostrar texto, debemos escribirlo entre comillas simples o dobles.

Correcto:

```python
print("Hola")
print('Hola')
```

Incorrecto:

```python
print(Hola)
```

En el ejemplo incorrecto, Python intentará interpretar `Hola` como si fuera un nombre y no como texto.

### Escribir con claridad

En programas simples, cada línea suele contener una instrucción clara. Esto facilita la lectura y reduce errores. Por ejemplo:

```python
print("Hola")
print("Bienvenida")
```

## Elementos básicos

En una instrucción simple como `print("Hola")`, podemos identificar los siguientes elementos:

| Elemento | Función |
|---|---|
| `print` | Muestra información en pantalla |
| `()` | Delimitan argumentos en una función |
| `""` o `''` | Indican texto |
| `.py` | Extensión de un archivo de Python |

:::caution[Error frecuente]
Un error frecuente es olvidar las comillas o los paréntesis al escribir una instrucción con `print()`. Cuando esto ocurre, Python no puede interpretar correctamente la línea y genera un error. También es frecuente escribir mal el nombre de la función.
:::

## Mini práctica

Escribe y prueba las siguientes instrucciones:

1. Muestra el texto `Hola`.
2. Muestra tu nombre.
3. Muestra una frase breve de tu elección.

Luego revisa qué ocurre si:

- Quitas una comilla
- Quitas un paréntesis
- Escribes mal `print`

