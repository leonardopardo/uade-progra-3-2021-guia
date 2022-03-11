# Backtraking
Es una técnica que intenta buscar una solución a problema, no interesa el costo. Es un método de búsqueda exaustiava que genera un arbol y realiza un busqueda en profundidad, si no cumple la condición retornará
un nivel y volverá 

## Problema de las _N_ reinas
Se deben colocar N reinas en un tablero de N casilleros de tal manera que las reinas no deben
amenazarse. El resultado corresponde e un array de n posiciones [0, 1, 2,...,n-1, n] donde en
cada indice se representa la columna y su valor representa la fila en la que se encuentra la
reina.
__Ejemplo__
[2,0,3,1]
- reina en la posicion columna 0 fila 2
- reina en la posicion columna 1 fila 0
- reina en la posicion columna 2 fila 3
- reina en la posicion columna 3 fila 1

   0 1 2 3
0 |-|x|-|-|
1 |-|-|-|x|
2 |x|-|-|-| 
3 |-|-|x|-|

__Pseudo Código__
CONST REINAS = N;
boolean Reinas(int[] S, int columna){

    if(columna >= N) return false;

    boolean flag = false;

    S[columna] = 0;

    for(i=0; i < N; i++){
        S[columna] = S[columna] + 1;

        if(PosicionValida(S, columna)){
            if(columna != N){
                flag = Reinas(S, columna + 1)
            }else{
                flag = true;
            }
        }
    }

    return flag;
}

boolean PosicionValida() {

}