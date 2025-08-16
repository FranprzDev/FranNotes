Una Gramática es $$<\Sigma_N, \Sigma_T, P, S>$$Este tipo de gramáticas corresponden al tipo 3, sus reglas pueden tener el formato regular por derecha de o regular por izquierda; pero no ambos a la vez. También incluyen reglas donde los no terminales derivan a un único terminal. Estos solo generan lenguajes regulares y sirven para describir el nivel lexicográfico del lenguaje. El modelo que acepta este tipo de lenguajes es un **autómata finito**
Reglas del tipo:
$N_1 \rightarrow wN_2$
$N_1 \rightarrow N_2w$
$N_i \rightarrow w$

El formato estándar es utilizado con el objetivo de facilitar el procesamiento de las reglas de producción; se definen estándares para cada tipo de gramática según la jerarquía de Chomsky.
La FNC3 es la siguiente:
**Reg Der.** $N_1 \rightarrow tN_2$
**Reg Izq** $N_1 \rightarrow N_2t$
**Reg Der o Izq** $N_1 \rightarrow t$
Donde $N_i \in \Sigma_N \space, t \in \Sigma_T$ 

Puede tener la regla de borrado, $S \rightarrow \lambda$  en cualquier caso S no debe aparecer en la parte derecha.

## Método para obtener la FNC3:

1) Eliminar las reglas innecesarias
		Son aquellas que no cumplen con la FNC3
		Aquellas reglas de redominación
2) Eliminar el axioma S de la derecha, si es que $\lambda \in L(GR)$
		Si el axioma S aparece a la derecha de alguna regla, de modo tal que produciendo se genera $S \rightarrow \space *\lambda$ .
		Para hacer esto, tenemos que hacer un cambio por un nuevo axioma $S_1$ de modo tal que genere $S_1 \rightarrow S | \lambda$ 
3) Eliminar reglas de redenominación,  $N_1 \rightarrow N_2$
4) Eliminar reglas de borrado $N \rightarrow \lambda$
		Todas aquellas reglas que surgen de remplazar lambda en la sustitución son remplazadas por lo que daría si este lambda no estaría especificamente.
5) Realizar las sustituciones necesarias para reducir a uno la longitud de las secuencias de terminales.
		Hay que llevarlos a la FNC3, de modo tal que quede como una gramatica por izquierda o por derecha; pero que sea un solo no terminal junto con un terminal por derecha o izquierda segun corresponda.
## Equivalencia entre GR por derecha y GR por izquierda
Los dos formatos de gramáticas son equivalentes entre sí, para esto se utiliza el siguiente algoritmo:
1) Si el axioma está en lqa derecha; se transforma a la  GR de la siguiente forma:
	1) Agregar un nuevo símbolo no-terminal L 
	2) Si S es el axioma, y $t \in \Sigma_T \space y \space N \in \Sigma_N$ entonces
		1) Para cada regla de la forma $S \rightarrow Nt \space o \space S \rightarrow$ t, se crea una regla $L \rightarrow Nt \space o \space L \rightarrow t$ 
		2) Cada regla de la forma $N \rightarrow St$ se cambia por la regla $N \rightarrow Lt$ 
	3) Se crea un grafo dirigido
		1) Un nodo por cada no-terminal N y otro para $\lambda$ 
		2) Para cada regla de la forma $N_1 \rightarrow N_2t$ se crea un arco desde el nodo N_1 al nodo N_2 con rotulo t 
		3) Para  cada regla de la forma $N \rightarrow t$ se crea un arco desde el nodo $N \space a \space \lambda$ 
		4) Si existe la regla de $S \rightarrow \lambda$, entonces se crea una regla para si solo
	4) Se transforma el grafo de la siguiente manera.
		1) Se intercambian las etiquetas de los nodos S y $\lambda$
		2) Se invierte el sentido de todos los arcos
	5) Se transforma el grafo en un conjunto de reglas
		1) Para cada arco etiquetado con t que va de un nodo al otro nodo $N_1 \rightarrow tN_2$ 
		2) Para cada arco etiquetado con t que va del nodo N al nodo $\lambda$ se crea la regla $N \rightarrow t$ 
		3) Si existe un arco del nodo del axioma S al nodo $\lambda$ se crea la regla $S \rightarrow \lambda$

De forma similar al revés.
