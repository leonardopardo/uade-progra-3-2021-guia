# Greedy

## Características del Algoritmo
- Se aplica a problemas de __optimización__.
- Se tienen __n__ entradas.
- Encontrar un subconjunto que satisfaga ciertas restricciones.
- Optimice alguna función objetivo (maximizar o minimizar)


## Solución Factible
- Solución factible es cualquier subconjunto que satisface las restricciones

## Solución Objetivo
- Solucion objetivo es una solución factible que __maximice o minimice la función objetivo__. Una 
solución factible que logra este objetivo se llama óptima. 

## Costo del Algoritmo
El costo del algoritmo depende de:  
- el número de iteraciones, que depende del tamaño de la entrada.
- el costo de las fuciones __seleccionar__ y __factible__.

1. Factible -> generalmente tiempo constante.
2. Seleccionar -> explora el conjunto de candidatos y obtiene el mejor en ese momento.
_Mejora: preparar el conjunto de candidatos antes de entarar al bucle (por ejemplo, ordenar por 
algún criterio)_ 

```
void Greedy(A, n) {
    solución = vacio;
    for(i=1; i < n; i++) {
        x = Seleccionar(A);
        A = A-{x};
        if(Factible(solucion, x)){
            solucion = solucion U {x};
        }
    }
}
```

## Características de la técnica
Propiedades de los problemas resolubles por greedy:

1. __Identificar la Restricción__
2. __Identificar la función objetivo (maximizar o minimizar)__
3. __Rango de la variable de iteración__

Solución factible <- 1 y 3
Solución óptima <- todo

1. Elección greedy (greedy-choice): una solución globalmente óptima puede ser alcanzada tomando alternativas localmente óptimas.

    - En un momneto dado, realizamos la mejor alternativa y luego resolvemos el subproblema que queda.

    - Debemos probar que la elección greede en cada paso conduce a l asolución optima global. 

2. Subestructura óptima
    
    - Un problema exhibe una subestructura óptima si una solución óptima al problema contiene soluciones óptimas para los subproblemas.


__Ejemplo__
```
void Greedy_Mochila(float M, int n) {
    
    
    float resto = M;

    for( i=1; (i < n) && (P[i] <= resto); i++ ) {
        X[i] = 1;
        resto = resto - P[i];
    }

    if( i <= n)
        X[i] = resto / P[i];
}
```