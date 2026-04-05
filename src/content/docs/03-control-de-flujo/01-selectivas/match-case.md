---
title: Match case
description: Selección de casos en Python mediante la estructura match-case.
slug: control-de-flujo/selectivas/match-case
sidebar:
  label: Match case
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de comprender las estructuras `if` y `elif`, el uso de comparaciones y la importancia de la indentación en Python.
:::

En algunos problemas, el programa necesita comparar un mismo valor con varios casos posibles. En esas situaciones, escribir muchas condiciones seguidas con `if` y `elif` puede funcionar, pero no siempre resulta la forma más clara de expresar la idea. La estructura `match-case` ofrece una alternativa que, en ciertos contextos, vuelve la lectura más directa y ordenada.

## Objetivo

Comprender cómo utilizar la estructura `match-case` para seleccionar una acción según el valor o la forma de un dato en Python.

## Qué aporta `match`

La estructura `match-case` permite evaluar un valor y compararlo con distintos patrones. Cuando uno de esos patrones coincide, Python ejecuta el bloque asociado y detiene la revisión de los casos siguientes.

Esta forma de escribir el código resulta especialmente útil cuando se desea trabajar con:

- Opciones definidas de antemano
- Códigos o estados concretos
- Menús simples
- Valores que representan categorías conocidas

La forma general de la estructura es la siguiente:

~~~python
match valor:
    case patron_1:
        instruccion_1
    case patron_2:
        instruccion_2
    case _:
        instruccion_final
~~~

En esta escritura conviene reconocer cuatro elementos:

- `match` indica el inicio de la estructura
- `valor` corresponde al dato que se evaluará
- Cada `case` representa un patrón posible
- El bloque indentado contiene la acción asociada a cada caso

:::caution[Compatibilidad]
La estructura `match-case` está disponible desde Python 3.10. Si trabajas con una versión anterior, esta sintaxis no funcionará.
:::

## Un caso a la vez

Cuando Python encuentra una estructura `match`, evalúa el valor indicado y lo compara con los patrones escritos en los distintos `case`.

La idea central es sencilla:

- Python revisa los casos en orden
- Cuando encuentra el primer caso que coincide, ejecuta ese bloque
- Después de eso, no sigue evaluando los demás casos

Esta característica es importante, porque evita que se ejecuten varios bloques para un mismo valor.

## Cuando el mismo dato tiene varias opciones

Observa el siguiente ejemplo:

~~~python
opcion = 2

match opcion:
    case 1:
        print("Seleccionaste agregar")
    case 2:
        print("Seleccionaste editar")
    case 3:
        print("Seleccionaste eliminar")
~~~

Aquí, Python compara el valor de `opcion` con cada caso escrito:

- Primero revisa si `opcion` coincide con `1`
- Luego revisa si coincide con `2`
- Como ese caso sí coincide, ejecuta el bloque correspondiente

El resultado será:

~~~text
Seleccionaste editar
~~~

Este ejemplo muestra una diferencia importante respecto de una secuencia extensa de `if` y `elif`: la estructura se organiza alrededor de un solo dato y varios casos posibles.

## El comodín `_`

En muchos problemas conviene contemplar también un caso general para cualquier valor no previsto de forma explícita. Para eso se utiliza `_`.

~~~python
dia = 8

match dia:
    case 1:
        print("Lunes")
    case 2:
        print("Martes")
    case 3:
        print("Miércoles")
    case _:
        print("Valor fuera de rango")
~~~

En este ejemplo, si `dia` no coincide con ninguno de los primeros casos, Python ejecuta el bloque asociado a `_`.

:::tip[Idea clave]
El patrón `_` funciona como comodín. Coincide con cualquier valor y suele utilizarse como caso final.
:::

Esta organización ayuda a leer el código como una selección ordenada de posibilidades, en lugar de una cadena larga de comparaciones independientes.

## Cuándo conviene usarlo

`match-case` no reemplaza automáticamente a `if` o `elif`. Su utilidad aparece con más claridad cuando el problema gira en torno a un mismo dato que debe compararse con varios casos posibles.

Suele ser una buena opción cuando:

- Se analiza una opción ingresada por el usuario
- Se interpreta un código numérico o textual
- Se responde a un menú
- Se desea que la lectura del programa sea más directa

Si el problema depende de comparaciones como `mayor que`, `menor que` o condiciones combinadas, en muchos casos `if` y `elif` siguen siendo la opción más natural.

:::note[Una decisión de diseño]
Usar `match-case` tiene sentido cuando varios casos pertenecen a una misma selección. Si el problema se expresa mejor mediante condiciones, `if` y `elif` suelen ofrecer una solución más adecuada.
:::

La siguiente tabla resume el papel que cumple cada parte básica de `match-case`.

| Elemento | Función | Ejemplo |
| --- | --- | --- |
| `match` | Inicia la comparación de casos | `match opcion:` |
| `case` | Define un caso o patrón posible | `case 1:` |
| `_` | Actúa como comodín para cualquier otro caso | `case _:` |
| Bloque indentado | Contiene la acción que se ejecuta si hay coincidencia | `print("Seleccionaste editar")` |

## Un ejemplo cercano a un menú

Supongamos que un programa recibe una opción y debe responder según el número ingresado.

~~~python
opcion = int(input("Ingresa una opción: "))

match opcion:
    case 1:
        print("Ver perfil")
    case 2:
        print("Editar perfil")
    case 3:
        print("Cerrar sesión")
    case _:
        print("Opción no válida")
~~~

Aquí el proceso ocurre en varios pasos:

1. El programa solicita una opción al usuario
2. El dato se convierte a entero con `int()`
3. `match` compara ese valor con los casos disponibles
4. Se ejecuta solo el primer caso que coincide

Este patrón es muy útil en programas donde las acciones están claramente asociadas a opciones definidas.

:::caution[Conversión de datos]
Si el valor ingresado debe compararse como número, recuerda convertirlo antes de usar `match`. `input()` devuelve texto.
:::

## También puede trabajar con texto

La estructura `match-case` no se limita a valores numéricos. También puede utilizarse con cadenas de texto.

~~~python
comando = input("Escribe un comando: ")

match comando:
    case "guardar":
        print("Archivo guardado")
    case "abrir":
        print("Archivo abierto")
    case "salir":
        print("Programa finalizado")
    case _:
        print("Comando no reconocido")
~~~

Este tipo de escritura resulta útil cuando se desea asociar acciones claras a palabras específicas.

## Del concepto al código

Escribe un programa en Python que solicite al usuario un número del `1` al `4` y muestre un mensaje según la estación del año correspondiente.

### Requisitos

- Debe pedir un número usando `input()`
- Debe convertir el dato a `int`
- Debe usar `match-case`
- Debe contemplar un caso general para valores no válidos

### Sugerencia de equivalencias

- `1` → Verano
- `2` → Otoño
- `3` → Invierno
- `4` → Primavera

### Ejemplo de interacción

~~~text
Ingresa una opción: 3
Invierno
~~~

:::tip[Antes de escribir el código]
Piensa primero cuál será el valor que evaluará `match` y luego define con claridad qué acción corresponde a cada `case`.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta `match` dentro del capítulo de control de flujo y muestra ejemplos iniciales de uso.

- [Referencia del lenguaje: sentencia `match`](https://docs.python.org/3/reference/compound_stmts.html#the-match-statement)  
  Describe con mayor precisión técnica cómo funciona `match-case`, incluyendo patrones, comodines y reglas de evaluación.

- [Novedades de Python 3.10: Structural Pattern Matching](https://docs.python.org/3/whatsnew/3.10.html)  
  Explica la incorporación de esta estructura al lenguaje y ofrece contexto sobre su propósito general.