---
title: Comparación
description: Operadores de comparación en Python para relacionar valores y obtener resultados lógicos.
slug: fundamentos/operadores/comparacion
sidebar:
  label: Comparación
  order: 3
---

:::note[Verificación previa]
Antes de continuar, asegúrate de conocer los tipos de datos básicos en Python, saber usar variables en expresiones simples y ya haber trabajado con operadores aritméticos y expresiones numéricas.
:::

Programar no consiste solo en calcular. También implica **evaluar situaciones**. Un programa necesita comprobar si un valor cumple una condición, si una cantidad supera un límite o si dos datos coinciden. Para realizar ese tipo de comprobaciones, Python utiliza operadores de comparación.

## Objetivo

Comprender cómo los operadores de comparación permiten relacionar valores en Python y producir resultados lógicos que luego pueden utilizarse en decisiones, validaciones y estructuras de control.

## Comparar también es programar

En muchos problemas, el programa necesita responder preguntas como estas:

- ¿La edad es mayor o igual a 18?
- ¿Dos valores son iguales?
- ¿Un número es distinto de otro?
- ¿Una cantidad está por debajo de un límite?

Estas preguntas no producen un cálculo numérico como una suma o una multiplicación. Producen una **evaluación**. El programa contrasta dos valores y determina si la relación entre ellos se cumple o no.

Ese resultado puede ser solo uno de dos posibles:

- `True`, cuando la comparación se cumple
- `False`, cuando la comparación no se cumple

:::note[Idea clave]
Los operadores de comparación no generan un número nuevo. Generan un resultado lógico: `True` o `False`.
:::

## Seis operadores básicos

Python dispone de seis operadores de comparación fundamentales.

| Operador | Significado | Ejemplo | Resultado |
| --- | --- | --- | --- |
| `==` | igual que | `5 == 5` | `True` |
| `!=` | distinto de | `5 != 3` | `True` |
| `>` | mayor que | `8 > 2` | `True` |
| `<` | menor que | `2 < 8` | `True` |
| `>=` | mayor o igual que | `5 >= 5` | `True` |
| `<=` | menor o igual que | `4 <= 7` | `True` |

Estas expresiones pueden parecer cercanas a las matemáticas, pero en Python cumplen una función muy concreta: producir una respuesta lógica que el programa luego puede utilizar para decidir qué hacer.

~~~python
print(5 == 5)
print(5 != 3)
print(8 > 2)
print(2 < 8)
~~~

En pantalla aparecen cuatro valores lógicos:

~~~text
True
True
True
True
~~~

Esto permite apreciar una idea central: una comparación no “muestra una cuenta”, sino que informa si una relación entre dos valores es verdadera o falsa.

## Igualdad y diferencia

Dos de los operadores más usados son `==` y `!=`. El primero comprueba igualdad. El segundo comprueba diferencia.

~~~python
print(10 == 10)
print(10 == 5)

print(8 != 4)
print(8 != 8)
~~~

En la primera comparación, Python pregunta si ambos valores coinciden exactamente. En la segunda, pregunta si son distintos.

~~~text
True
False
True
False
~~~

Aquí conviene detenerse en un detalle importante: comparar no es asignar. Cuando escribes `10 == 10`, no estás guardando un valor ni modificando una variable. Estás formulando una pregunta al programa.

## Mayor, menor y límites

Los operadores `>`, `<`, `>=` y `<=` permiten comparar magnitudes. Son especialmente útiles cuando el problema implica umbrales, mínimos, máximos o rangos.

~~~python
print(9 > 3)
print(2 < 1)
print(7 >= 7)
print(4 <= 2)
~~~

En cada caso, Python evalúa la relación entre ambos valores y entrega un resultado lógico.

~~~text
True
False
True
False
~~~

Estos operadores aparecen constantemente en programación, porque muchos problemas dependen de verificar si un valor supera, alcanza o queda por debajo de cierta referencia.

Por ejemplo, pueden servir para preguntar:

- Si una nota alcanza el mínimo de aprobación
- Si una temperatura supera cierto valor
- Si una cantidad cabe dentro de un límite
- Si una edad cumple un requisito

## Comparar variables

Los operadores de comparación no se usan solo con valores escritos directamente. Su utilidad real aparece cuando intervienen variables que representan datos del problema.

~~~python
edad = 18
print(edad >= 18)

puntaje = 5
print(puntaje < 4)
~~~

En el primer caso, Python evalúa si el valor almacenado en `edad` cumple la relación `>= 18`. En el segundo, comprueba si `puntaje` es menor que `4`.

~~~text
True
False
~~~

La lógica no cambia por usar variables. Python toma el valor almacenado en cada una y realiza la comparación correspondiente.

Esto es importante porque permite que el programa no compare solo números fijos escritos a mano, sino datos que pueden venir de cálculos, entradas del usuario o resultados anteriores.

## El resultado de comparar también es un dato

Una comparación no solo produce `True` o `False` en pantalla. También puede almacenarse en una variable y reutilizarse.

~~~python
resultado = 5 > 2
print(resultado)
print(type(resultado))
~~~

Aquí, la variable `resultado` no guarda un número ni un texto. Guarda un valor lógico.

~~~text
True
<class 'bool'>
~~~

Esto es muy importante para lo que vendrá más adelante, porque las estructuras condicionales trabajan precisamente con este tipo de valores. Dicho de otro modo: las comparaciones preparan el terreno para que el programa pueda tomar decisiones.

:::tip[Una idea importante]
Toda comparación en Python produce un valor de tipo `bool`.
:::

## Cuando dos valores se ven parecidos

Una de las confusiones más frecuentes al comenzar es pensar que dos valores que se ven similares deberían compararse como equivalentes. Sin embargo, Python también considera el tipo de dato.

~~~python
print(5 == "5")
~~~

El resultado es:

~~~text
False
~~~

Aunque ambos valores pueden parecer parecidos a simple vista, no representan lo mismo para el lenguaje.

- `5` es un número entero
- `"5"` es un texto

Esto muestra que comparar no consiste solo en mirar el contenido visible, sino también en considerar qué tipo de dato está involucrado.

## Leer bien una comparación

Cuando una comparación aparece en un programa, conviene leerla como una pregunta precisa. Por ejemplo:

- `edad >= 18` puede leerse como “¿la edad es mayor o igual a 18?”
- `precio < 3000` puede leerse como “¿el precio es menor que 3000?”
- `nombre == "Ada"` puede leerse como “¿el nombre coincide con Ada?”

Esta forma de lectura ayuda mucho a comprender el código y prepara el paso hacia las estructuras condicionales, donde justamente el programa actuará según si una comparación resulta verdadera o falsa.

## `=` no es lo mismo que `==`

Este es uno de los errores más comunes en las primeras etapas.

- `=` se usa para asignar un valor a una variable
- `==` se usa para comparar si dos valores son iguales

Por ejemplo:

~~~python
edad = 18
print(edad == 18)
~~~

En la primera línea, el programa asigna un valor. En la segunda, formula una comparación.

Comprender esta diferencia es fundamental, porque una asignación modifica el estado del programa, mientras que una comparación solo evalúa una relación.

:::caution[Error frecuente]
Un error frecuente es confundir `=` con `==`. En Python, `=` se usa para asignar valores a una variable, mientras que `==` se usa para comparar si dos valores son iguales. También es frecuente comparar un número con un texto pensando que Python los interpretará como equivalentes.
:::

## Del concepto al código

Escribe y prueba las siguientes comparaciones:

1. `7 == 7`
2. `7 != 5`
3. `10 > 3`
4. `2 < 1`
5. `8 >= 8`
6. `4 <= 6`

Luego trabaja con variables:

1. Crea una variable `edad` con valor `16`
2. Comprueba si `edad >= 18`
3. Crea una variable `precio` con valor `2500`
4. Comprueba si `precio < 3000`

Puedes tomar como referencia un fragmento como este:

~~~python
print(7 == 7)
print(7 != 5)
print(10 > 3)
print(2 < 1)
print(8 >= 8)
print(4 <= 6)

edad = 16
print(edad >= 18)

precio = 2500
print(precio < 3000)
~~~

Al probar estas comparaciones, conviene fijarse en estas ideas:

- Comparar consiste en evaluar una relación entre dos valores
- El resultado siempre es `True` o `False`
- Una comparación puede utilizar valores directos o variables
- El tipo de dato también influye en el resultado

## Para profundizar

Si deseas ampliar este contenido con fuentes del propio lenguaje, estas lecturas son especialmente útiles:

- [Tutorial oficial de Python: una introducción informal](https://docs.python.org/3/tutorial/introduction.html)  
  Presenta expresiones, valores lógicos y operaciones básicas en un contexto progresivo y formativo.

- [Tipos integrados de Python](https://docs.python.org/3/library/stdtypes.html)  
  Describe con mayor precisión técnica los valores booleanos y el comportamiento general de comparaciones entre objetos.

- [Referencia del lenguaje: expresiones](https://docs.python.org/3/reference/expressions.html)  
  Explica cómo Python interpreta operadores y expresiones, incluyendo comparaciones.