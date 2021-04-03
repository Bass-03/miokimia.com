---
layout: post
title: Algoritmos
date: 2019-01-01
summary: Conceptos de programación y algoritmos
category: Programación
---


Hablamos de programación estructurada cuando queremos obtener un programa claro, de calidad y que toma un menor tiempo de desarrollo, utilizando funciones y tres estructuras básicas: Bloques de código, selección e iteración, el resultado de utilizar este paradigma es código que requiere menor mantenimiento y menor cantidad de errores.

Cuando programamos generamos un secuencia de instrucciones que le dicen a la computadora que actividad llevar a cabo, a esto se le llama algoritmo.

Los algoritmos son empleados en la solución de problemas en la vida cotidiana, no solo cuando programamos en la computadora, algunos ejemplos en matemáticas son la suma, resta, división y multiplicación, muchas veces hacemos estos cálculos de forma inmediata sin necesidad de revisar los pasos que conlleva por que se nos da de forma natural eso no significa que no sea necesaria una secuencia de pasos para obtener un resultado, es decir, un algoritmo.

## Un problema, un Algoritmo

Para demostrar el concepto de algoritmo vamos a utilizar la multiplicación de dos matrices y explicar los pasos necesarios para resolver el problema.
El problema a solucionar es multiplicar una Matriz de tamaño MxN y otra de tamaño NxP para obtener una nueva matriz de tamaño MxP

### Antecedentes

Una matriz es un arreglo de números en dos dimensiones, de forma que:

![matrix]({filename}/images/matrix.png)

Podemos definir sus dimensiones MxN de forma que M es la cantidad de filas y N la cantidad de columnas de la matriz.
Para resolver el problema de multiplicación de matrices debemos de entender las limitaciones del procedimiento.

Por definición, dada una matriz A y una B, el producto AB es posible cuando el número de columnas de la matriz A es igual al número de filas de la matriz B, es decir, las matrices con dimensiones MxN y NxP darán como resultado una matriz de dimensiones MxP, nótese que las dimensiones de las matrices A y B tienen en común el número N, el cual es el número de columnas de A y el número de filas de B.

Dado que el producto AB es posible, este se obtiene multiplicando cada fila de A por cada columna de B, de forma que teniendo una fila F y una columna C podemos decir que:

```
AB = FxA  CzB
```

Donde xA es el índice de Fila de la matriz A y zB es  el índice de columna de la matriz B.

## El Algoritmo

Para multiplicar dos matrices, por ejemplo 2x2 tenemos que:

1.  Saber si las dos matrices son multiplicables
1.  Multiplicar A11 por B11 y
1.  Multiplicar A12 por B21 y
1.  Sumar los resultados, este es el valor en  C11 de la resultante matriz C
1.  Multiplicar A11 por B12 y
1.  Multiplicar A12 por B22 y
1.  Sumar los resultados, este es el valor en  C12 de la resultante matriz C
1.  Multiplicar A21 por B11 y
1.  Multiplicar A22 por B21 y
1.  Sumar los resultados, este es el valor en  C21 de la resultante matriz C
1.  Multiplicar A21 por B12 y
1.  Multiplicar A22 por B22 y
1.  Sumar los resultados, este es el valor en C22 de la resultante matriz C

# En Pseudo código

Podemos notar como escribir el algoritmo de la forma anterior es muy tedioso, imagina una matriz de 1000x1000, no queremos escribir tanto.

Con pseudo código podemos utilizar conceptos de programación y escribir instrucciones que aplican a muchos mas casos que solo uno, es decir, aplicando los pasos en el pseudo código podemos resolver el problema para matrices de cualquier tamaño.

Vamos a usar dos estructuras comunes en cualquier lenguaje de programación:
1. Estructura de control **if ... then**
1. Estructure de repetición **while**

Entonces podemos escribir lo siguiente:

1.  LEER **matriz_A**
1.  LEER **matriz_B**
1.  Variable **matriz_C** = Arreglo
1.  if (ancho de **matriz_A** == largo de **matriz_B**)
    1.  variable **contador_A** = 0
    1.  while (**contador_A** <= ancho de **matriz_A**)
        variable **contador_B** = 0
        1.  while (**contador_B** <= largo de **matriz_B**)
            1.  AGREGAR  (**matriz_A**contador_A,contador_B * **matriz_B**contador_B,contador_A) a **matriz_C**
            1.  **contador_B** = **contador_B** + 1
        1.  **contador_A** = **contador_A** + 1
1.  imprimir **matriz_C**


Hay que tomar en cuenta que hay mejores formas de trabajar con arreglos en los diferentes lenguajes de programación, en ruby en vez de usar la estructura **while** utilizaría **Arreglo.each**, de forma que no tengo que mantener contadores.

También hay diferentes formas de agregar valores a la matriz resultante C, lo que importa es que sepamos que está pasando en el pseudo código y lo podamos replicar con código.
