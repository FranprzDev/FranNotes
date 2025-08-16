## Configuración de un $AF-\lambda$
Una descripción instantánea de un AF No Determinista con transiciones $\lambda$ requiere:
- Subconjunto de posibles estados actuales del $AF-\lambda$ 
- Contenido que falta leer de la cinta de entrada

Ejemplo: $\{q_j, \dots, q_k\}e_i, \dots, e_n$
## Lenguaje aceptado por un $AF-\lambda$
Es el conjunto de palabras que partiendo de una configuración inicial, llegan a una configuración que contiene en el subconjunto de estados al menos un estado final del $AF-\lambda$ y el total de la entrada leida.
$$
L(AF) = \{w / w \in \Sigma^* \space y \space \{q_0, \dots, q_i\}w |- ^*\{q_j,\dots,q_F,\dots,q_k\} \space y \space q_F \in F \}
$$
Por otro lado, si no se llega a un subconjunto de estados finales, entonces esto produce un bloqueo en el modelo; y son rechazadas por el af.

## Conversión de un $AF-\lambda$ a AFD
Se definen dos funciones sobre un subconjunto de estados T y el alfabeto de entrada $\sigma$ de $AF-\lambda$ 
1) $Clausura-\lambda$ Es la clausura transitiva del subconjunto T con transiciones $\lambda$, es decir el subconjunto T más todos los estados a los que se puede llegar desde T con una o más transiciones $\lambda$
2) $Destino(T,x)$ Es el destino directo de T con la lectura de un símbolo x del alfabeto de entrada, es decir el subconjunto de todos los estados a los que tiene transiciones T con el símbolo x.

## Complejidad de los Autómatas Finitos
Dada una ER $R$ con el alfabeto base $\Sigma$, la cantidad de estados que tendría el $AF-\lambda$ con el método de Thompson se define como:
1) Por cada $x \in \Sigma$ se necesitan 2 estados
2) Por cada operación $+ \space o \space *$ se agregan 2 estados más
3) La operación $.$ no agrega estados.
Entonces la cantidad de estados será:
$$
|Q_1| = 2x|r|
$$
Por otro lado si partimos de un $AF-\lambda$ con $|Q_1|$ estados, la cantidad de estados $|Q_2|$ que tendrá el AFD obtenido mediante el método de construcción de subconjuntos será:
4) La cardinalidad del conjunto potencia $2^{Q_1}$.
5) La cantidad de estados $|Q_2|$ del AFD será menor o igual que la cantidad máxima de subconjuntos de $Q_1$ 
6) La cardinalidad de $Q_1$ es proporcional al módulo de la ER
Entonces se puede decir que:
$$
|Q_2| \leq 2^{|Q_1|} \propto 2^{|r|}
$$

Si queremos obtener la cantidad máxima K de transiciones que se realizarán para una secuencia **w** de entrada, al momento de ser aceptada o rechazada, entonces:
1) En cualquier **AFND**, la cantidad de transiciones que puede tener un estado con un símbolo **"x"** determinado, es como máximo la cantidad total de estados.
2) La cardinalidad del conjutno $Q_1$ de estados del AF es proporcional al módulo de la ER
Entonces sabiendo esto, podemos afirmar que:
$$
K \propto |r| x |w|
$$
Si consideramos el caso de un AFD y nos hacemos la misma pregunta, respecto a la cantidad máxima K de transiciones que se realizan con una secuencia **"w"**, vemos que al ser determinista hay una sola posibilidad de transición desde un estado para un símbolo determinado en el alfabeto de entrada, por consiguiente la cantidad de transiciones será igual a la longitud o módulo de **w**.
Entonces:
$$
K = |w|
$$

Podemos definir, lo siguiente:

![[Pasted image 20250723232525.png]]
Con esta tabla, entonces se puede concluir lo siguiente:
El AFD temporalmente es más rápido, por que ocupa menos estados de transición para aceptar o rechazar una palabra.
En cambio un $AF-\lambda$  resuelve la aceptación mucho más lento, pero se necesitan menos estados para la implementación de uno de estos.