# Parte 3: Greedy

1. Cambio de monedas: Dado un conjunto C de N tipos de monedas con un número ilimitado de ejemplares 
de cada tipo, se requiere formar, si se puede, una cantidad M empleando el mínimo número de ellas. 
Por ejemplo, un cajero automático dispone de billetes de distintos valores: $100, $25, $10, $5 y $1, 
si se tiene que pagar $289, la mejor solución consiste en dar 10 billetes: 2 de $100, 3 de $25, 1 de 
$10 y 4 de $1.

2. Problema de la Mochila: Se tienen n objetos y una mochila. Para i = 1,2,..n, el objeto i tiene un 
peso positivo pi y un valor positivo vi. La mochila puede llevar un peso que no sobrepase P. El 
objetivo es llenar la mochila de tal manera que se maximice el valor de los objetos transportados, 
respetando la limitación de capacidad impuesta. Los objetos pueden ser fraccionados, si una fracción 
xi (0 £ xi £ 1) del objeto i es ubicada en la mochila contribuye en xi*pi al peso total de la mochila 
y en xi*vi al valor de la carga.