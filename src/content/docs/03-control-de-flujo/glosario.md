---
title: Glosario
description: Términos básicos utilizados en la unidad de control de flujo en Python.
slug: control-de-flujo/glosario
sidebar:
  label: Glosario
---

Este glosario reúne términos frecuentes de la unidad de control de flujo. Su propósito es facilitar la lectura de los contenidos y ofrecer definiciones breves, claras y útiles para trabajar con estructuras selectivas y repetitivas en Python.

:::note[Uso recomendado]
Consulta este glosario cuando encuentres un término técnico que no recuerdes o quieras revisar con mayor precisión.
:::

## Decisiones y condiciones

| Término | Definición |
|---|---|
| **Control de flujo** | Conjunto de estructuras que permiten modificar el recorrido natural de un programa. |
| **Condición** | Expresión cuyo resultado puede interpretarse como verdadero o falso. |
| **Comparación** | Relación entre dos valores que produce un resultado lógico. |
| **Resultado lógico** | Valor booleano obtenido al evaluar una comparación o condición. |
| **Valor de verdad** | Forma en que Python interpreta una expresión como verdadera o falsa dentro de una condición. |
| **`True`** | Valor booleano que representa una condición verdadera. |
| **`False`** | Valor booleano que representa una condición falsa. |
| **Estructura selectiva** | Estructura que permite elegir entre distintas acciones según una condición o caso. |

## Estructuras selectivas

| Término | Definición |
|---|---|
| **`if`** | Estructura que ejecuta un bloque solo si una condición es verdadera. |
| **`elif`** | Cláusula que permite agregar nuevas condiciones a una estructura iniciada con `if`. |
| **`else`** | Cláusula que representa un caso alternativo cuando las condiciones anteriores no se cumplen, o bien el cierre normal de un bucle sin `break`. |
| **`match`** | Palabra reservada que inicia una estructura de selección basada en casos. |
| **`case`** | Caso posible dentro de una estructura `match-case`. |
| **`match-case`** | Estructura que permite seleccionar una acción según el valor o caso que coincida. |
| **Comodín** | Caso general que coincide con cualquier valor no contemplado antes. En `match-case`, se representa con `_`. |
| **Patrón** | Valor o forma con que un `case` intenta coincidir dentro de `match-case`. |

## Repetición y recorridos

| Término | Definición |
|---|---|
| **Estructura repetitiva** | Estructura que permite repetir instrucciones. |
| **Bucle** | Estructura que repite un bloque de código varias veces. |
| **Iteración** | Cada una de las vueltas de un ciclo. |
| **`while`** | Bucle que repite instrucciones mientras una condición se mantenga verdadera. |
| **`for`** | Bucle que recorre una secuencia elemento por elemento. |
| **Recorrido** | Proceso mediante el cual un programa avanza por una secuencia o por las iteraciones de un ciclo. |
| **Secuencia** | Conjunto ordenado de elementos que puede recorrerse, como una lista, una cadena o un `range()`. |
| **Variable de control** | Variable que participa en el avance o finalización de un ciclo. |
| **Contador** | Variable que suele aumentar o disminuir en cada iteración para controlar un ciclo. |
| **Condición de salida** | Situación que hace que un ciclo termine. |
| **Bucle infinito** | Ciclo que no termina de manera natural porque su condición nunca deja de cumplirse. |
| **`range()`** | Función que genera una secuencia de números enteros y se usa con frecuencia junto con `for`. |

## Control de bucles

| Término | Definición |
|---|---|
| **`break`** | Sentencia que termina de inmediato el bucle más cercano. |
| **`continue`** | Sentencia que omite el resto de la iteración actual y pasa a la siguiente. |
| **Interrupción del ciclo** | Finalización anticipada de un bucle antes de completar su recorrido natural. |
| **Recorrido completo** | Situación en que un bucle termina normalmente, sin haber sido interrumpido por `break`. |
| **Búsqueda** | Proceso de recorrer datos para encontrar un valor o caso específico. |
| **Validación** | Comprobación de que un dato cumple una condición requerida por el programa. |

## Escritura del código

| Término | Definición |
|---|---|
| **Indentación** | Sangría que en Python define los bloques de código. |
| **Bloque de código** | Conjunto de instrucciones que pertenecen a una misma estructura. |
| **Sintaxis** | Conjunto de reglas que indica cómo debe escribirse una instrucción para que Python pueda interpretarla. |
| **Cláusula** | Parte de una estructura mayor, como `elif` o `else`. |
| **Sentencia** | Instrucción completa que Python puede ejecutar, como `break` o `continue`. |
| **Flujo secuencial** | Ejecución de instrucciones una tras otra, en el orden en que fueron escritas. |

## Comprensión y errores frecuentes

| Término | Definición |
|---|---|
| **Jerarquía de decisiones** | Orden en que Python evalúa varias condiciones dentro de una misma estructura. |
| **Caso excluyente** | Situación en la que solo una de varias alternativas debe ejecutarse. |
| **Error lógico** | Error en el que el programa se ejecuta, pero no produce el resultado esperado. |
| **Error de sintaxis** | Error producido por una instrucción mal escrita. |
| **Salida esperada** | Resultado que debería aparecer si el programa funciona correctamente. |
| **Entrada** | Información que el programa recibe durante su ejecución. |
| **Salida** | Información que el programa muestra en pantalla. |