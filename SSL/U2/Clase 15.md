El autómata finito esu n caso particular de una MT, es la máquina más restrictiva de todas, este modelo matemático representa la solución del problema de aceptación de lenguajes de tipo 3 o Lenguajes Regulares, de hecho el AF es una MEF de tipo Moore, con dos simbolos de salida; uno de aceptación y otro de rechazo; de modo que los estados están comprendidos implicitamente, de este modo se simplifica el modelo integrando las salidas con los estados.

## Funcionameinto de un AF
1) Lee un símbolo del a cinta de entrada y mueve el cabezal a la derecha
2) De acuerdo al **estado actual** y al símbolo leído, transiciona a un **nuevo estado** (que puede ser el mismo)
3) Repite 1 y 2 hasta que lee completamente la palabra, si encuentra algún **estado final** se dice que la palabra escrita es aceptada; y en caso contrario es rechazada, o hasta que se llega a un estado en el que no está definida una transición, entonces se dice que el AF se **bloquea** y la secuencia está rechazada.

## Definición formal de un AF
$$
AF = < Q, \Sigma, q_0, F, f >
$$
Donde:
- Q $\rightarrow$ Conjunto finito y no vacío de estados.
- $\Sigma \rightarrow$ Alfabeto de los símbolos de entrada
- $q_0 \rightarrow$ Estado inicial  (Pertenece a Q)
- $F \rightarrow$ Conjunto de estados finales
- $f \rightarrow$ Función de control definida como: $f: Q x \Sigma \rightarrow Q$

El criterio de aceptación está dado por llegar a un estado final (F) y que la función de transición sea a un estado final.

El lenguaje universal de los AF queda dividido en 2 ($\Sigma^*$):
- Todas las palabras aceptadas por el AF
- Todas las palabras rechazadas por el AF

Es decir, para todo LR existe un AF capaz de aceptarlo y a la vez rechazar a su complemento, esto es importante ya que el problema de las LR siempre tiene solución mediante AF.

Al igual que el resto de modelos, la relación de transición puede ser **detemrinista** o **no determinista**, pero en este caso se puede demostrar que el **AF** es **determinista** por naturaleza.
Es decir que todo AF no-determinista tiene un equivalente determinista.

**Despues de una investigación llegué a la conclusión que:**
**Esto se debe pura y exclusivamente que un AF es en realidad una MEF de tipo Moore donde la propiedad principal para que pase a ser un AF es que esta sea determinista.**

## Descripción instantánea
Requiere las siguientes especificaciones:
- Estado actual del AF
- Contenido que falta leer de la cinta de entrada

Esta es la configuración del AF.

## Lenguaje Aceptado por un AF
Es el conjunto de palabras que partiendo de una configuración inicial, llegan a una configuración que contiene un estado final del Af y el total de la entrada leída.
$$
 L(AF) = \{w / w \in \Sigma^* \\^ q_0w|- \space y \space ^*q_f \space y \space   q_f \in F \}
$$

## Autómata Conexo
Un AFD se dice conexo cuando todos sus estados son accesibles desde el estado inicial
## Autómata Completo
Un AFD se dice completo cuando todos sus estados tienen transiciones con cada uno de los símbolos de entrada válidos
## Estado Sumidero
Un estado se llama sumidero cuando no es final y transiciona con todos los símbolos de entrada a sí mismo, es un estado de rechazo.
## Estado Generador
Un estado se llama generador cuando solo salen transiciones desde él, es útil cuando es inicial.

## Representación Matricial
Cuando tenemos un AF completo conviene representación su función de transición con una matriz cuyas columnas representan los símbolos de entrada y sus filas los estados posibles.

## Paso a paso para hacer Conexo un AF
Se eliminan los estados inaccesibles y todas las transiciones que salen o llegan a ellos, existe una correspondencia entre estos estados y los no terminales inútiles de la GR.
## Completar un AF
Si existe un estado sumidero, o algún estado del cual no salgan transiciones enviaremos todas las transiciones faltantes hacia ese estados; si no agregaremos un sumidero nuevo y procedemos igual.

## Equivalencia y Minimización
Dados los AFD $A_1$ y $A_2$ se dice que son equivalentes si y solo si los lenguajes que aceptan son iguales.
$$
A_1 \equiv A_2 \iff L(A_1) = L(A_2)
$$
## Minimización de un AFD
El AFD minimo es aquel que tiene menos cantidad de estados.

## Extensión de la función de transición
Dada la función original:
$$
f : Q \times \Sigma \rightarrow Q
$$
La función extendida será:
$$
f' : Q \times \Sigma^* \rightarrow Q

$$
Esto se debe a tener en cuenta dos casos, el base y el recursivo:
- **Caso base** Si es la palabra vacía $\lambda$ , entonces $f'(q, \lambda) = q$ por lo tanto el estado no cambia.
- **Caso recursivo** Si la palabra es de la forma $xw$ donde $x \in \Sigma$, es el primer símbolo y $w \in \Sigma^*$ vendría a ser justamente el resto de la palabra, entonces.
$$
f'(q, xw) = f'(f(q,x), w)
$$
	De esta forma nos aseguramos de ir aplicando recursivamente a todos los estados necesarios..
Ej:
Si tengo $f(2,a) = 3 \space y \space f(3,b) = 6$ entonces:

$$
f'(2, ab) = f'(f(2,a), b) = f'(3, b) = f'(6, \lambda) = 6 
$$

## Redefinición de lenguaje aceptado por un AFD
En base al concepto anterior, podemos decir que el lenguaje de todas las palabras aceptadas por el automata será:
$$
L(AFD) = \{w / w \in \Sigma^* \space y \space f'(q_0,w)\in F\}
$$

Es decir, todas las palabras del universo del alfabeto de entrada que hagan transicionar al AFD desde su estado inicial hasta algún estado final.

## Equivalencia entre dos estados de un AFD
Dos estados $q_1$ y $q_2$ $\in Q$ de un AFD son equivalentes si:
$$

q_1 \equiv q_2 \iff \forall w \in \Sigma^*,\ f'(q_1, w) \in F \iff f'(q_2, w) \in F

$$

Si las transiciones de $q_1$ con w llegan a un estado final, y las de $q_2$ también llegan a un estado final, y pasa lo mismo al revés, ninguno de los 2 llega a un estado final; entonces esos estados son equivalentes.
## Equivalencia de Orden N
Para obtener un algoritmo con los subconjuntos de estados equivalentes de un conjunto de estados dado, se define la **Equivalencia de Orden N entre dos estados**
### De un mismo AFD
$$

q_1 \equiv_N q_2 \iff \forall w \in \Sigma^* \space y \space |w|\ \leq N, f'(q_1,w)\in F \iff f'(q_2,w)\in F

$$
### De dos AFD distintos
$$
q_1 \equiv_N q_2 \iff \forall w \in \Sigma^* \space y \space |w|\ \leq N, f_1'(q_1,w)\in F_1 \iff f_2'(q_2,w)\in F_2
$$

## Relación entre Equivalencia y N-Equivalencia
Es una forma de comparar dos estados de un AFD sin tener que probar todas las palabras posibles, se verifica si se compartan igual para todas las palabras de longitud menor o igual a N.
- Esto exige que al menos dos estados se comporten igual para todas las palabras posibles, pero como es imposible comprobarlo usamos el orden N. Si dos estados siguen siendo indistingubles para palabras de lonngitud 0,1,2, ..., N; entonces probablemente son equivalentes.
- Si dividimos los estados en clases de equivalencia por longitud de palabra, el proceso se  lo estabiliza en K-1 pasos, para esto verificamos hasta N = K - 2, donde es suficiente para saber si dos estados son equivalentes.

Si usamos AFD distintos, entonces son equivalentes si se comportan igual para todas las palabras de longitud menor o igual a $K_1+K_2-2$ 
## Clases de equivalencia de un conjunto de estados
Dado un conjunto de estados de un AFD o la unión de los conjuntos de estados de dos o más AFD, se llama Clases de Equivalencia a los subconjuntos de estados equivalentes; haciendo extensible a N-Equivalencia si hace falta.
 ## Conjunto cociente de un conjunto de estados
 Dado un conjunto de estados de un AFD o la unión de los conjuntos de estados de dos o más AFD, llamamos el Conjunto Cociente al conjunto de todas las **clases de equivalencia** de un conjunto de estados
 ## Partición N de un Conjunto de Estados
 Dado un conjunto de estados de un AFD o la unión de los conjuntos de estados de dos o más AFD, llamamos **Partición N** al conjunto de todas las clases de **N-Equivalencia** del conjunto de estados.

## Verificación de Equivalencia de AFD

## Minimización de un AFD

## Equivalencia por ISOMORFISMO
