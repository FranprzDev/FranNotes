# Clase 27

# Gramáticas independientes del Contexto (GIC)
Definimos a una GIC como:
$$
GIC = <\Sigma_N, \Sigma_T, P, S>
$$
Las reglas de P pueden ser:
$$
N \rightarrow \beta
$$
Donde: $N \in \Sigma_N \space y \space \beta \in (\Sigma_N \cup \Sigma_T)^*$ 

El lenguaje, es el independiente del contexto que pertenece a las gramáticas del tipo 2 según la Jerarquía de Chomsky, y pertenece al nivel sintáctico; el modelo que lo representa es el **automata de pila**

## Diseño de una GIC
Para construir una GIC a partir de un LIC se recurre a distintos artificios.
1) Adaptación de una gramática
	Se pueden realizar modificaciones sencillas a una gramática conocida para obtener la del lenguaje requerido, no hay una forma como tal para hacer esto, si no que consiste en darse cuenta y ser pillo.
	El ejemplo que se proporciona es el siguiente:
	![[Pasted image 20250724015822.png]]
	Dado esto, si queremos generar una nueva $LIC$ que cumpla que:
	$LIC8 = \{a^nb^m / n,m \geq 0 \space y \space n > m\}$
	Entonces lo que debemos hacer es pensar donde poner las reglas, el ejemplo sugiere lo siguiente:
	![[Pasted image 20250724020059.png]]
2) Mezcla de Gramáticas
	Podemos combinar dos gramáticas, de manera que la gramática resultante contenga la unión de todas las reglas de ambas gramáticas, para esto se debe tener en cuenta los simbolos terminales y no terminales, y que el axioma debe ser el mismo pero mezclandolo.
	![[Pasted image 20250724023912.png]]
3) Operaciones con GIC
	1) Unión
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ y $G_2=<\Sigma_{N_2}, \Sigma_{T_2},S_2,P_2>$
		La unión será aquella que genere una nueva gramática, $G_3$ tal que $L(G_3) = L(G_1) \cup L(G_2)$ Por lo tanto, para $G_3$ será la unión del alfabeto de no terminales y la unión del alfabeto de terminales, además de la unión de las reglas de producción agregando una nueva regla de producción, $S_3$ que será la unión de los axiomas de cada GR, es decir $S_3 = S_1 \cup S_2$
		![[Pasted image 20250724024608.png]]
	2) Concatenación
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ y $G_2=<\Sigma_{N_2}, \Sigma_{T_2},S_2,P_2>$ se generará una  $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ siendo la concatenación de $L(G_3) = L(G_1).L(G_2)$ 
		Donde:
		$\Sigma_{N3}=\Sigma_{N1}\cup\Sigma_{N2} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}\cup \Sigma_{T2}$
		$P_3=P_1\cup P_2\cup { S_3 \rightarrow S_1S_2 }$ 
	3) Estrella de Kleene
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^*$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}
		$P_3=P_1\cup { S_3 \rightarrow S_1S_3 | \lambda }$ 
	4) Estrella Positiva
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^+$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}$
		$P_3=P_1\cup { S_3 \rightarrow S_1S_3 | S_1 }$ 
	5) Inversa
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^-1$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1}$
		$\Sigma_{T3}=\Sigma_{T1}$
		$P_3= N \rightarrow \beta^-1 / N \rightarrow \beta \in P_1$
		 



# Clase 28

## Arbol de Derivación o de Sintaxis
Las derivaciones pueden ser representadas en forma de arbol, cumpliendo las siguientes propiedades.
1) Cada nodo tiene una etiqueta
2) La raiz tiene como etiqueta el Axioma
3) La etiqueta de los nodos que no son hojas debe estar en $\Sigma_N$ y las de las hojas en $\Sigma_T\cup \{\lambda\}$ 
4) Para armar el arbol hay que pensar en un Nodo "N" y sus nodos hijos $n_1, \dots, n_m$ con sus respectivas etiquetas $N_1,\dots,N_m$ entonces $N\rightarrow N_1,\dots N_m \in  P$

El recorrido del árbol se hace en preorden, expadiendo los no terminales que nos encontramos en el camino. 

## Ambigüedad en una GIC
Al no ser una correspondencia biunívoca, hace que para ciertas GIC existan distintos arboles de derivación, es decir que usando un criterio fijo hay más de una forma de derivar esa palabra. En este caso se dice que esas cadenas son **generadas con ambigüedad**  La realidad es que la ambigüedad puede estar en cualquier lenguaje,  y esta se corrige en lenguajes superiores; cuando no se puede se dice que es **inherentemente ambiguo del tipo i**

## Eliminación de la ambigüedad
Existen técnicas para eliminarlas, para esto se introducen nuevos no-terminales de modo que se eliminan los árboles de derivación no deseados. Para esto, no existe un algoritmo, simplemente es hacerlo y esperar que este bien hecho.

## Arbol Total de un lenguaje
El conjunto de todas las secuencias que se pueden obtener a partir de una gramática de tipo 2 o 3, se pueden representar mediante un árbol del LIC o LR.
Esta es la generalización del concepto de árbol de derivación.
En general, un árbol total del lenguaje contiene todas las palabras de dicho lenguaje, si este arbol es finito entonces el lenguaje también lo es; si es infinito, el lenguaje será infinito, y si no tiene hojas entonces el lenguaje asociado será $\Phi$
Cada camino desde la raíz hasta una hoja representa el árbol de derivación de dicha palabra; y para construir dicho arbol es necesario seguir siempre el mismo criterio **más a la derecha** o **más a la izquierda**
Cuando seguimos este criterio y obtenemos hojas repetidas, entonces la palabra es ambigua y por ende la GIC también.
## Formas de Representación de la Sintaxis de los Lenguajes de Programación
### Backus Naur Form (BNF)
La BNF es una notación para escritura de GIC, que representa la sintaxis de los lenguajes de programación que utiliza los siguientes metacaracteres:
- $<>$ Los parentesis angulares se usan para encerrar nemotécnicos que representan los NO-TERMINALES de la GIC.
- $::=$ Los cuatro puntos seguidos del igual sustituye a la flechita
- $|$ La barra vertical se usa de igual modo que la forma habitual.
- $\{\}$ Las llaves se usan para encerrar las secuencias que se repiten
	Por ejemplo la regla recursiva $A \rightarrow A\beta \space |\space \lambda$ se reemplaza por $<A> ::= {\beta}$
- $[]$ Los corchetes se usan para encerar las secuencias que son optativas.
	Por ejemplo $A \rightarrow \beta \space | \space \lambda$ se reemplaza por $<A> ::= |\beta|$ 
- $()$ Los paréntesis se usan para encerar varias secuencias alterativas con prefijo y/o sufijos comunes.
	Por ejemplo $w(x | y | z)u$ 
### Diagramas de Sintaxis
El diagrama de sintaxis es una forma gráfica de representación del nivel sintáctico de un lenguaje de programación
**Símbolos**
- **Circulito alargado:** Representa el valor de un componente léxico análogo a los terminales de la GIC
	![[Pasted image 20250724034623.png]]
- **Circulito:** Representa el valor de un símbolo espacio especial
	![[Pasted image 20250724034704.png]]
- **Rectangulito:** Implica una estructura sintáctica que tiene su propio diagrama de sintaxis, similar a los No-Terminales de la GIC
	![[Pasted image 20250724034729.png]]
- **Flechita:** Indica el componente que sigue a continuación 


# Clase 29

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


# Clase 31

## Simplificaciones de una GIC
Para obtener la FNC como la FNG de una GIC, se necesita en primer lugar simplificar la gramática eliminando reglas indeseables.

Los pasos a seguir son
1) Eliminar las reglas innecesarias
	Son producciones que no aportan nada, no cumplen con:
	$S \Rightarrow^* \space \alpha N \beta \space y \space N \Rightarrow^* \space w$
	Donde S es el axioma, $w \in \Sigma_T^*$ y $\alpha, \beta \in \Sigma^*$ 
	Reglas de la forma: $N \rightarrow N$ (Redenominación)
2) Considerar la generación de la palabra vacía
	Si $S \rightarrow^* \lambda$, entonces
	- Si el axioma no figura a la derecha se agrega la regla $S \rightarrow \lambda$ 
	- Caso contrario, si el axioma aparece a la derecha de alguna de las reglas de producción se debe realizar el siguiente artificio.
		1) Se introduce un nuevo simbolo $S_1$ 
		2) Se agregan las producciones de las reglas: $S_1 \rightarrow S \space | \space \lambda$ 
3) Eliminar las reglas de borrado $N \rightarrow \lambda$
	Partimos de una $GIC = < \Sigma_N, \Sigma_T, S, P>$
	1) Identificamos el conjunto A de los no-terminales anulables, es decir todos aquellos que cumplan con $N \Rightarrow^* \lambda$ 
		1) Inicializamos A con todos los no-terminales N para los cuales existe una producción de borrado, excepto para el propio axioma.
		2) Para cada $N \rightarrow W \in P$, Si $W \in A^+$ entonces agregar N a A.
	2) Se reemplaza las producciones de la forma $N \rightarrow \lambda$ por las reglas que surgen de sustituir los no-terminales anulables por $\lambda$, en todas las reglas que figuren exceptuando las de borrados. Si $\lambda$ pertenece a la GIC, la única regla de borrado que no debe eliminarse es cuando el axioma deriva a lambda 
4) Eliminar reglas de redenominación del tipo $N_1 \rightarrow N_2$
	Partimos de una $GIC = < \Sigma_N, \Sigma_T, S, P>$ que no tiene reglas de borrado


## Obtención de la Forma Normal de Chomsky para una GIC (FNC)
Debemos seguir los siguientes pasos:
1) **Obtener la GIC simplificada o bien formada:** Eliminar las reglas innecesarias, de borrado y de redenominación
2) **Llevar a la GIC al FNC de tipo 0** Es decir, sustituir los terminales de la parte derecha por nuevos no-terminales y se agregan las reglas **nuevo no-terminal** derivada a **terminal asociado**
3) **Reducción de la longitud** Para toda regla que no cumpla con el FNC de tipo 2, se procede a reducir la longitud mediante sustituciones, agregando los no-terminales nuevos que sean necesarios.


# Clase 33

# FNG
$$
N \rightarrow tW
$$
Con:
- $N \in \Sigma_N$
- $t \in \Sigma_T$
- $W \in \Sigma_N^*$
- Como excepción $S \rightarrow \lambda$, pero sin S a la derecha.

## Pasos para obtener la FNG
1) **Obtener la GIC simplificada,** eliminar las reglas innecesarias, de borrado y de redenominación
2) **Eliminar reglas recursivas por izquierda** Es decir reglas de la forma $N \rightarrow N \beta$ (recursividad directas) o reglas que conducen a una recursividad por izquierda en varios pasos, es decir $N \Rightarrow^* N \beta$ 
3) **Eliminación de reglas que comiencen con no-terminal** A efectos que todas las reglas comiencen con un terminal, se debe realizar una serie de sustituciones.
4) **Sustitución de sufijos con terminales** Con el fin de llegar a la FNG se transforma las reglas que tengan a la derecha sufijos con terminales.

## Eliminación de recursividades por izquierda

Para eliminar las recursividades por izquierda se reemplaza las reglas de la forma:
$$
	N \rightarrow N \alpha_1 \space  | \space N \alpha_2 \space | \space  \dots \space | \space  N \alpha_n \space | \space \beta_1  \space | \space  \beta_2 \space  | \space  \dots \space | \space  \beta_m
$$
Por las siguientes reglas equivalentes
$$
N \rightarrow \beta_1N' \space | \space \beta_2N' \space | \space \dots \space | \space \beta_mN'
$$
$$N \rightarrow \alpha_1N' \space | \space \alpha_2N' \space | \space \dots \space | \space \alpha_nN \space | \space \lambda'$$

Para realizar este proceso de forma sistemática se parte de una gramática simplificada, sin recursividades  por izquierda y se siguen los siguientes pasos:
1) Establecer un orden cualquiera para los No-Terminales $N_1,N_2,\dots, N_n$ 
2) Dividir las reglas en 3 grupos:
	1) Grupo 1: $N_i \rightarrow xw \space | \space x \in \Sigma_T, w \in \Sigma^*$ 
	2) Grupo 2: $N_i \rightarrow N_jw \space | \space$  $N_i, N_j \in \Sigma_N, i < j, w \in \Sigma^*$
	3) Grupo 3: $N_i \rightarrow N_jw \space | \space N_i, N_j \in \Sigma_N, i > j, w \in \Sigma^*$
3) Seleccionar las reglas del grupo 3 cuyo "i" sea mínimo en el orden y se las sustituye por las que se obtiene al reemplazar $N_j$ por todas las partes derechas de sus producciones; repitiendo esta regla.

**Sustitución de sufijos con terminales**
Se parte de una GIC, cuyas reglas en sus partes derechas comienzan con un símbolo terminal a excepción de la regla de borrado, si es que existe. 
Para cada relga que no cumpla con la FNG, ya que en su parte derecha tiene más de un terminal se reemplaza cada terminal, menos el primero por un nuevo no-terminal y luego se agrega la regla "nuevo no-terminal" deriva al terminal asociado.

## Factorización por Izquierda
Cuando en una GIC tenemos para un mismo no-terminal, reglas que tienen partes derechas con prefijos iguales; se produce una indeterminación en el momento de elegir una de esas reglas para resolver el problema de análisis de una palabra.
El proceso que elimina este problema se denomina factorización por la izquierda y se define como:
- Por cada $N \in \Sigma_N$ 
	- Si $N \rightarrow \beta \alpha_1 \space | \space \beta \alpha_2 \space | \space \dots \space | \space \beta \alpha_k$
	- Entonces se cambian las producciones por:
		- $N \rightarrow \beta N'$
		- $N' \rightarrow \alpha_1 | \alpha_2 | \dots | \alpha_k$





# Clase 35

# Diseño de un AP a partir de una GIC
Para construir el AP correspondiente a una GIC, se sigue el mismo proceso de derivación de palabras de dicho lenguaje; a partir del árbol de sintaxis de cada cadena, se puede usar el arbol total.
Existen 2 formas:
1) Recorrer el árbol total desde su raiz (el axioma S) hasta la hoja en cuestión, en este caso el criterio de análisis es descdenente y se utilizan derivaciones más a la izquierda.
2) Recorrer el camino inverso desde una hoja hacia la raíz, en cuyo caso el criterio de análisis es ascendente y se utilizan derivaciones más a la derecha. 

En ambos casos se puede plantear criterios de aceptación por estado final o por pila vacía, y es un modelo no-determinista (en general).

## Primer Caso: FNGreibach $\Rightarrow$ APND
Partimos de una GIC en FNG

Se toma en cuenta las siguientes convenciones:
1) Se adopta el criterio de aceptación por pila vacía
2) Se aplica un criterio de análisis descendente y derivación más a la izquierda.
3) Se supone que el símbolo inicial de la pila es el axioma y está cargado.
4) No se lee explícitamente el símbolo de final de cadena.

Para cada regla de la GIC se procede a agregar un lazo en el único estado del modelo,
![[Pasted image 20250726034233.png]]

## Segundo Caso FNChomsky $\Rightarrow$ APND
Partimos de una GIC en FNC
Tenemos en cuenta las siguientes convenciones
1) Adoptamos el criterio por estado final
2) Aplicamos un criterio de análisis ascendente y derivación más a la derecha
3) Se supone que el símbolo inicial de la pila es **#** y no está cargado
4) Se lee explícitamente el símbolo del final de cadena.

Para cada relga de la GIC se agrega un lazo en el segundo estado del modelo, tendrá la siguiente forma D
![[Pasted image 20250726041217.png]]

## Equivalencia entre LIG, GIC y AP
Para ver la equivalencia, hay que construir un algorimto para construir una GIC a partir de un AP, la idea se basa en el funcionamiento de un AP con criterio de aceptación por pila vacia; que reconoce una secuencia de símbolos; este modelo parte de un estado inicial, ya leyendo uno por uno los símbolos de $e_i$, saca y pone símbolos en la pila; pasando de un estado a otro, hasta que completa la lectura de dicha secuencia de entrada y extrae todos los símbolos de la pila.

Más formalmente, el AP para lograr que se vacie la pila, pasará de estados **p** a estados **q** mientras extrae un símbolo **X**, haciendo un push $\lambda$. 
Las ternas $(pXq)$ representan el resultado de los movimientos y son los No-Terminales de la GIC, agregando el axioma S, que será el símbolo inical de la pila.
Los terminales de la GIC serán el alfabeto ed entrada del AP.

Las reglas de la GIC serán todas las transiciones que se deben realizar por los distintos caminos del AP que conduzcan a un estado de aceptación, es decir cuando se vacía la pila.
Simplificando, se generan todas las posibilidades y se elimina las innecesarias.
Las reglas se construyen con el FNG, pero pueden tener reglas de borrado eventuales.

### Pasos a seguir
#### Obtener las reglas de la GIC
1) Para todos los estados $p \in Q$, la GIC contiene una producción
		$S \rightarrow [q_0Sp]$ 
	Donde $q_0$ es el estado inicial del AP
2) Suponemos que la función de transición $f(q,t,X)$ contiene la tupla $(r, Y_1, Y_2, \dots, Y_k)$ donde $t \in \Sigma_T$ o $t = \lambda$,  Además todos los otros son no terminales, con $q, r \in Q$ y k un número cualquiera incluido el 0.
	 Entonces
	 $$
	 [qXr_k] = t[rY_1r_1][r_1Y_2r_2] \dots [r_{k-1}Y_kr_k]
	 $$
	Esto significa que una forma de extraer X de la pila, pasando del estado q a $r_k$ es leyendo el símbolo de entrada **t**, que puede ser $\lambda$, leer una entrada para extraer de la pila y pasando de un estado $r$ a uno $r_1$ y saí sucesivamente.

## Propiedades de los LIC
- Todo LIC puede describirse con un diagrama de sintaxis, con árboles sintácticos y con árboles totales del lenguaje
- Todo LIC tiene asociado un AP que lo acepta y una GIC que lo genera
- Siempre es posible obtener una GIC al realizar las operaciones **unión, concatenación, estrella de kleene, estrella positiva e inversa** con toras GIC.
- Los LIC son cerrados con respecto a estas operaciones, pero no con respecto al complemento y a la intersección.
- La Intersección de dos LIC no es necesariamente otra LIC.
$Sea \space L_1 = {a^nb^nc^k / n,k \geq 1}$    concatenacion de una LIC con un LR, y $L2 = {a^kb^nc^n / n,k \geq 1}$ LIC y GR concatenados, la unión entre ellos no es una LIC ya que es de lenguaje tipo 1, lo cual no esta ocmprendido.
- El complemento de una LIC en general no es otro LIC > Se demuestra con la ley de Morgan $~L_1 \cup ~L_2 = ~(L_1 \cap L_2)$, cosa que por arriba es posible.

## Lema del Bombeo
Establece el límite a la capacidad de estos lenguajes para representar patrones.
Existe para cada GIC un número k tal que toda $w \in L(GIC)$ donde $|w| > k$ puede ser escrita como $w = uvxyz$ de tal manera que **v** y **y** no son ambas vacías, y que $uv^ixy^iz \in L(GIC)$ para cualquier $i \geq 0$
