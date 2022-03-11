# Calculo de Complejidad

## Concatenación, Selección, Iteración

__Concatenación__

 `T1(n) + T2(n) + ... + Tk(n) <= (c1 + c2 + ... + ck) * ( max( f(n), g(n), ..., z(n) ) )`

__Selección__

 `T(n) pertenece O(max(f(n), g(n))`

__Iteración__

 `T(n) = tc + (tc + ts) * iteraciones`

## Algoritmos Recursivos

__Método de sustracción__  

T(n) = 
- `c` si 0 <= n < b
- ` aT( n - b ) + p(n)` si n >= b

T(n) pertenece
- `Theta(n^k)` si a < 1
- `Theta(n^k+1)` si a = 1
- `Theta(a^(n/b))` si a > 1 

__Método de división__  

T(n) = 
- `c` si 0 <= n < b
- ` aT( n / b ) + p(n)` si n >= b

T(n) pertenece
- `Theta(n^k)` si a < b^k
- `Theta(n^k log n)` si a = b^k
- `Theta( n^[log_b(a)] )` si a > b^k 

__a:__ es la cantidad de llamadas recursivas que se ejecutan efectivamente para el peor caso.

__b:__ es la cantidad de unidades en la que se disminuye o divide el tamaño de la entrada.

__k:__ es el grado del polinomio que representa el tiempo de ejecutar las sentencias fuera de la llamada recursiva