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
