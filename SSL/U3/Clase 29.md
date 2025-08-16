# Autómata de Pila (AP)
El autómata de pila es un caso particular de una MT, pero también lo podemos ver como un Af, que además de su cinta finita de entrada tiene una cinta auxiliar infinita, llamada cinta de apilamiento; ya que sobre esta misma se apilan y desapilan símbolos auxiliares, este modelo matemático representa la solución al problema de aceptación de lenguajes de tipo 2 o LIC.

Se escribe en la cinta de entrada la palabra que se desea analizar $e_i$, la misma termina con un símbolo de fin de cadena que normalmente es un espacio en blanco $\Delta$. 
Por otro lado la cinta de apilamiento se encuentra vacía, lo cual se indica con el símbolo especial $z_0$ en el tope o cima de la misma, en esta situación el AP está en el estado inicial.

## Como funciona un AP
1) **Lee un símbolo** de la cinta de entrada y mueve el cabezal a la derecha
2) **Descarga (POP)** una secuencia de símbolos de la cinta de apilamiento, suele ser un solo símbolo, lee un símbolo del tope y mueve el cabezal a la derecha; exceptuando cuando llegó al extremo derecho.
3) De acuerdo al **estado actual**, al símbolo leído y a la secuencia descargada:
	1) **CARGA (PUSH)** en la cinta de apilamiento una secuencia de símbolos auxiliares. Para lo cual, mueve el cabezal a la izquierda, escribe un símbolo y repite estas acciones para toda la secuencia.
	2) Transiciona a un **NUEVO ESTADO** (que puede ser el mismo)
4) Repite 1, 2 y 3 hasta que llega a alguno de los **estados finales** en cuyo caso se dice que la palabra escrita inicialmente es **aceptada**, o hasta que llega a un estado que no está definida la transición entonces el AP se **bloquea** y la secuencia de entrada es **rechazada**

Las acciones de **LEER, POPEAR Y PUSHEAR** pueden ser nulas, lo que se representa con $\lambda$ 

## Definición formal de un AP
$$
AP = < Q, \Sigma_E, \Sigma_P, q_0, z_0, F, f> 
$$
Donde:
- $Q$ conjunto finito y no vacío de estados
- $\Sigma_E$ Alfabeto de símbolos de entrada.
- $\Sigma_P$ Alfabeto de símbolos auxiliares de la pila
- $q_0$ Estado inicial $\in Q$
- $z_0$ Símbolo inicial de la pila $\in \Sigma_P$ 
- $F$ Conjunto de estados finales $\in Q$
- $f$ Relación de control o transición

Donde $f$ se define como:
$$
f: (Q-F) \times (\Sigma_E\cup \{\Delta, \lambda\}) \times \Sigma_{P}^* \Rightarrow 2^{Q\times\Sigma_P^*}
$$
El producto cartesiano entre la diferencia entre todos los estados y los estados finales, el alfabeto de entrada unido con el símbolo de pila vacía y lambda, y la estrella de kleene del alfabeto de símbolos de la pila.
Como se ve en el rango, $2^{Q \times \Sigma_P^*}$ esto quiere decir que puede tener varias alternativas de respuestas para un mismo estímulo.

## Convención para la carga y descarga de la pila
### Para Pushear
Suponemos que la secuencia $x_1x_2 \dots x_N$ se introduce de derecha a izquierda a la pila (osea desde $x_N$  y se saca de izquierda a derecha, o sea desde $x_1$ 
### Para Popear
Para sacar de la pila lo hacemos desde izquierda a derecha, es decir primero saldrán $x_1$, $x_2$ y así en orden hasta el último.

Ejemplo práctico:
![[Pasted image 20250725010817.png]]

 $\Sigma_E^*$ es conocido como el lenguaje universal, que quedará dividido 
- Todas las palabras aceptadas por el AP
- Todas las palabras rechazadas por el AP
Para toda LIC, existe un AP que es capaz de aceptarlo y a la vez de rechazar su complemento, esto es importante ya que el problema del reconocimiento de las LIC, tiene solución

## Representación
Para la representación formal de la función de transición; se puede utilizar la tabla de transición donde tendremos que indicar el estado actual, el simbolo que lee, lo que saca de la pila, el estado nuevo, y lo que agrega a la pila.

En este caso, pasamos de usar un símbolo en la flechita, a dos símbolos a la flechita a llegar hasta 3 símbolos en la flechita; que es la forma que se usa ahora.
Se compone por medio de una terna **(estado actual, símbolo que se lee, secuencia que se descarga en la pila)**.
Estos modelos  pueden ser **Deterministas** y **No Deterministas** pero se puede demostrar que el Ap es ND por naturaleza, tanto en su rango como en su dominio; esto significa que no todos los **AP ND** tienen un equivalente determinista.

Por lo tanto:
- $C_1 = Conjutno \space de \space AP \space Deterministas$
- $C_2 = Conjutno \space de \space AP \space No \space Deterministas$

$$
Podemos \space decir \space que \space C_2 \subset C_1  
$$

Ejemplo con un AP:
![[Pasted image 20250725012113.png]]

Si definimos el AP sería el siguiente:

$$
AP = < Q, \Sigma_E, \Sigma_P, q_0, z_0, F, f> 
$$
Donde:
- $Q = \{1,2,3\}$ 
- $\Sigma_E = \{1,2\}$ 
- $\Sigma_P = \{\#, A\}$ 
- $q_0 = \{1\}$ 
- $z_0 = \{\#\}$  
- $F = \{3\}$
- $f$ Relación de control o transición
Donde $f$ se define como:
$$
f: (\{1,2,3\}-\{3\}) \times (\{1,2\}\cup \{\#, A\}) \times \Sigma_{P}^* \Rightarrow 2^{Q\times\Sigma_P^*}
$$
$$
f: \{1,2\} \times \{1,2, \#, A\} \times \Sigma_{P}^* \Rightarrow 2^{Q\times\Sigma_P^*}
$$
y ya de aqui ya no se hacer eso
Pero bueno, supongamos siguiendole el caminito: 
![[Pasted image 20250725015815.png]]
![[Pasted image 20250725015820.png]]
![[Pasted image 20250725015827.png]]
![[Pasted image 20250725015834.png]]
![[Pasted image 20250725015840.png]]

## Configuración del AP
La descripción instantánea del AP se da con:
- Estado actual del AP
- Contenido de la cinta de apilamiento
- Contenido que falta leer de la cinta de entrada

Entonces quedaría algo como:
$$
e_i, \dots, e_nq_kz_m,\dots,z_0
$$
## Lenguaje aceptado por un Ap
El lenguaje aceptado es el conjunto de palagbras que partiendo de una configuración inicial llegan a una configuración que contiene un estado final del AP y el total de la entrada leída

Representado como:
$$
L(AP) = \{w / w \in \Sigma_E^* \space y \space w\Delta q_0z_0 |-_* q_F \beta \space y \space q_F \in F \space y \space \beta \in \Sigma_P^* \}
$$

Todas las palabras que partiendo de una configuración inicial llegan a una configuración donde se produce un bloqueo se dice que son rechazadas por el AP.

## Criterios de aceptación de un AP
### Por estado final
Es la forma tradicional de aceptación, se acepta una secuencia de entrada cuando al leer el final de cadena transiciona a un estado final.

$$
L(AP)={w∣w∈Σ_E^∗ \space ∧ \space wΔq_0z_0⊢∗q_Fβ \space ∧ \space q_F\in F\space ∧ \space β∈Σ_P^∗}
$$
Las palabras w, tal que w pertenezca al conjunto de todas las palabras posibles, incluyendo la vacía que se pueden formar con el alfabeto de entrada **y** por la configuración de la pila $(w \Delta q_0z_0)$ con una secuencia de derivaciones llegando a un estado final $q_F \in F$ y con un $\beta \in \Sigma_P^*$ siendo el contenido final de la pila; y se llegó al $\Delta$, indicando que toda la palabra fue leida entonces la palabra estará aceptada por el AP. 
### Por pila vacía
En este nuevo criterio se acepta cuando llega al final de la cadena y la pila está vacía.
$$
L(AP) = \{w | w \in \Sigma_E^* \space ∧ \space w \Delta q_0z_0 ⊢^* q_i \beta ∧ q_i \in Q\}
$$
Donde $\beta = \lambda$ es decir que ese $\beta$, no existe; osea que no hay nada en la pila, entonces la palabra es aceptada. 
La formal es:
$$
L(AP) = \{w | w \in \Sigma_E^* \space ∧ \space w \Delta q_0z_0 ⊢^* q_i ∧ q_i \in Q\}
$$
(Yo lo cambié, pero la formal es de arriba.)

En ambos casos, el rechazo se producirá por el bloqueo del modelo; es decir cuando se produce un estimulo que no está definido.
## Cambios de criterios
1) Si el modelo acepta **por estado final** y al llegar al mismo la pila no está vacía, entonces se coloca un autolazo con etiquetas **$(\lambda,z_i,\lambda)$** para cada $z_i\in \Sigma_P$ hasta dejar la pila vacia.
2) Si el modelo acepta **por pila vacia**, colocamos transiciones $(\Delta, z_0, \lambda)$ desde todos los estados donde se puede producir la aceptación, hacia un estado final nuevo; siendo $z_0$ el símbolo inicial de la pila y $\Delta$ el final de cadena.
3) 