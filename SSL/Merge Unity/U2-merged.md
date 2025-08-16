# Clase 9

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



# Clase 11

## Expresiones Regulares
Es una forma algebraica que se define sobre un alfabeto base $\Sigma$ y un alfabeto especial $\Sigma' = {+,*,.,\Phi, \lambda,(,)}$ con $\Sigma$ y $\Sigma'$ disjuntos mediante las siguientes clausulas.

1) $\Phi, \lambda, x \in \Sigma \space son \space ER$ 
2) Si $E_1 \space y \space E_2$ son ER, entonces $E_1+E_2 \space y \space E_1.E_2$ también son ER.
3) Si E es una ER entonces $E*$ Y (E) también son ER
4) Toda ER se puede definir mediante las cláusulas 1, 2 y 3

Los simbolos actúan como operadores; en ese orden de prioridad.
Obviamente existe una relación entre ER y LR

En general las ER se asocian con los LR, las GR y los AF, y tienen distintas aplicaciones por ejemplo:
1) Para describir patrones textuales
	1) Búsquedas por Regex
	2) Datos de prueba random
	3) Criterios de Busqueda para DB
	4) grep, findstr o awk en gnu/linux
2) Para formalización de diagramas.
3) Para describir el léxico de un lenguaje de programación

## Propiedades de las ER

1) $\Phi* = \lambda$ 
2) $E.E*=E*.E$
3) $E*=\lambda+E.E*$
4) $(E_1^*.E_2^*)* = (E_1+E_2)*=(E_1^*.E_2^*)^*.E_1^*$
5) $E* = (\lambda+E+E^2+E^3+...E^N-1).(E^N)^*$

## Sistemas de Ecuaciones Características de una GR

Dada una GR por derecha, se pueden obtener un conjunto de definiciones regulares de la forma $X = R + T.X$ donde $X \in \Sigma_N$ y (R,T) son ER sobre el alfabeto Sigma de la Gramática Regular.
Para resolver debemos:
1) Agrupar todas las reglas que tengan igual parte izquierda
2) Igualar cada no-terminal X con la unión de todas las partes derechas correspondientes, usando el conectivo **"+"**
3) Sustituir la yuxtaposición de símbolos con la concatenación del mismo usando el conectivo **"."**

La yuxtaposición es la acción de colocar dos o más elementos uno al lado del otro.
Lo más fácil para entenderlo es un ejemplo:

$G = <\Sigma_N, \Sigma_T, P, S>$
$\Sigma_N={\{S,A,B,C\}}$ 
$\Sigma_T=\{a,b,c\}$
$P: S \rightarrow aA | bB | cC$
$A \rightarrow bA | aB$
$B \rightarrow cB | a$
$C \rightarrow cC | c$

Entonces vamos a hacer los pasos para obtener el sist de ecuaciones caracteristicas, como no hay reglas iguales; no agrupamos nada si no que pasamos al paso 2; remplazamos los | por +
$P: S \rightarrow aA + bB + cC$
$A \rightarrow bA + aB$
$B \rightarrow cB + a$
$C \rightarrow cC + c$

Una vez hicimos esto, entonces lo siguiente es agregar el operador concatenación; es decir, si no están juntos entonces lo hacemos que esten juntos.

$P: S \rightarrow a.A + b.B + c.C$
$A \rightarrow b.A + a.B$
$B \rightarrow c.B + a$
$C \rightarrow c.C + c$

**Es obvio, que tiene que ser una gramática regular en fnc3 para que sea posible hacerlo**

## Solución de la Ecuación genérica
Se realizan un par de pasos para deducir la solución; que cumpla con la igualdad que tomaremos como base.
$$ X = R + T.X$$
1) Sabiendo que X es un no-terminal y que R y T son expresiones regulares, entonces aplicamos a T la operación estrella de kleene (el asterisco)
$$ T* = \lambda + T.T*$$
2) Si ahora hacemos una postconcatenación es decir "multiplicamos ambos miembros"
$$T*.R=(\lambda+T.T*).R$$
3) Por la propiedad distributiva podemos escribir el segundo miembro como:
$$T*.R=(\lambda.R+T.T*.R)$$
4) Por culpa de que $\lambda$ no hace nada en la concatenación podemos reescribir como:
$$T*.R=R+T.T*.R$$
5) Ahora revisamos a lo que queríamos llegar $X=R+T.X$ y lo comparamos.
6) La diferencia es clara $T*.R$ es igual a $X$ , entonces lo remplazamos.
7) $$T*.R=x \space \rightarrow X =R+TX$$
8) Entonces quedó demostrado lo que se conoce como el Lema de Arden.

## Obtención de la ER del lenguaje generado por una GR.
1) Se plantea el sistema de ecuaciones características
2) Se resuelve el sistema mediante
	1) Método de sustitución
	2) Solución de la ecuación genérica (lema de arden)
3) La ER del lenguaje generado por la GR es la solución correspondiente al axioma de la gramática.

## Ejemplo
$P: S \rightarrow a.A + b.B + c.C$
$A \rightarrow b.A + a.B$
$B \rightarrow c.B + a$
$C \rightarrow c.C + c$

Entonces si pasamos a las ecuaciones características
$C = c*.c$ 
$B=c*.a$ 
$A=b*.a.c*.a$
$S = a.b*.a.c*.a+b.c*.a+c.c*.c$



# Clase 13

# MEF 
Una maquina de estados finitos es un caso particular de una máquina de turing, este modelo tiene como objetivo obtener una secuencia de salida de igual longitud y ne correspondencia con la secuencia de entrada; pero no depende solo de la entrada, si no del estado en el que se encuentre el modelo.
Funciona de la siguiente forma:

- **Cinta Finita de Entrada** Contiene la secuencia de símbolos que debe procesar $e_i$
- **Cabezal de Lectura** se posiciona sobre el primer símbolo de la secuencia de entrada al inicio del proceso, se mueve a la derecha después de leer un simbolo
- **Cinta de Salida** Donde se escriben los símbolos de salida $s_i$ 
- **Control** Un componente que puede cambiar de estado y determina las acciones de la máquina según su estado actual
- **Estados** un conjunto finito y no vacio de estados en los que la máquina puede encontrarse

Una vez entendido todos estos componentes, podemos decir que el funcionamiento es el siguiente:
1) La máquina se puede encontrar en cualquiera de sus estados, el cabezal se encuentra en el primer símbolo de la palabra de entrada.
2) La máquina **LEE un símbolo** de la cinta de entrada y, al hacerlo el cabezal se mueve a la derecha.
3) De acuerdo al estado actual, (el inicial) y el símbolo leído la máquina transiciona a un nuevo estado, que puede ser el mismo; esta función está definida por una función de control $f: Q x \Sigma_E \rightarrow Q$ 
4) La máquina escribe un símbolo en la cinta de salida y mueve el cabezal a la derecha. La elección del símbolo se basa en el modelo de máquina mef que estamos utilziando.
	1) **Modelo Mealy** La salida se selecciona según el **estado actual y el símbolo leido**, primero se obtiene la salida y después se cambia al nuevo estado. Su función de salida es $f: Qx\Sigma_E \rightarrow \Sigma_S$ 
	2) **Modelo Moore** La salida se elige de acuerdo con **el nuevo estado que transiciona**, en su implementación primero se obtiene el nuevo estado y dsepués se transiciona, la función de salida es $f: Q \rightarrow \Sigma_S$ 
5) **Repetición y parada** Los pasos 1,2,3 se repiten hasta haber leído completamente la palabra de entrada, momento en el cual se detiene.

## Definición formal de la MEF
$$MEF = <Q,\Sigma_E,\Sigma_S,f,g>$$
Donde:
- **Q** es el Conjunto finito y no vacío de estados
- **$\Sigma_E$**  Alfabeto de símbolos de entrada
- $\Sigma_S$ Alfabeto de símbolos de salida
- f: Función de control o de transición, $f : Q x \Sigma_E \rightarrow Q$ 
- g: Función de salida
	- Para Mealy $g: Q x \Sigma_E \rightarrow \Sigma_S$
	- Para Moore $g : Q \rightarrow \Sigma_S$ 

**Punto de vista funcional de los 2 modelos diferentes:**
- **Mealy** la salida se realiza instantáneamente, bien se lee un símbolo de la cinta de entrada y según el estado actual, se escribe un símbolo en la cinta de salida.
- **Moore** la salida sufre un retardo, ya que se debe realizar primero la transición a otro estado, según el símbolo leído y el estado actual, para recién escribir un símbolo en la cinta de salida, que depende del estado que se ha transaccionado. 

## Ejemplo MEF

$$MEF1 = <Q,\Sigma_E,\Sigma_S,f,g>$$
Donde:
- $Q = \{q_0,q_1,q_2\}$
- $\Sigma_E=\{0,1\}$
- $\Sigma_S=\{p,i,n\}$

Esta mef escribe "n" o "p" o "i", si la secuencia de entrada tiene solo 0, uan cantidad par de 1 o una cantidad impar de 1.
![[Pasted image 20250717212552.png]]

## Descripción instantánea de una MEF

La descripción se puede dar por:
- Estado actual de la MEF
- Secuencia que falta leer de la cinta de entrada
- Secuencia que se va escribiendo en la cinta de salida

Esta terna es la **CONFIGURACIÓN DE LA MEF**

## Obtención de MEF tipo Mealy a partir de una Moore

Link:
https://g.co/gemini/share/e5ecf0f4df5c



# Clase 15

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



# Clase 19

# Autómatas finitos no deterministas
Son aquellos AF cuyas relaciones de transición pueden tener varias reacciones para un mismo estímulo, se pueden distinguir 3 modelos que tienen esta características, difieren en el dominio de la relación de transición y son equivalentes.

$$
AFND = < Q, \Sigma, Q_0, F, f > con f: Q x \Sigma \rightarrow 2^Q > 
$$
Aquí $Q_0 \subseteq Q$ es un subconjunto no vacío de estados iniciales

$$ AF-\lambda = < Q, \Sigma, q_0, F, f > con f: Q x\Sigma \cup \{\lambda\} \rightarrow 2^Q$$
Donde la entrada puede ser vacia, es decir que puede transicionar sin leer.
$$ AF-Lazy = <Q, \Sigma, q_0, F, f> con f: Q x \Sigma^* \rightarrow 2^Q >$$
La entrada puede ser una palabra cualquiera sobre $\Sigma$ 

## Equivalencia entre los modelos
Todos los modelos se pueden transformar al otro modelo.
1) $AFND \space a \space AF-\lambda$ 
	1) Si tiene un solo estado inicial, se puede considerar como un caso particular de $AF-\lambda$ que no tiene transiciones con $\lambda$
	2) En caso contrario, se agrega un estado inicial nuevo y se colca transiciones $\lambda$ hacia los estados iniciales originales.
2) $AF-Lazy \space a \space AF-\lambda$ 
	1) Si no tiene transiciones con secuencias de longitud mayor que 1, se puede considerar un caso particular de $AF-\lambda$ 
	2) En caso contrario, se reemplaza cada transición de longitud N, por N transiciones de un símbolo cada una, agregando N-1 estados nuevos.

Si los AF tienen varios estados finales lo ideal es unificarlos remplazándolos por uno nuevo, mediante transiciones $\lambda$ 

## Asociación entre AF y GR
Existe una equivalencia entre los $AF = < Q, \Sigma, q_0, F, f >$ ya sean deterministas o no deterministas con un solo estado inicial, con las $GR = <\Sigma_N, \Sigma_T, P, S>$
### Algoritmo AF > GR
$$
\Sigma_N = Q, \Sigma_T=\Sigma, S=q_0
$$


De modo que:

$$
P = f(q,w)=p \Rightarrow q \rightarrow wp
$$


$$
q \in F \Rightarrow q \rightarrow \lambda
$$

Donde $w \in \Sigma_T^*$
### Algoritmo GR > AF
$$
	Q = \Sigma_N \cup {E} , \Sigma=\Sigma_T, q_0 = S, F = {E}
$$
Teniendo en cuenta que:
$$
f > N_1 \rightarrow wN_2 \Rightarrow f(N_1,w) = N_2 
$$
$$
f > N_1 \rightarrow w \Rightarrow f(N_1,w) = E
$$

## Operaciones definidas con AF 
### Unión
La unión de dos AF, da como resultado un AF-Lazy que reconoce la unión de los lenguajes que aceptan los autómatas, se crea un estado inicial nuevo y se definen transiciones lambdas desde este hacía los estados iniciales de los AF de partida.

### Concatenación
Da como resultado un AF-Lazy que reconoce el producto de los lenguajes que aceptan los autómatas. Se colocan transiciones lambdas desde todos los finales del primero al inicial del segundo; de modo tal que el inicial corresponde al primero y los finales al segundo.

### Estrella de Kleene
Da como resultado un AF-Lazy que reconoce la estrella de Kleene del lenguaje que acepta el autómata base, el mecanismo consiste en crear transiciones lambdas al estado inicial viejo y crear un nuevo estado inicial que tenga una transición lambda al estado inicial viejo.

### Estrella Positiva
Da como resultado un AF-Lazy que reconoce la estrella positiva, se colocan transiciones lambdas desde todos los finales al inicial, pero no se cambia el estado inicial.

### Inversa
Da un AF-Lazy que reconoce la inversa del lenguaje que acepta el autómata base, el mecanismo consiste en invertir todas las transiciones del AF, luego hacer que el estado inicial sea el nuevo y único estado final, y agregar un estado nuevo con transiciones lambdas a los estados finales y este será el estado inicial nuevo.
### Complemento

Para obtener el complemento de un AF, se requiere que este sea DETERMINISTA y completo, el mecanismo consiste en convertir en finales los estados no-finales y viceversa.

###  Intersección
Para obtener la intersección es necesario que los AF sean determinista y completos, el mecanismo es el siguiente
$$
AF_1 = <Q_1, \Sigma,q_1,F_1,f_1>
$$
$$
AF_2= <Q_2,\Sigma,q_2,F_2,f_2>
$$
$$
AF_3 = <Q_3,\Sigma, q_3,F_3,f_3> 
$$
Donde definiremos:
$Q_3 \subseteq Q_1 \times Q_2$
$q_3=[q_1,q_2]$
$F_3 \subseteq F_1 \times F_2$
$f_3([q_1,q_2], x) = [f_1(q_1,x), f_2(q_2,x)]$



# Clase 21

## Obtención del $AF-\lambda$ a partir de una ER

### Plantillas de Thompson
![[Pasted image 20250723023928.png]]

### Método de Thompson
A partir de una ER, con alfabeto $\Sigma$ se puede construir un AF-\lambda que acepta el lenguaje asociado con dicha expresión, mediante las siguientes pautas.
1) Se construye un AF-lambda correspondiente a cada símbolo de $\Sigma$ y también para $\lambda$ si es necesario
2) Se procede a realizar las operaciones entre estos $AF-\lambda$, de acuerdo a la ER de partida
3) Se unifica los estados finales en cada paso.

## Equivalencia entre ER, GR y AF
### Derivada de una ER
Para poder llegar al AF a partir de una ER se define el concepto de derivada.
La derivada de una expresión regular "E" respecto a un símbolo x perteneciente al alfabeto $\Sigma$ se define como:
$$D_x(E) = {w / x.w \in E}
$$
Es decir el conjunto de palabras w que están representadas por "E" (la expresión regular), seleccionando aquellas que empiezan con el símbolo "x" respecto al cual se deriva y la derivada será el conjunto de esas palabras sin el prefijo "x"

### Propiedades de la Derivada
Para todo $x,y \in \Sigma$ se cumple que:
1) $D_x(\Phi) = \Phi$ 
2) $D_x(x) = \lambda$
3) $D_x(\lambda)=\Phi$
4) $D_x(y)=\Phi \space con \space y \neq x$
5) $D_x(E_1+E_2) = D_x(E_1) + D_x(E_2)$
6) $D_x(E_1 . E_2) = D_x(E_1).E_2+f(E_1).D_x(E_2)$
	1) Donde $f(E_1) = \lambda \space si \space \lambda \in E_1$
	2) Donde $f(E_1) = \Phi \space si \space \lambda \notin E_1$ 
7) $D_x(E*) = D_x(E).E*$

### Composición de Derivadas
Se puede componer derivadas de la siguiente forma, como si fuera la regla de la cadena
$$
D_{xy}(E)=D_y(D_x(E))
$$

### Obtención de la GR que genera el lenguaje de una ER
Dada una ER $E_0$ y el conjunto D de todas las ER $E_i$ distintas que se obtienen por derivación compuesta con respecto a todos los símbolos x de $\Sigma$ del alfabeto base de $E_0$, las componentes de la gramática G que genera el lenguaje $E_0$ son:
$$\Sigma_N={E_0} \cup D, \space \Sigma_T=\Sigma , \space S = E_0$$
Y las reglas de producción serán:
$Si \space D_x(E_1)=E_2, E_2 \neq \lambda, E_2 \neq \Phi \rightarrow \space Crea \space la \space regla \space E_1 \rightarrow xE_2$
$Si \space \lambda \in D_x(E_1), \space crear \space la \space regla\space E_1 \rightarrow x$
$Si \space \lambda \in E_0, \space crear \space la \space regla E_0 \rightarrow \lambda$
$Si D_x(E_1)=\Phi$ no se crea ninguna regla.

## Propiedades de los LR
- Todo lenguaje finito es un LR
- Todo LR tiene asociado un AF que lo acepta y un GR que lo genera
- Siempre es posible obtener el AF al realizar operaciones de unión, concatenación, estrella de kleene, estrella positiva, inversa, complemento e intersección con AF.

## Lema del Bombeo
El Lema del Bombeo (también conocido como _Pumping Lemma_) es una propiedad clave de los **lenguajes regulares (LR)** que se utiliza principalmente para **demostrar que un lenguaje _no_ pertenece a esta categoría**.

Aquí te lo explico rápidamente para los Lenguajes Regulares:

- **Propósito:** Se utiliza para probar que un lenguaje _no_ es regular.
    
- **Enunciado:** Si `L` es un lenguaje regular, y es aceptado por un Autómata Finito Determinista (AFD) con `n` estados, entonces toda palabra `w` que pertenezca a `L` y cuya longitud `|w|` sea mayor o igual que `n`, puede ser escrita como `w = xyz`. Esta división debe cumplir tres condiciones:
    
    1. La longitud de `y` debe ser mayor que cero (`|y| > 0`).
    2. La longitud de la concatenación `xy` debe ser menor o igual que `n` (`|xy| <= n`).
    3. Para cualquier número entero `i` mayor o igual que cero (`i >= 0`), la palabra `xy^iz` (es decir, `y` repetida `i` veces) también debe pertenecer al lenguaje `L`.
- **Justificación:** En un AFD, para aceptar una secuencia `w`, se deben realizar `|w|` transiciones. Si la longitud de la palabra `|w|` es mayor o igual que el número de estados `n` del AFD, esto implica que **necesariamente el autómata debe transicionar por algún estado más de una vez**. Esta repetición de un estado forma un **circuito o bucle** en el grafo del AFD. La subcadena `y` corresponde a la parte de la palabra que se "recorre" en ese circuito. Esto permite que `y` sea "bombeada" (repetida `i` veces o incluso eliminada si `i=0`) y la palabra resultante `xy^iz` seguirá siendo aceptada por el autómata, ya que simplemente se recorre el bucle una cantidad diferente de veces. La secuencia `x` recorre desde el estado inicial hasta el comienzo del bucle, `y` es la parte que recorre el bucle, y `z` es lo que se recorre desde el final del bucle hasta el estado final.
    
- **Uso (prueba por contradicción):** Para demostrar que un lenguaje _no_ es regular, se asume que sí lo es y se aplica el Lema del Bombeo. Si se puede encontrar una palabra en el lenguaje que, al ser "bombeada" (repetida o eliminada la subcadena `y`), produce una palabra que _no_ pertenece al lenguaje, se llega a una contradicción. Esta contradicción invalida la suposición inicial, probando que el lenguaje no es regular. Por ejemplo, el lenguaje `{a^kb^k / k=1,2,3,...}` no es regular, porque al bombear la parte `a` o `b` de una palabra como `a^nb^n`, el balance entre `a` y `b` se rompe, o las letras se desordenan, violando la regla del lenguaje.


# Clase 23

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