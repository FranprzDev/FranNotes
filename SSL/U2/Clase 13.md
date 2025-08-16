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
