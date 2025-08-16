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