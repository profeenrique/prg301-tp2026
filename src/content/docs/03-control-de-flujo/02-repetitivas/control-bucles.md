---
title: Control de bucles
description: Uso de break, continue y else para modificar el comportamiento de los bucles en Python.
slug: control-de-flujo/repetitivas/control-bucles
sidebar:
  label: Control de bucles
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de que comprendes cómo funcionan los bucles `while` y `for`, reconoces la importancia de la indentación en Python y sabes leer condiciones y comparaciones simples.
:::

Un bucle no siempre recorre todo su camino de la misma forma. A veces conviene detenerlo apenas ocurre algo importante. En otras ocasiones, interesa ignorar un caso puntual y continuar con el siguiente. También puede ser útil distinguir entre un ciclo que terminó “normalmente” y otro que fue interrumpido antes de tiempo. Para expresar esas diferencias, Python incorpora herramientas específicas de control dentro de los bucles.

## Objetivo

Comprender cómo `break`, `continue` y `else` permiten modificar el flujo de un bucle en Python para resolver recorridos, búsquedas y validaciones con mayor precisión.

## Ajustar el recorrido

Cuando se trabaja con un `for` o un `while`, lo habitual es que el ciclo siga su recorrido natural:

- `for` avanza por todos los elementos de la secuencia
- `while` repite mientras su condición siga siendo verdadera

Sin embargo, muchos problemas requieren un control más fino. Puede ser necesario:

- detener el ciclo al encontrar un valor
- saltar una iteración que no interesa procesar
- ejecutar una acción solo si el bucle terminó sin interrupciones

En Python, ese ajuste del recorrido se expresa principalmente con estas construcciones:

| Construcción | Tipo | Función principal |
| --- | --- | --- |
| `break` | Sentencia | Termina el bucle de inmediato |
| `continue` | Sentencia | Omite el resto de la iteración actual |
| `else` | Cláusula | Se ejecuta si el bucle termina sin `break` |

:::note[Idea clave]
Estas construcciones no reemplazan al bucle. Modifican su comportamiento para que el recorrido responda mejor a la lógica del problema.
:::

## Detener el ciclo

La sentencia `break` termina de inmediato el bucle más cercano en el que aparece escrita. Cuando Python la ejecuta, abandona el ciclo y continúa con la primera instrucción que viene después.

~~~python
for numero in range(1, 6):
    if numero == 4:
        break
    print(numero)

print("Fin del recorrido")
~~~

Aquí el ciclo comienza recorriendo los números del `1` al `5`, pero no llega hasta el final. En cuanto `numero` vale `4`, se ejecuta `break` y el recorrido se interrumpe.

~~~text
1
2
3
Fin del recorrido
~~~

Este comportamiento resulta útil cuando el programa ya encontró lo que buscaba o cuando seguir recorriendo dejó de tener sentido.

:::tip[Cuándo usar `break`]
Piensa `break` así: “si ocurre esto, el ciclo debe terminar ahora”.
:::

## Saltar una vuelta

La sentencia `continue` no termina el bucle. Lo que hace es omitir el resto de la iteración actual y pasar directamente a la siguiente.

~~~python
for numero in range(1, 6):
    if numero == 3:
        continue
    print(numero)
~~~

En este caso, cuando `numero` vale `3`, Python no ejecuta el `print(numero)` de esa vuelta. En lugar de eso, vuelve al inicio del ciclo y continúa con el siguiente valor.

~~~text
1
2
4
5
~~~

`continue` es útil cuando hay casos que no deben procesarse, pero el recorrido general sí debe continuar.

## No producen el mismo efecto

Aunque `break` y `continue` suelen enseñarse juntos, cumplen funciones distintas. Esa diferencia es fundamental para leer correctamente el flujo de un ciclo.

| Construcción | Qué hace | Efecto en el bucle |
| --- | --- | --- |
| `break` | Interrumpe el ciclo completo | El recorrido termina |
| `continue` | Interrumpe solo la vuelta actual | El ciclo sigue con la siguiente iteración |

~~~mermaid
flowchart TD
    A[Inicio de la iteración] --> B{¿Se cumple una condición?}
    B -->|No| C[Ejecutar normalmente el bloque]
    B -->|Sí, usar continue| D[Omitir el resto de la vuelta]
    B -->|Sí, usar break| E[Salir del bucle]
    C --> F[Siguiente iteración]
    D --> F
~~~

Esta distinción puede parecer pequeña al comienzo, pero cambia por completo la lógica del programa. Una sentencia detiene todo el proceso; la otra solo evita procesar un caso puntual.

## Buscar y detenerse

Uno de los usos más frecuentes de `break` consiste en detener un recorrido cuando se encuentra un valor determinado.

~~~python
nombres = ["Ana", "Luis", "Camila", "Pedro"]

for nombre in nombres:
    if nombre == "Camila":
        print("Nombre encontrado")
        break
~~~

Aquí el programa recorre la lista hasta encontrar `"Camila"`. En ese momento imprime el mensaje y termina el ciclo. No necesita seguir revisando los elementos restantes, porque el objetivo de la búsqueda ya se cumplió.

Este patrón aparece con frecuencia en búsquedas simples, verificaciones de existencia y validaciones tempranas.

## Seguir, pero ignorar algunos casos

`continue` aparece a menudo cuando ciertos elementos deben omitirse sin detener el recorrido completo.

~~~python
notas = [6.0, 0.0, 5.5, 0.0, 4.8]

for nota in notas:
    if nota == 0.0:
        continue
    print(nota)
~~~

En este caso, las notas `0.0` se ignoran y el ciclo sigue con las demás.

~~~text
6.0
5.5
4.8
~~~

La utilidad de `continue` se aprecia bien aquí: el programa no rechaza toda la lista por algunos casos problemáticos, sino que sigue avanzando y procesa solo los valores que interesan.

## Cuando el ciclo termina sin romperse

Tanto `for` como `while` pueden incluir una cláusula `else`. Esta parte se ejecuta únicamente si el ciclo termina de forma normal, es decir, sin haber pasado por un `break`.

~~~python
numeros = [2, 4, 6, 8]

for numero in numeros:
    if numero == 5:
        print("Encontrado")
        break
else:
    print("No se encontró el valor")
~~~

Como el valor `5` nunca aparece, `break` no se ejecuta y Python entra en la cláusula `else`.

~~~text
No se encontró el valor
~~~

Este comportamiento es especialmente útil cuando se quiere distinguir entre dos situaciones distintas:

- el ciclo terminó porque encontró lo que buscaba
- el ciclo terminó porque revisó todo y no lo encontró

:::caution[Atención con `else`]
En un bucle, `else` no significa “en caso contrario” de una condición aislada. Significa, más bien, “si el ciclo terminó sin ser interrumpido por `break`”.
:::

## Leer `else` con más precisión

La cláusula `else` en bucles suele parecer extraña al comienzo porque muchas personas la asocian de inmediato con `if`. Sin embargo, aquí cumple una función diferente.

No responde a una comparación puntual, sino al **modo en que terminó el ciclo**. Esa es la idea que conviene retener:

- si hubo `break`, `else` no se ejecuta
- si no hubo `break`, `else` sí puede ejecutarse

Entender esta diferencia ayuda a leer mejor estructuras de búsqueda, validación y recorrido completo.

## También dentro de `while`

Las sentencias `break` y `continue` no se limitan al bucle `for`. También pueden utilizarse dentro de un `while`, donde cumplen la misma función general: modificar el flujo natural del ciclo.

En un `while`, este control puede resultar incluso más importante, porque el ciclo depende de una condición que se vuelve a evaluar en cada vuelta. Eso significa que el recorrido puede prolongarse bastante si no se gestiona con cuidado.

~~~python
numero = 0

while numero < 5:
    numero = numero + 1

    if numero == 2:
        continue

    if numero == 4:
        break

    print(numero)
~~~

Este fragmento conviene leerlo con calma, porque muestra dos formas distintas de intervenir en una misma repetición.

En cada vuelta:

- Primero `numero` aumenta en `1`
- Luego se revisa si vale `2`
- Después se revisa si vale `4`
- Si no ocurre ninguna de esas situaciones, se imprime

El recorrido queda así:

- Cuando `numero` vale `1`, se imprime
- Cuando vale `2`, se ejecuta `continue` y esa vuelta termina sin imprimir
- Cuando vale `3`, se imprime
- Cuando vale `4`, se ejecuta `break` y el bucle finaliza

~~~text
1
3
~~~

Este ejemplo permite observar con claridad que `continue` y `break` no producen el mismo efecto:

- `continue` interrumpe solo la iteración actual
- `break` interrumpe el ciclo completo

## Qué problema ayuda a resolver cada uno

Una forma útil de decidir entre estas construcciones es pensar en el tipo de problema que se quiere resolver.

- `break` ayuda cuando el recorrido debe detenerse en cuanto ocurre algo decisivo
- `continue` sirve cuando ciertos casos deben ignorarse sin cancelar el resto del proceso
- `else` permite distinguir entre un recorrido interrumpido y uno completado normalmente

Esa mirada evita usarlos “por costumbre” y ayuda a que el código exprese con mayor claridad la intención del algoritmo.

## Controlar no es complicar

Estas herramientas vuelven a los bucles más expresivos, pero también exigen cuidado. Si un mismo ciclo acumula demasiados `break`, `continue` y condiciones cruzadas, el código puede volverse difícil de leer.

Por eso conviene usarlas cuando realmente mejoran la solución y no solo porque “funcionan”.

:::tip[Buena práctica]
Usa `break` y `continue` cuando aclaren la lógica del problema. Si el recorrido se vuelve confuso, quizá convenga replantear la estructura del ciclo.
:::

## Del concepto al código

Escribe un programa en Python que solicite números enteros al usuario hasta que se ingrese `0`. El programa debe sumar solo los números positivos. Los números negativos deben ignorarse.

El programa debe cumplir con los siguientes requisitos:

- Debe usar un bucle `while`
- Debe pedir números usando `input()`
- Debe convertir cada dato a `int`
- Debe usar `break` para terminar cuando se ingrese `0`
- Debe usar `continue` para omitir los números negativos
- Debe mostrar la suma final al terminar

Cuando ejecutes el programa, debería funcionar de la siguiente manera:

~~~text
Ingresa un número: 5
Ingresa un número: -2
Ingresa un número: 7
Ingresa un número: 0
Suma total: 12
~~~

:::tip[Antes de escribir el código]
Piensa por separado en estas decisiones: cuándo termina el ciclo, qué casos deben ignorarse y en qué momento se actualiza la suma.
:::

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: herramientas de control de flujo](https://docs.python.org/3/tutorial/controlflow.html)  
  Presenta `break`, `continue` y `else` en bucles con ejemplos progresivos y explicaciones orientadas al aprendizaje.

- [Referencia del lenguaje: sentencias simples](https://docs.python.org/3/reference/simple_stmts.html)  
  Describe con mayor precisión técnica cómo funcionan `break` y `continue` dentro del lenguaje.

- [Referencia del lenguaje: sentencias compuestas](https://docs.python.org/3/reference/compound_stmts.html)  
  Explica cómo se relacionan estas instrucciones con la estructura de los bucles `for` y `while`, incluyendo el uso de `else`.