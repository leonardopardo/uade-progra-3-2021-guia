# DIVIDE Y CONQUISTA

Tecnica de diseño de algoritmos que resuelve un problema recursivamente, aplicando tres pasos en cada nivel de la recursión:  
- __Divide__ el problema en un número de subproblemas que son instancias menores del mismo problema.  
- __Conquista__ los subpromeas resolviéndolos recursivamente. Si el tamaño del subproblema es suficientemente pequeño, lo resuelve de manera directa.
- __Combina__ las soluciones de lso subproblemas para obtener la solución al problema original

## Caractéristicas de los problemas
- El problema debe admitir una formulación recursiva
- Los subproblemas deben ser del mismo tipo que el problema original, pero con datos de tamaño estrictamente menor.
- El tamaño de los datos que manipulen los subproblemas ha de ser lo más parecido posible.

__Ejemplo: Factorial de n__

```
int factorial(int n) {
    if( n == 1) {
        return 1;
    } else {
        return n * factorial(n-1);
    }
}
```
_a_ = 1  <- se llama una sola ves a la llamada recursiva  
_b_ = 1  <- se decrementa en una unidad el tamaño de la entrada  
_k_ = 0  <- no hay ningúna otra operación  

Dado que `a = b` entonces  
`T(n) = n^(k+1)`  
`T(n) = n^(0+1)`
`T(n) = n^1`  
`T(n) = n`      

Por lo tanto T factorial (n) pertenece O(n)

__Ejemplo: Mergesort__  
```
int[] A = { 5, 2, 4, 7, 1, 3, 2, 6 };
void mergeSort(A, i, d) {
    if (i < d) {
        m = Math.floor( ( i + d ) / 2 );
        mergeSort(A, i, m);
        mergeSort(A, m + 1, d);
        merge(A, i, m, d);
    }
}
```
_a_ = 2  
_b_ = 2  
_k_ = polinomio de grado 1  

 Dado que `a = b^k` entonces  
 `T(n) = n^k log n`    
 `T(n) = n^1 log n`  
 `T(n) = n log n`
 
 Por lo tanto T mergesort(n) pertenece a O(n log n)

__Ejemplo: Quicksort__  
```
void quickSort(int A[], int inicio, int final) {
    if( inicio < final ) {
        int p = Particion(A, inicio, final) // retorna la posición del pivote

        quickSort(A, inicio, p-1);
        quickSort(A, p+1, final);
    }
}
```
***LA COMPLEJIDAD DE QUICKSORT ESTÁ DADA POR COMO QUEDA LA PARTICIÓN, SI ES DESBALANCEADA PUEDE QUEDAR DEL ORDEN n^2***

__Esquema algorítmico de Divide y Conquista__

```
DyC(P) {
    
    // Caso base o solución directa
    if( SIMPLE(P) ) {
        return solución;
    } else {
        DIVIDE P  en K subproblemas P1, P2, ... , PK
        return ( COMBINA(DyC(P1), DyC(P2), ... , DyC(P3)) ); 
    }
}

```

```
<tipo> DyC(<tipo> x) {
    if( <caso base> ) {
        return <solución conocida>;
    } else {
        <tipo> parte = Parte(x);
    }

    return Combinar(DyC(parte));
}
```

__Análisis de Eficiencia__

T(n) =  
- `g(n)` si n pequeño  
- `T(n1) + T(n2) + ... + T(nk) + f(n)` si n suficientemente grande  

__T(n)__ es el tiempo de ejecución de DyC con n entradas.  
__g(n)__ es el tiempo para resolver directamente las entradas pequeñas.  
__f(n)__ es el tiempo de dividir P en subproblemas y combinar las soluciones.
