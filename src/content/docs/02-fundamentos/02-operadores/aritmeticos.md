---
title: Aritméticos
description: Operadores aritméticos básicos en Python para realizar cálculos simples.
slug: fundamentos/operadores/aritmeticos
sidebar:
  label: Aritméticos
  order: 1
---

:::note[Verificación previa]
Antes de continuar, asegúrate de reconocer los tipos de datos numéricos básicos en Python, saber crear variables y asignarles valores, y comprender conversiones simples entre texto y número.
:::

Programar no consiste solo en guardar información. También implica **transformarla**. Un programa suma cantidades, calcula diferencias, multiplica valores, reparte datos y obtiene resultados nuevos a partir de datos anteriores. Para realizar esas transformaciones, Python utiliza operadores aritméticos.

## Objetivo

Comprender cómo los operadores aritméticos permiten construir cálculos en Python y utilizarlos correctamente con valores numéricos y variables.

## Calcular dentro de un programa

Cuando resolvemos un problema con código, muchas veces necesitamos hacer algo más que mostrar datos. Puede ser necesario:

- Calcular un total
- Obtener una diferencia
- Repartir una cantidad
- Hallar un resto
- Elevar un valor a una potencia

En todos esos casos, el programa necesita aplicar operaciones matemáticas. En Python, esas operaciones se expresan mediante operadores aritméticos.

:::note[Idea clave]
Los operadores aritméticos permiten producir nuevos valores a partir de cantidades numéricas ya existentes.
:::

## Qué operadores se usan

En esta etapa conviene trabajar con los operadores aritméticos más frecuentes.

| Operador | Nombre | Ejemplo | Resultado |
| --- | --- | --- | --- |
| `+` | Suma | `4 + 2` | `6` |
| `-` | Resta | `4 - 2` | `2` |
| `*` | Multiplicación | `4 * 2` | `8` |
| `/` | División | `4 / 2` | `2.0` |
| `//` | División entera | `5 // 2` | `2` |
| `%` | Módulo o resto | `5 % 2` | `1` |
| `**` | Potencia | `2 ** 3` | `8` |

Esta tabla sirve como mapa inicial, pero no conviene memorizarla de forma aislada. Lo importante es comprender qué hace cada operador y en qué situaciones puede resultar útil.

## Operar con valores y variables

Los operadores aritméticos pueden aplicarse tanto a valores escritos directamente como a variables que ya almacenan números.

~~~python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
~~~

Al ejecutar este fragmento, Python realiza cuatro operaciones distintas usando los valores almacenados en `a` y `b`.

~~~text
13
7
30
3.3333333333333335
~~~

Aquí puede observarse algo importante: los operadores no solo sirven para “hacer cuentas”, sino para construir resultados a partir de datos que el programa ya tiene disponibles.

## Sumar y restar

La suma y la resta permiten combinar cantidades o calcular diferencias entre valores.

~~~python
precio = 1200
descuento = 300

print(precio - descuento)
print(precio + descuento)
~~~

En la primera operación, el programa calcula cuánto queda después de aplicar un descuento. En la segunda, suma ambos valores y produce una cantidad distinta.

En pantalla aparecen estos resultados:

~~~text
900
1500
~~~

Este tipo de operación aparece constantemente en problemas simples: totales, diferencias, acumulaciones o comparaciones de cantidades.

## Multiplicar una cantidad

La multiplicación permite repetir una cantidad varias veces o calcular el producto entre dos valores.

~~~python
cantidad = 4
precio_unitario = 2500

print(cantidad * precio_unitario)
~~~

Aquí el cálculo representa una situación bastante habitual: multiplicar una cantidad de objetos por su valor unitario para obtener un total.

~~~text
10000
~~~

La multiplicación es especialmente útil cuando el problema involucra agrupaciones, cantidades repetidas o escalas de proporcionalidad.

## Dos formas de dividir

La división merece más atención, porque en Python no existe una sola manera de dividir.

### División con `/`

El operador `/` realiza una división y devuelve un resultado decimal, aunque la división sea exacta.

~~~python
print(8 / 2)
print(7 / 2)
~~~

En pantalla aparecen:

~~~text
4.0
3.5
~~~

Aquí conviene fijarse en un detalle importante: incluso cuando `8 / 2` produce una división exacta, Python entrega `4.0`, es decir, un valor decimal.

:::tip[Una idea importante]
En Python, el operador `/` devuelve un resultado de tipo `float`.
:::

### División con `//`

El operador `//` realiza una división entera. Eso significa que devuelve solo la parte entera del cociente.

~~~python
print(7 // 2)
print(9 // 4)
~~~

En pantalla aparecen:

~~~text
3
2
~~~

Este operador resulta útil cuando interesa trabajar solo con la cantidad completa de veces que un valor cabe dentro de otro, sin considerar la parte decimal.

:::caution[Atención con la división]
`/` y `//` no hacen lo mismo. El primero devuelve un resultado decimal; el segundo conserva solo la parte entera del cociente.
:::

## El resto también entrega información

El operador `%` devuelve el resto de una división.

~~~python
print(7 % 2)
print(10 % 3)
~~~

En ambos casos, Python calcula qué sobra después de dividir.

~~~text
1
1
~~~

Esta operación puede parecer menos familiar al comienzo, pero resulta muy útil en programación. Por ejemplo, permite saber si un número es par o impar.

~~~python
print(8 % 2)
print(9 % 2)
~~~

~~~text
0
1
~~~

Cuando el resto de dividir por `2` es `0`, el número es par. Si el resto es `1`, el número es impar.

## Potencias

El operador `**` permite elevar un número a una potencia.

~~~python
print(2 ** 3)
print(5 ** 2)
~~~

En pantalla aparecen:

~~~text
8
25
~~~

Esta operación resulta útil cuando el problema requiere cuadrados, cubos u otras potencias, como ocurre en fórmulas, áreas o cálculos más generales.

## Cuando el cálculo depende de variables

Una de las ideas más importantes de este tema es que los operadores aritméticos no se usan solo con números escritos directamente. Su verdadero valor aparece cuando intervienen variables.

~~~python
base = 5
altura = 3
area = base * altura

print(area)
~~~

Aquí el programa no está calculando con valores aislados sin contexto. Está utilizando variables que representan datos del problema y, a partir de ellas, construye un nuevo resultado.

En pantalla aparece:

~~~text
15
~~~

Esto vuelve el código más flexible, porque si cambian los valores de `base` o `altura`, el cálculo también cambia sin necesidad de reescribir toda la operación.

## El orden del cálculo también importa

No basta con conocer los operadores. También conviene entender que el orden en que aparecen puede cambiar el resultado.

~~~python
print(2 + 3 * 4)
print((2 + 3) * 4)
~~~

En el primer caso, Python multiplica antes de sumar. En el segundo, los paréntesis obligan a realizar primero la suma.

~~~text
14
20
~~~

Este detalle es importante porque muestra que un cálculo no depende solo de los valores y operadores, sino también de la forma en que se organiza la expresión.

:::tip[Buena práctica]
Cuando una expresión puede prestarse a confusión, usa paréntesis para dejar clara la intención del cálculo.
:::

## Cuando el tipo del dato cambia el resultado

Los operadores aritméticos están pensados para trabajar con números. Si una variable contiene texto en lugar de un valor numérico, el comportamiento del programa puede no ser el esperado.

~~~python
edad = "18"
print(edad + 2)
~~~

Este código produce un error, porque `"18"` es texto y `2` es un número entero. Python no puede sumarlos directamente.

Por eso, antes de operar, conviene asegurarse de que el dato tenga el tipo correcto. En muchos casos, eso implicará convertirlo.

:::caution[Error frecuente]
También es frecuente intentar operar con textos cuando el programa espera números. Si el dato no tiene un tipo numérico, conviene revisar si antes debe convertirse con `int()` o `float()`.
:::

## Del concepto al código

Escribe y prueba un programa que haga lo siguiente:

1. Calcule la suma de dos números
2. Calcule la resta entre dos valores
3. Calcule el producto de dos números
4. Divida dos valores con `/`
5. Divida dos valores con `//`
6. Calcule el resto de una división con `%`
7. Eleve un número a una potencia con `**`

Puedes tomar como referencia un punto de partida como este:

~~~python
a = 12
b = 5

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** 2)
~~~

Al probar este fragmento, conviene prestar atención a estas ideas:

- No todos los operadores producen el mismo tipo de resultado
- La división con `/` y con `//` no se comporta igual
- El tipo de dato influye en las operaciones que pueden realizarse

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta operaciones numéricas básicas en un contexto progresivo y formativo.

- [Biblioteca estándar: tipos numéricos](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)  
  Describe cómo se comportan los tipos numéricos en Python.

- [Referencia del lenguaje: expresiones](https://docs.python.org/3/reference/expressions.html)  
  Explica con mayor precisión técnica cómo se interpretan los operadores y el orden de evaluación de las expresiones.