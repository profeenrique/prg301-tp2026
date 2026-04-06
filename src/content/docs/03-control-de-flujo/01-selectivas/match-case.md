---
title: Match case
description: Selección de casos en Python mediante la estructura match-case.
slug: control-de-flujo/selectivas/match-case
sidebar:
  label: Match case
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que comprendes las estructuras `if` y `elif`, sabes trabajar con comparaciones y valores lógicos, y reconoces la importancia de la indentación en Python.
:::

No todos los problemas se resuelven comparando condiciones distintas una tras otra. En algunos casos, el programa necesita mirar **un solo valor** y decidir qué hacer según una lista de opciones posibles. Cuando esa situación aparece, una cadena extensa de `if` y `elif` puede funcionar, pero no siempre ofrece la forma más clara de expresar la idea. La estructura `match-case` surge justamente como una manera más ordenada de representar esa selección.

## Objetivo

Comprender cómo `match-case` permite seleccionar una acción a partir de un valor y organizar con mayor claridad problemas que dependen de casos bien definidos.

## Cuando un valor abre varias opciones

Hay problemas en los que el programa no necesita preguntar “¿se cumple esta condición?” de muchas formas distintas, sino algo más concreto: “¿con cuál de estos casos coincide este valor?”.

Piensa en situaciones como estas:

- Una opción elegida en un menú
- Un código que representa un estado
- Un número asociado a una categoría
- Un comando escrito por la persona usuaria

En todos esos casos, el foco no está en comparar rangos o relaciones complejas, sino en revisar si un valor coincide con una alternativa específica. Ahí es donde `match-case` resulta especialmente útil.

## Qué hace `match-case`

La estructura `match-case` evalúa un valor y lo compara con distintos casos posibles. Cuando encuentra una coincidencia, ejecuta el bloque correspondiente y deja de revisar los demás.

~~~python
match valor:
    case patron_1:
        instruccion_1
    case patron_2:
        instruccion_2
    case _:
        instruccion_final
~~~

En esta forma general conviene distinguir cuatro elementos:

- `match` indica el inicio de la estructura de selección
- `valor` corresponde al dato que se evaluará
- cada `case` propone un caso o patrón posible
- el bloque indentado contiene la acción asociada a la coincidencia

:::note[Idea clave]
`match-case` organiza una selección a partir de un solo valor. El programa toma ese valor y revisa, en orden, con cuál de los casos definidos coincide.
:::

## Cómo recorre los casos

Cuando Python encuentra una estructura `match`, no ejecuta todos los `case`. Los revisa uno a uno, en el orden en que fueron escritos, hasta encontrar el primero que coincide.

~~~mermaid
flowchart TD
    A[Evaluar valor] --> B{¿Coincide con el primer case?}
    B -->|Sí| C[Ejecutar bloque correspondiente]
    B -->|No| D{¿Coincide con el siguiente case?}
    D -->|Sí| E[Ejecutar bloque correspondiente]
    D -->|No| F[Seguir revisando otros casos]
~~~

Esta lógica es importante porque muestra que `match-case` no es una colección de bloques independientes. Es una sola estructura de selección, y por eso el orden de los casos también influye en cómo se lee y se organiza el código.

## Un valor, varios casos

Una forma simple de ver esta idea consiste en trabajar con una variable que representa una opción.

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

Aquí Python compara el valor de `opcion` con cada uno de los casos escritos.

- Primero revisa si coincide con `1`
- Luego revisa si coincide con `2`
- Como ahí encuentra coincidencia, ejecuta ese bloque y termina la revisión

~~~text
Seleccionaste editar
~~~

Este ejemplo permite notar una diferencia importante respecto de una secuencia larga de `if` y `elif`: el código se organiza alrededor de **un solo dato** y de una lista de posibilidades claramente delimitadas.

## Cuando ningún caso coincide

En muchos problemas no basta con definir solo los casos esperados. También conviene contemplar qué ocurrirá si el valor no coincide con ninguno de ellos. Para eso suele utilizarse `_`, que actúa como comodín.

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

En este ejemplo, como `dia` no coincide con ninguno de los primeros casos, Python ejecuta el bloque asociado a `_`.

:::tip[Comodín útil]
El patrón `_` suele utilizarse como caso final para capturar cualquier valor que no haya coincidido antes con un `case` explícito.
:::

Su presencia mejora la robustez del programa, porque evita dejar situaciones sin respuesta y hace más explícito qué debe ocurrir cuando aparece un valor no previsto.

## Qué parte cumple cada elemento

A estas alturas conviene mirar la estructura con un poco más de detalle. No se trata solo de saber “qué hace”, sino de entender cómo se organiza.

| Elemento | Función | Ejemplo |
| --- | --- | --- |
| `match` | Inicia la selección a partir de un valor | `match opcion:` |
| `case` | Propone una coincidencia posible | `case 1:` |
| `_` | Captura cualquier otro caso no previsto | `case _:` |
| Bloque indentado | Indica la acción que se ejecutará si hay coincidencia | `print("Seleccionaste editar")` |

Mirada de este modo, la estructura se vuelve más clara: `match` define el valor que se examina, cada `case` propone una posibilidad y el bloque indentado expresa la respuesta del programa cuando encuentra coincidencia.

## Cuándo conviene usarlo

`match-case` no reemplaza automáticamente a `if` o `elif`. Su utilidad aparece con más claridad cuando el problema gira en torno a un mismo dato que debe compararse con varios casos posibles.

Suele ser una buena elección cuando:

- Se analiza una opción ingresada por el usuario
- Se interpreta un código numérico o textual
- Se responde a un menú
- Se trabaja con categorías ya definidas
- Se desea que la lectura del programa sea más directa

Si el problema depende de comparaciones como “mayor que”, “menor que”, intervalos numéricos o condiciones combinadas, en muchos casos `if` y `elif` siguen siendo la opción más natural.

:::caution[Decisión de diseño]
Usar `match-case` tiene sentido cuando varios casos pertenecen a una misma selección. Si el problema se expresa mejor mediante condiciones, `if` y `elif` suelen ofrecer una solución más adecuada.
:::

## Un menú simple

Uno de los usos más claros de `match-case` aparece en programas con menús u opciones numeradas.

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

Aquí el programa sigue un proceso bastante natural:

1. Solicita una opción
2. Convierte ese dato a entero
3. Compara el valor con los casos disponibles
4. Ejecuta solo el bloque que corresponde

Este patrón resulta útil porque el código expresa de manera muy directa la relación entre una entrada y la respuesta esperada.

:::caution[Conversión de datos]
Si el valor ingresado debe compararse como número, conviene convertirlo antes de usar `match`. `input()` devuelve texto.
:::

## También con texto

La estructura `match-case` no se limita a números. También puede trabajar con cadenas de texto, lo que amplía bastante sus posibilidades.

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

Aquí el programa no compara cantidades, sino palabras concretas. Eso permite construir respuestas claras a partir de comandos, estados, nombres de opción o cualquier valor textual bien definido.

Este ejemplo también ayuda a ver que `match-case` no depende del tipo numérico. Lo importante no es si el valor es entero o texto, sino si existe una lista clara de casos posibles contra los cuales conviene compararlo.

## Un matiz importante

En Python, `match-case` forma parte de una característica más amplia conocida como *structural pattern matching*. Sin embargo, en este nivel no hace falta profundizar todavía en todos sus matices técnicos. Lo importante, por ahora, es comprender su uso más directo: seleccionar una acción a partir de un valor que se compara con casos definidos.

Ese enfoque basta para aprovechar la estructura en situaciones simples de programación y algoritmos, especialmente menús, códigos y categorías.

:::caution[Compatibilidad]
La estructura `match-case` está disponible desde Python 3.10. Si trabajas con una versión anterior, esta sintaxis no funcionará.
:::

## Del concepto al código

Escribe un programa en Python que solicite al usuario un número del `1` al `4` y muestre un mensaje según la estación del año correspondiente.

El programa debe cumplir con los siguientes requisitos:

- Debe pedir un número usando `input()`
- Debe convertir el dato a `int`
- Debe usar `match-case`
- Debe contemplar un caso general para valores no válidos

Equivalencias sugeridas:

- `1` → Verano
- `2` → Otoño
- `3` → Invierno
- `4` → Primavera

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa una opción: 3
Invierno
~~~

:::tip[Antes de escribir el código]
Piensa primero cuál será el valor que evaluará `match` y luego define con claridad qué respuesta corresponde a cada `case`.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta `match` dentro del capítulo de control de flujo y muestra ejemplos iniciales de uso.

- [Referencia del lenguaje: sentencia `match`](https://docs.python.org/3/reference/compound_stmts.html#the-match-statement)  
  Describe con mayor precisión técnica cómo funciona `match-case`, incluyendo patrones, comodines y reglas de evaluación.

- [Novedades de Python 3.10: Structural Pattern Matching](https://docs.python.org/3/whatsnew/3.10.html)  
  Explica la incorporación de esta estructura al lenguaje y ofrece contexto sobre su propósito general.