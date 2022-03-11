# Parte 2 - Divide y conquista

1. Determinar si una secuencia de n caracteres está ordenada alfabéticamente.

```
// code here ...
```

2. Dado un vector de n números naturales ordenados crecientemente, determinar si un
número x dado pertenece al vector.

```
public static boolean PerteneceValor(int[] arreglo, int i, int d, int val) {

    if (i >= d)
        return false;

    int m = (i + d) / 2;

    if( arreglo[m] == val)
        return true;
    else if(arreglo[m] < val)
        return PerteneceValor(arreglo, m + 1, d, val);
    else
        return PerteneceValor(arreglo, i, m, val);
}
```

3. Calcular a^n cuando n es una potencia de 2.
```
// code here ...
```
4. Dado un vector A de números enteros, calcular elemento mayoritario. Si se tieneun vector A de n 
enteros, un elemento x se denomina mayoritario de A si x aparece en el vector A más de n/2 veces. 
Considerar que no puede haber más de un elemento mayoritario.
```
// code here ...
```

5. Dadas dos matrices cuadradas M1 y M2 de NxN, calcular el producto de ambas,donde N es una 
potencia de 2.
```
// code here ...
```

6. Sea A[1..n], n ³ 1, un vector de enteros diferentes y ordenados crecientemente, tal que algunos 
de los valores pueden ser negativos. Diseñar un algoritmo que devuelva un índice natural k, 1£ k £ 
n, tal que A[k] = k, siempre que tal índice exista.
```
public static int IndiceValor(int[] arreglo, int i, int j) {
    if (i == j)
        return arreglo[i] == i ? i : -1;

    int m = (i + j) / 2;

    return m > arreglo[m]
            ? IndiceValor(arreglo, m + 1, j)
            : IndiceValor(arreglo, i, m);
}
```

7. Dado un Vector A de números enteros, ordenarlo en forma creciente. Utilizar el método de 
ordenamiento Merge-Sort, pero dividiendo el vector en 3 subvectores y analizar el costo.
```
// code here ...
```

8. Un organismo ha decidido organizar un torneo de fútbol con n equipos participantes. Cada equipo 
ha de competir exactamente una vez con todos los demás equipos oponentes. Además, se ha decidió 
que cada equipo juega exactamente un partido cada jornada, con la posible excepción de un solo día en
el cual no juega. Si n es una potencia de 2, diseñar un algoritmo que permita
que el torneo concluya en n-1 jornadas.
```
// code here ...
```

9. El problema del par más cercano consiste en encontrar dos puntos dentro de un conjunto de puntos 
cuya distancia sea menor que la que existe entre cualquier otro par de puntos del conjunto. 
Suponiendo que los puntos vienen ordenados por sus coordenadas (x; y), y que han sido clasificados 
en orden ascendente de la coordenada x, resolver el problema.
```
// code here ...
```

