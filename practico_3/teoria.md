# Árboles de Recubrimiento
Árbol libre (sin raíz y sin ciclos) que conecta a todos los vértices del grafo.

## Árboles de Recubrimiento de Costo Mínimo
Aquel cuyo costo sea menor que el costo de cualquier otro árbol de recubrimiento para el grafo.

## Árboles de Recubrimiento de Costo Máximo
Aquel cuyo costo sea mayor que el costo de cualquier otro árbol de recubrimiento para el grafo.

## PRIM
- Comienza con un solo árbol formado por un vértice cualquiera del grafo.
- En cada paso, __selecciona la arista de mínimo costo que conecta al árbol un vértice que no está en él.__
- Termina cuando todos los vértices han sido incorporados al árbol de recubrimiento.

*Ejemplo*  

`vertices [1,2,3,4,5,6]`

_Matriz de Adyacencia_

```
X 1 2 3 4 5 6
1 0 6 1 5 0 0
2 6 0 5 0 3 0
3 1 5 0 5 6 4 
4 5 0 5 0 0 2
5 0 3 6 0 0 6
6 0 0 4 2 6 0
``` 
- Paso 0 []
- Paso 1 [1] <- se selecciona un vértice cualquiera
- Paso 2 [1, 3] <- la arista de menor costo para incoropara un nuevo vertice
- Paso 3 [1, 3, 6]
- Paso 4 [1, 3, 6, 4]
- Paso 5 [1, 3, 6, 4, 2] <- como todos los adyacentes de 4 ya fueron agregados se busca la arista de 
menor peso que pueda incorporar un nuevo vértice.
- Paso 6 [1, 3, 6, 4, 2, 5] <- Al descubrir todos los vértices el algoritmo finaliza.

__Pseudo Código__
```
// Prim construye un árbol de recubrimiento de costos mínimo T para G
PRIM(G, T){
    // Inicializar el árbol de recubrimiento T
    T = {};

    // Inicializar el conjunto de vértices S
    S = {1};

    while(S != V){
        elegir una arista(u,v) de mínimo costo / u pertenece S y v pertenece a V-S
        T = T U {(u,v)};
        S = S U {v}
    }
}
```

## KRUSKAL
- Comienza con un bosque cuyos árboles son los vértices del grafo.
- En cada paso, __selecciona la arista de mínimo costo que conecta dos árboles distintos.
- Termina cuando el bosque tiene un solo árbol.


*Ejemplo*  

`vertices [1,2,3,4,5,6]`

_Matriz de Adyacencia_

```
X 1 2 3 4 5 6
1 0 6 1 5 0 0
2 6 0 5 0 3 0
3 1 5 0 5 6 4 
4 5 0 5 0 0 2
5 0 3 6 0 0 6
6 0 0 4 2 6 0
``` 
```
Atención! Los pesos se encuentran ordenados de forma ascendente para 
hayar árbol mínimo y descendente apra hayar árbol máximo
```

1. [{1,3}, 1]
1. [{4,6}, 2]
1. [{2,5}, 3]
1. [{3,6}, 4]
1. [{1,4}, 5]
1. [{2,3}, 5]
1. [{3,4}, 5]
1. [{1,2}, 6]
1. [{3,5}, 6]
1. [{5,6}, 6]

- _Paso 0_:  [{1}, {2}, {3}, {4}, {5}, {6}]
- _Paso 1_:  [{1, 3}, {2}, {4}, {5}, {6}]
- _Paso 2_:  [{1, 3}, {2}, {4, 6}, {5}]
- _Paso 3_:  [{1, 3}, {2, 5}, {4, 6}]
- _Paso 4_:  [{1, 3, 4, 6}, {2, 5}]
- _Paso 5_:  [{1, 3, 4, 6, 2, 5}] 

__Pseudo Código__
```
Kruskal(G){
    // Inicializar el árbol de recubrimiento T.
    T = {}; 

    // Aristas de G ordenadas ascendentemente por costo.
    Aristas;

    // Inicialización: conjunto de conjuntos disjuntos.
    Componentes;

    while( |Componentes| > 1) {
        
        {u, v} = A.Primero() // <- elegir árista de mínimo coste.
        
        Aristas.EliminarPrimero();
        
        if(u y v pertenecen a distintos conjuntos C1, y C2){
            T = T U { {u, v} };
            Componentes -> reemplazar C1 y C2 por (C1 U C2); 
        }
    }
}
```

__Análisis de complejidad__
Siendo e la cantidad de aristas de G y n la cantidad de vértices de G.

T_kruskal(e, n) pertenece O(e log n)