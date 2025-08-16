# U1-merged

# Clase 1

La palabra lenguaje tiene su origen en el término **lenguagtge**, sus significados son:
- Facultad del ser humano de expresarse y comunicarse con los demás a través del sonido articulado o de otros sistemas de signos.

## Introducción al Lenguaje
**Signo** algo que evoca o representa una cosa o concepto.
Pueden tener distintos tipos.
- **Sin intención comunicativa:** No existe la pareja emisor-receptor
	- **ÍNDICE** son signos que dan indicios de alguna entidad o hecho.
- **Con intención comunicativa:** Hay un emisor-receptor del mensaje
	- **ÍCONO** son signos que por sus aspectos se asemejan a lo que representan
	- **SÍMBOLO** Son signos meramente convencionales que no guardan ningún parecido con lo que representan.

### Tipos de Lenguaje
**Formal:** 
- Se formaliza antes de usar
- No es ambiguo
- De dominio específico
- Para humanos y/o máquinas
- Ej: Programación, Música, etc.
**Natural**
- Se usa antes de formalizar
- Es ambiguo
- De dominio general
- Para humanos
- Ej: Oral, Escrito, Lenguaje de Señas.

### Niveles de un Lenguaje
Existen 4 dimensiones del lenguaje, para que así podamos analizar de manera correcta un texto escrito en un lenguaje determinado.
- **Nivel Léxico**
	Es la dimensión del lenguaje que trata sobre la relación entre los símbolos que representan las distintas palabras que se utiliza para formar una frase válida. Es lo que llamamos diccionario. Cada palabra se forma por un componente léxico.
- **Nivel Sintáctico**
	Es la dimensión del lenguaje que estudia la forma en la que se organizan los componentes léxicos para formar una frase válida, es decir la estructura de la secuencia de componentes que conforman dicha frase. 
	Este nivel es independiente del contexto, tanto en los lenguajes naturales como en los formales.
- **Nivel Semántico**
	Es la dimensión del lenguaje que analiza el significado o connotación de los componentes léxicos y de las frases válidas que se pueden formar con ellos. En el caso de lenguajes formales, la semántica es simple; ya que no hay duda que "eso" significa exactamente lo que dice, no pasa lo mismo con los lenguajes no formales.
- **Nivel Pragmático**
	Es la dimensión que trata sobre hechos o acciones que evocan las frases, tiene en cuenta el contexto donde se aplica el lenguaje; por lo tanto es dependiente del mismo. Es complicado, por que una misma frase podría significar hechos totalmente distintos.


# Clase 2

## Alfabeto
Es un conjunto finito no vacío de símbolos diferentes, lo denotamos con la letra $\Sigma$, por ejemplo el alfabeto binario es $\Sigma = \{1,2\}$ 
Un conjunto de símbolos es lo que llamamos **datos**
La información son un conjunto de **datos significativos**
Un símbolo se compone de un significante que es la imagen gráfica con la que representamos y de un significado, que es el concepto asociado.
**Palabra:** secuencia finita de símbolos pertenecientes aun alfabeto.
La palabra vacía se representa con lambda $\lambda$, y es aquella secuencia que no tiene símbolos.
$\Sigma*$ representa el conjunto de todas las palabras formadas por los símbolos de dicho alfabeto. (Es el conjunto universal)
$\Sigma+$ representa al Conjunto Universal sin la palabra vacía

## Lenguajes Formales
El lenguaje es cualquier subconjunto L del Conjunto Universal de palabras sobre un alfabeto $\Sigma$
Podemos decir que $L \subseteq \Sigma*$ 
El lenguaje universal entonces será $\Sigma*$
El lenguaje vacío será $\Phi$
El lenguaje $L\lambda = \{\lambda\}$ 

## Operaciones con palabras
### Concatenación
Es una función con dominio $\Sigma* \ x \ \Sigma*$ y rango $\Sigma *$, Tal que dadas las palabras u y v la concatenación de u con v da como resultado la palabra w formada por la secuencia de símbolos de u seguida por la secuencia d esímbolos de v.
### Potenciación
Dada la palabra u y el número natural j, la potencias con base u y exponente j da como resultado la palabra w formada por una sucesión de j veces la palabra u

### Longitud
Tal que dada la palabra u la longitud de u da como resultado la cantidad de símbolos que forman la palabra.

### Inversa
Tal que dada la palabra u la inversa de u da como resultado la imagen especular de u, es decir la imagen reflejada de un objeto, que parece casi idéntica pero está invertida al revés.

## Operaciones con Lenguajes

### Unión
Dados dos lenguajes L1 y L2, la unión enter L1 y L2 será el lenguaje L3 formado por todas las palabras de L1 y todas las palabras de L2 sin repeticiones.

### Diferencia
Tal que dado los lenguajes L1 y L2, la diferencia entre L1 y L2 da como resultado L3 formado por todas las palabras de L1 excepto aquellas que pertenezcan también a L2

### Intersección
Dado los lenguajes L1 y L2, la intersección de L1 y L2 da como resultado otro lenguaje L3 formado por todas las palabras que pertenecen a L1 y que también pertenecen a L2.

### Complemento
Dado el lenguaje L1, el complemento de este lenguaje es L3 formado por toads las palabras que pertenecen al universo ($\Sigma*$) y que no pertenecen a L1.

### Producto o Concatenación
Dado L1 y L2 se obtiene L3 formado por todas las palabras que resultan de concatenar una palabra de L1 con una palabra de L2 y solo en ese oredn.

### Potenciación
Dado L1 y el número natural i mayor igual que 2, da como resultado el lenguaje L3 formado por el producto de L1 consigo mismo (i-1) veces

### Clausura o estrella de Kleene
Tal que dado L1, la operación "L1 estrella" da como resultado L3, formado por todas las potencias de base L1 y exponente i, desde i igual a cero hasta infinito.
Es decir
$L_1* = L_1^0 \cup L_1^1 \cup L_1^2 \cup ... \cup L_1^n$ 
Tiene propiedades interesantes como por ejemplo:
- $(L_1^*)*=L1^*$
- $\Phi^* = L\lambda$ y $L\lambda^* = L\lambda$ 

### Estrella Positiva
Dado L1, "L1 estrella positiva" da L3 formado por todas las potencias de base L1 y de exponente i, desde i igual a uno hasta infinito.
Esto quiere decir que no incluye la vacía.
$L_1* = L_1^1 \cup L_1^2 \cup ... \cup L_1^n$ 
Mismas props.

### Inversa
Tal que dado L1, la inversa de L1 da como resultado otro lenguaje L3 formado por todas las inversas correspondientes a las palabras de L1.



# Clase 3

## Gramáticas estructuradas por frases

Se pueden definir por:
- **Definición por Extensión** Listado de las palabras del lenguaje
- **Definición por comprensión** Especificación de atributos de las palabras
- **Definición por patrones** Expresiones de palabras con parámetros
La gramática es el conjunto de reglas de formación junto con los símbolos utilizados.

## Definición formal de una gramática estructurada por frases

$$ G = < \Sigma_N \\, \Sigma_T \\, P \\, S>$$
- $\Sigma_N$ es el alfabeto de símbolos No-terminales o variables de la gramática
- $\Sigma_T$ es el alfabeto de símbolos terminales o símbolos del lenguaje
- P es el conjunto finito no vacío de Reglas de Producción de la forma:
				$\alpha \rightarrow \beta$   
	donde:
	$\alpha = \alpha_1N\alpha_2 \space con \space \alpha_1 \\, \alpha_2 \in \Sigma* \space N \in \Sigma_N \space \beta \in \Sigma*$    
- S es el símbolo inicial o axioma de la gramática.

Es importante que $\Sigma_N \space y \space \Sigma_T$ sean conjuntos disjuntos.

### Derivación de palabras a partir del axioma (S)
Podemos generar una palabra del lenguaje que describe una gramática comenzando por una regla que tenga el axioma a la izquierda y luego se continúa con el resto de las reglas que sean necesarias para llegar a la palabra.
Podemos decir que:
$S \rightarrow \alpha_1 \rightarrow \alpha_2 \rightarrow \space ... \space \alpha_n \rightarrow w$
Que equivale a decir $S \rightarrow *w$ 
Donde el operador de la flechita es la derivación, y la flechita estrellita es derivación a la larga.

### Forma Sentencial
Cualquier secuencia $\gamma~$ que se obtenga a partir del axioma en un proceso de derivación se denomina forma sentencial.
Una forma sentencial está compuesta por símbolos terminales, se denomina sentencia y constituye el final del proceso de derivación.
De aquí se desprende la idea de que:
- **Derivación más a la izquierda** Cuando se empieza a reemplazar la subsecuencia por la izquierda estamos ante este tipo de derivación.
- **Derivación más a la derecha** Cuando se empieza a reemplazar la subsecuencia por la derecha estamos ante este tipo de derivación

### Lenguaje generado por una gramática
El lenguaje generado por una gramática para estructuras de frases G detonado como L(G), es el conjunto definido como:
$$L(G) = {w / w \in (\Sigma_T^*) \space \\y \space S \rightarrow * w}$$
### Equivalencia entre gramáticas
Dos gramáticas G y G' se dicen equivalentes si y sólo si los lenguajes generados por ambas son iguales es decir.
$$ L(G) = L(G') \Leftrightarrow G \equiv G'$$  
### Jerarquía de Chomsky
Es una clasificación realizada por Chomsky, que implica una jerarquía de los lenguaje generados por las gramáticas de cada tipo, ya que una gramática del tipo X surge de aplicar ciertas restricciones al tipo anterior (X-1)
De este modo, queda organizado así
$$L_0 \supset L_1 \supset L_2 \supset l_3 \supset L_4$$


<table border="1" cellpadding="5" cellspacing="0">
  <thead>
    <tr>
      <th>Tipo</th>
      <th>Gramática</th>
      <th>Lenguaje</th>
      <th>Nivel Lingüístico</th>
      <th>Modelo Matemático</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Irrestricta (GI)</td>
      <td>Recursivamente enumerable (LI)</td>
      <td>Pragmático</td>
      <td>Máquina de Turing (MT)</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Dependiente del Contexto (GDC)</td>
      <td>Lenguaje Dependiente del Contexto (LDC)</td>
      <td>Semántico</td>
      <td>Autómata Linealmente Limitado (ALL)</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Independiente del Contexto (GIC)</td>
      <td>Lenguaje Independiente del Contexto (LIC)</td>
      <td>Sintáctico</td>
      <td>Autómata de Pila (AP)</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Regular (GR)</td>
      <td>Lenguaje Regular (LR)</td>
      <td>Léxico</td>
      <td>Autómata Finito (AF)</td>
    </tr>
  </tbody>
</table>

#### Tipo 0 (Irrestricta o Sin Restricciones -GI)
Está estructurada por frases sin ninguna restricción, es decir que sus reglas de producción tienen en la parte izquierda al menos un símbolo no terminal y en la parte derecha cualquier secuencia de terminales o no-terminales, inclusive vacía.
Todo lenguaje generado por una GI y que no puede ser generado por una gramática de menor jerarquía, se llama "**Lenguaje Irrestricto o Recursivamente Enumerable (LI)**"

#### Tipo 1 (Dependiente del / Sensible del Contexto GDC)
Es la gramática estructurada por frases cuyas reglas de producción se restringen en la longitud de su parte derecha, la cual no puede ser menor que la longitud de la parte izquierda, es decir que no tienen reglas compresoras; exceptuando la regla de borrado $S \rightarrow \lambda$, siempre y cuando S no figure a la derecha de ninguna regla y el objetivo de esto, es generar la palabra vacía.

#### Tipo 2 (Independiente / Libre del Contexto - GIC)
Gramática estructurada por frases cuyas reglas de producción se restringen en la longitud de su parte izquierda, que debe ser igual a 1. Es decir la parte izquierda es un no-terminal y la parte derecha puede ser cualquier secuencia de terminales o no-terminales.
Cualquier lenguaje formal que no puede ser generado por una gramática de menor jerarquía, se llama **Lenguaje Independiente del Contexto (LIC)** 

#### Tipo 3 (Lineal / Regular - GR)
Es una gramática estructurada por las reglas de producción que su parte izquierda debe ser igual a 1, y la parte derecha puede ser una secuencia de terminales con un no-terminal como sufijo (GR por derecha) o con un no-terminal como prefijo (GR por izquierda) o simplemente una secuencia de terminales.
Existe una equivalencia entre ambas formas.
Todo lenguaje formal generado por una GR por derecha se llama **Lenguaje Regular (LR)**


# Clase 5

## Proceso de Compilación

### Traductor
Se define como un programa que traduce o convierte desde un texto o programa escrito en un lenguaje fuente hasta un texto o programa equivalente en un lenguaje destino, produciendo si existe un error.
Existen distintos tipos de traductores
- **Preprocesadores**
	Permite modificar el programa fuente antes de la verdadera compilación.
- **Compiladores**
	Es aquel traductor que tiene como entrada sentencias de un lenguaje formal y como salidas un fichero en un lenguaje de bajo nivel, es decir de lenguaje de alto nivel a código máquina.
- **Interpretes**
	Es un traductor que toma como entrada sentencias escritas en un lenguaje formal y como salida las ejecuta sin almacenarlas, es decir traduce sentencia por sentencia y las ejecuta sin crear un archivo donde se guarde.
- **Pseudo interepretes**
	El código fuente pasa por un pseudocompilador que genera un pseudoejecutable, para esto utilizan un motor de ejecución como lo es Java.
- **Interpretes de comandos**
	Traduce sentencias simples o invocaciones a programas de una biblioteca, utilizado por ejemplo en la shell de linux con el comando **cd**
- **Ensambladores**
	Es un compilador sencillo, en el que el lenguaje fuente tiene una estructura simple que permite la traducción de cada sentencia fuente a una única instrucción  en código máquina. Ej: mandarlo en assembler, **MOV**
- **Transpiladores**
	Permiten traducir de un lenguaje de alto nivel a otro lenguaje de alto nivel, así consiguiendo portabilidad entre lenguajes. Por ejemplo **TypeScript**
- **Traductores de idioma**
	Son traductores de lenguajes naturales, es decir tienen como entrada un texto escrito en un idioma y como salida un texto escrito en otro idioma.

### Fases de ejecución 
#### Compilación
Un compilador no suele producir un fichero ejecutable, sino que el código se estructura en modulos que se almacena en un fichero de tipo objeto (.obj), estos poseen infromación relativa tanto al código máquina como a una tabla de símbolos que almacena la estructura de las variables y tipos utilizados por el programa
![[Pasted image 20250622222545.png]]
#### Enlace
Es un único bloque que **unifica todos los módulos** generados por el compilador y las integra en un único bloque coherente código máquina, además **organiza el espacio en memoria** que se utilizará para la ejecución, y es el encargado de generar el **ejecutable final** 
![[Pasted image 20250622223006.png]]
#### Carga
El cargador que es parte del S.O coloca diferentes segmentos del fichero ejecutable en las direcciones de memoria disponibles, de tal modo que las direcciones relativas del código se le suma la dirección base del segmento correspondiente, y así obteniendo los valores que tomará el procesador para acceder una variable o realizar una acción.
![[Pasted image 20250622223111.png]]


# U2-merged

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


# U3-merged

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



# U4-merged

# Clase 39

# Máquina de Turing (MT)
La MT fue concebida por Turing en el 36, como un modelo matemático abstracto que representa la solución de cualquiera problema algorítmico y en particular el reconocimiento de lenguajes de Tipo 0 o Irrestrictos.

El modelo dispone de una **cinta infinita** dividida en casilleros que pueden contener un símbolo cada uno. Un **cabezal de lectura y escritura** sobre la cinta. Un **control** que puede responder de distintas formas según el **estado** en el que se encuentre.

Al comienzo la cinta está llena de espacios en blancos $\Delta$ y se escribe la palabra que se desea analizar $e_i$, el cabezal estará en la posición del primer símbolo de la palabra, en este caso se dice que el control se encuentra en el **ESTADO INICIAL**

A partir del estado inicial el modelo comienza a funcionar realizando las siguientes acciones

1) **Lee** un símbolo
2) De acuerdo al **estado actual** y al símbolo leído
	1) **ESCRIBE** otro símbolo (que puede ser el mismo)
	2) **MUEVE** el cabezal un lugar hacia la derecha o izquierda, eventualmente puede no moverse.
	3) **TRANSICIONA** a un **NUEVO ESTADO** (que puede ser el mismo)
3) Repite 1 y 2 hasta que llega a alguno de los llamados **ESTADOS FINALES** en este caso, se dice que la palabra escrita inicialmente es **ACEPTADA**, o hasta que se llega a un estado en el que no está definida una transición para el símbolo leído, en este caso se produce un **BLOQUEO** y la secuencia de entrada es **RECHAZADA** 

## Definición formal de la MT

$$
MT = <Q, \Sigma_E, \Sigma_A, q_0, F, f>
$$
Donde:
- $Q$ Conjunto finito y no vacío de estados
- $\Sigma_E$ Alfabeto de símbolos de entrada
- $\Sigma_A$ Alfabeto de símbolos auxiliares (incluye a "$\Delta$")
- $q_0$ Estado inicial perteneciente a Q
- $F$ Conjunto de estados finales, incluido en Q
- $f$ Función de transición
Donde $f$ se define como:

$$
f: (Q-F) \times (\Sigma_E \cup \Sigma_A) \Rightarrow Q \times (\Sigma_E \cup \Sigma_A) \times {I,N,D}
$$
Donde los simbolos I, N y D representan los movimientos del cabezal de lectura escritura sobre la cinta, hacia la izquierda, nulo y hacia la derecha respectivamente.
El domino no incluye a $F$, es decir que los estados finales son de parada; todos los símbolos se pueden leer y escribir, pero inicialmente solo hay espacios en blanco y una secuencia de símbolos de entrada.

Según Turing $\Sigma_E^*$ queda divido en tres subconjuntos
- Todas las palabras aceptadas por la MT
- Todas las palabras rechazadas por la MT
- Aquellas palabras que hacen que la MT no se detenga, es decir que ni se acepta ni se rechaza.

Esto implica que todo LI tiene asociado una MT que es capaz de reconocerlo, pero qeu su completo **NO SIEMPRE**

La representación formal se hace por medio del par **(estado actual, símbolo de entrada)** y la terna **(estado nuevo, símbolo de salida, movimiento)** 

En el caso de la MT se puede afirmar que se trata de un modelo DETERMINISTA por naturaleza, es decir que para toda MT ND existe una MT determinista equivalente.

## Configuración de una MT
Es una descripción instantánea de una MT requiere las siguientes especificaciones
- Estado actual del a MT
- Contenido de la cinta
- Posición del Cabezal
Esta terna es la **configuración** de la MT y vamos a representar con la secuencia de símbolos que hay en la cinta antes de la posición del cabezal 
$$
\Delta c_1 \dots c_{i-1} q_kc_i \dots c_n \Delta 
$$

Se define el operador $⊢$ como el operador de transformación directa de una configuración a otra, que implica el paso de un paso de $C_1$ a $C_2$, mediante la aplicación de la función de transición $f$ una sola vez; y en el caso de que se realicen varios se define como:
$$C_1 ⊢^* C_2
$$
Una secuencia de varias configuraciones consecutivas se llama **SECUENCIA DE CONFIGURACIÓN DE LA MT**

## Lenguaje aceptado por una MT
Se define el lenguaje aceptado como el conjunto de palabras que partiendo de una configuración inicial llegan a una configuración que contiene un estado final de la MT.

$$
L(MT) = \{w / w \in \Sigma_E^* \space y \space \Delta q_0w \Delta ⊢^* \Delta \beta_1 q_F \beta_2 \Delta \space y \space q_F \in F \}
$$
Todas aquellas donde se bloquea, entonces esas palabras son rechazadas.

## Autómata Linealmente Limitado (ALL)
Es una MT que tiene restringida la longitud de su cinta, limitandose a la longitud de la secuencia de entrada inicial. Este modelo matemático abstracto representa la solución del problema de aceptación de lenguajes de Tipo 1 o LDC.

El modelo es igual a la MT pero dispone de una **cinta finita**, al comienzo se escribe la palabra $e_i$ el cabezal de lectura-escritura se encuentra en la primera posición, donde está el símbolo inicial de la palabra; se dice que el **control** está en el **estado inicial**. Automáticamente se coloca en los extremos los parentesis angulares $< \space y \space >$ a la izq y derecha respectivamente, actuando como límites para el desplazamiento del cabezal, de tal modo que no se pueden desplazar más a la izquierda o derecha que ellos, es el tope.

### Definición formal
$$
ALL = < Q, \Sigma_E, \Sigma_A, q_0, F, f >
$$
Donde:
- $Q$ Conjunto finito y no vacío de estados
- $\Sigma_E$ Alfabeto de símbolos de entrada
- $\Sigma_A$ Alfabeto de símbolos auxiliares, incluyendo a $< \space y \space >$ 
- $q_0$ Estado inicial, perteneciente a $Q$
- $F$ Conjunto de estados finales, incluido en $Q$
- $f$ Función de control
La función se define como:
$$
f : (Q-F) \times (\Sigma_E \cup \Sigma_A) \Rightarrow Q \times (\Sigma_E \cup \Sigma_A) \times \{I,N,D\}
$$
Donde:
$$
\forall q \in (Q-F) \space y \space q' \in Q:
$$
- $f(q,<) = (q', <, D)$
- $f(q, >) = (q',>,I)$
El dominio no incluye a F, es decir que los estados finales son de parada; todos los simbolos se pueden leer y escribir; pero inicialmente solo se encuentra la secuencia de entrada delimitada por los parentesis angulares.

En este caso, el lenguaje de entrada $\Sigma_E^*$, quedará dividido en:
- Todas las palabras aceptadas por el ALL
- Todas las palabras rechazadas por el ALL

Es decir, para todo LDC existe un ALL que es capaz de aceptarlo y a la vez rechazar su complemento, esto quiere decir que el problema de reconocimiento de LDC siempre tiene solución.

La representación es la siguiente:
- **El par** $(estado \space actual, \space símbolo \space de \space entrada)$
- **La terna** $(estado \space nuevo, \space símbolo \space de \space salida, \space movimiento)$

La relación de transición puede ser **determinista o no-determinista**, pero naturalmente el **ALL** es **determinista por naturaleza**
Aún no se demuestra que para todo ALL ND existe un ALL Determinista equivalente, pero es la creencia más común.

Tienen los mismos conceptos de **configuración, secuencia de configuración y lenguaje aceptado** de una MT.

## MT Transformadora de secuencias

Se puede ver a la MT como un **modelo general de procesamiento de datos** capaz de realizar cualquier transformación sobre una secuencia inicial y obtener una secuencia final que cumpla ciertas condiciones.

La secuencia inicial son los **datos de entrada** y la secuencia final los **datos de salida o resultado de un problema algorítimico**

En estos casos la **aceptación de la secuencia inicial** se puede interpretar como la **validación de los datos de entrada**, ya que si no son validos se rechazan.


# Clase 41

# Construcción de una MT
## Composición de MT

Sea $MT_1 \space y \space MT_2$ dos MT sobre el mismo alfabeto de entrada $\Sigma_E$ y el mismo alfabeto auxiliar $\Sigma_A$  donde:
$$
 MT_1 = <Q_2, \Sigma_E, \Sigma_A, q_{01}, F_1, f_1>
$$
$$
	MT_2 = <Q_2, \Sigma_E, \Sigma_A, q_{02}, F_1, f_1>
$$
Con $Q_1 \space y \space Q_2$ disjuntos, la composición de estas dos máquinas generará una $MT_3$ tal que:

$$
MT3 = < Q_1 \cup Q_2, \Sigma_E, \Sigma_A, q_{01}, F_2, f_3 >
$$
Donde $f_3(q,e)$ sucederá:
- $f_1(q,e) \space si \space q \in Q_1 \space y \space f_1(q,e) \neq (p, s, m) \space \forall p \in F_1$
- $f_2(q,e) \space si \space q \in Q_2$
- $(q_02, s, m) \space si \space q \in Q_1 \space y \space f_1(q,e)=(p,s,m) \space y  \space p \in F_1$

Osea:
- Si está dentro del espacio de la MT1, con excepción del estado final
- Si está la MT2
- Si es el estado final.

Entonces, aquí es donde podemos usar como plantillas de máquinas de turing simples y las vamos combinando según necesitamos, al estilo de thompson.
![[Pasted image 20250727051229.png]]
![[Pasted image 20250727051234.png]]
Ejemplo:
![[Pasted image 20250727051244.png]]

## Variantes de la MT
Con el objetivo de resolver problemas más complejos se pueden plantear variaciones de la MT. Las mas comunes se encuentran la **MT Multicinta y la MT Multiplista**.

La MT multicinta consta de N cintas infinitas con N cabezales independientes de tal modo que inicalmente se escriben secuencias de entrada en las N cintas y los cabezales comienzan en una posición determinada de las cintas, normalmente en el extremo izquierdo.
El control de cada uno de los cabezales requiere una func de transición independiente, similares a una MT de una sola cinta. 
Esto quiere decir que:
$$
MT_{multicinta} = <Q, \Sigma_E, \Sigma_A, q_0, F, f>$$
Donde $f$ resulta en varias funciones de transiciones dependiendo de a que cinta se apunte.

La MT multipista, la única diferencia es que los cabezales están restringidos a realizar todos juntos el mismo movimiento.

## Aceptores del lenguaje

### Comprobación de pertenencia
La comprobación de pertenencia responde al problema de verificar si una palabra **w** está incluida en un lenguaje que genera una gramática **G**.
Se puede afirmar que este problema tiene solución para los lenguajes de Tipo 1, 2 y 3.
Sin embargo, para los lenguajes de tipo 0 o LI no existe un algoritmo general que permita comprobar la pertenencia de una palabra **w** a un lenguaje generado por una gramática irrestricta.

La dificultad está en las gramáticas irrestrictas en la permisividad de las reglas compresoras; específicamente cuando se desea obtener todas las palabras de longitud menor o igual a **N**. En este caso las secuencias pueden ir disminuyendo de longitud, entonces no se sabe con seguridad cuando terminar el proceso; y de esta forma entrar en un posible lazo infinito.

Esto es justamente lo que se llama **"PROBLEMA DE LA PARADA DE LA MT"** **(The Halting Problem)** que constituye el primer problema sin solución algorítmica demostrable

## Problema de la parada de la MT
### 1. **¿Qué es el problema de la parada?**
El **problema de la parada** (*halting problem*) pregunta si existe un algoritmo que pueda determinar, para cualquier **Máquina de Turing (MT)** \( M \) y entrada \( w \), si \( M \) se detiene (termina su ejecución) o sigue indefinidamente. Su lenguaje asociado es:
$$
L_{\text{parada}} = \{ \langle M, w \rangle \mid M \text{ es una MT y } M \text{ se detiene en } w \}
$$


Es un lenguaje **recursivamente enumerable** (Tipo 0 en la jerarquía de Chomsky), pero **indecidible**.

### 2. **¿Qué quiso demostrar Turing?**
Alan Turing quiso demostrar que **no todos los problemas computacionales son decidibles**, específicamente que no existe una Máquina de Turing que pueda resolver el problema de la parada para cualquier entrada. Esto establece un límite fundamental en la computación, mostrando que hay preguntas sobre programas que no pueden responderse algorítmicamente.

### 3. **¿De qué trataba el problema de Entscheidungsproblem?**
El **Entscheidungsproblem** ("problema de decisión") fue propuesto por David Hilbert y Wilhelm Ackermann en 1928. Se preguntaba si existe un algoritmo general que pueda determinar si una afirmación en lógica de primer orden es universalmente válida (verdadera en todos los modelos). Turing usó el problema de la parada para demostrar que el Entscheidungsproblem es indecidible, ya que resolverlo implicaría resolver problemas indecidibles como el de la parada.

A continuación, reescribo la sección de la **demostración de la indecidibilidad** del problema de la parada, incorporando expresiones matemáticas en formato LaTeX donde corresponda, siguiendo tu instrucción. Cada expresión matemática estará encerrada en símbolos de dólar (\$) para indicar que es una expresión matemática, como es estándar en LaTeX.

### 4. **Demostración de la indecidibilidad (paso a paso)**
Turing demostró que el problema de la parada es indecidible mediante una **prueba por contradicción**:

1. **Suposición**: Supongamos que existe una Máquina de Turing $H$ que decide el problema de la parada. Para cualquier entrada $\langle M, w \rangle$, donde $\langle M, w \rangle$ es la codificación de una Máquina de Turing $M$ y una entrada $w$:
   - $H$ acepta si $M$ se detiene en $w$, es decir, $H(\langle M, w \rangle) = \text{acepta}$.
   - $H$ rechaza si $M$ no se detiene en $w$, es decir, $H(\langle M, w \rangle) = \text{rechaza}$.

2. **Construcción de $D$**: Se crea una nueva Máquina de Turing $D$ que toma como entrada la codificación de una Máquina de Turing $\langle M \rangle$ y opera como sigue:
   - Ejecuta $H(\langle M, \langle M \rangle \rangle)$, es decir, evalúa si $M$ se detiene cuando se le da su propia codificación $\langle M \rangle$ como entrada.
   - Si $H(\langle M, \langle M \rangle \rangle) = \text{acepta}$ (i.e., $M$ se detiene en $\langle M \rangle$), entonces $D$ entra en un bucle infinito.
   - Si $H(\langle M, \langle M \rangle \rangle) = \text{rechaza}$ (i.e., $M$ no se detiene en $\langle M \rangle$), entonces $D$ se detiene.

3. **Paradoja**: Ejecutamos $D$ con su propia codificación $\langle D \rangle$:
   - Si $D$ se detiene en $\langle D \rangle$, entonces $H(\langle D, \langle D \rangle \rangle) = \text{acepta}$, lo que implica que $D$ debería entrar en un bucle infinito (contradicción).
   - Si $D$ no se detiene en $\langle D \rangle$, entonces $H(\langle D, \langle D \rangle \rangle) = \text{rechaza}$, lo que implica que $D$ debería detenerse (contradicción).

4. **Resultado**: La suposición de que existe una Máquina de Turing $H$ que decide el problema de la parada lleva a una contradicción. Por lo tanto, no puede existir tal $H$, y el problema de la parada es indecidible.


### 5. **Ejemplo en código Python**
No podemos implementar un solucionador general del problema de la parada (porque es indecidible), pero podemos ilustrar la idea de la paradoja con un código Python que simula el razonamiento de Turing. Este código muestra cómo la existencia de un supuesto "decisor" lleva a una contradicción:

```python
def halts(program, input):
    # Suponemos que existe una función que decide si 'program' se detiene en 'input'
    # En la realidad, esta función no puede existir
    # Aquí simulamos una lógica simple (esto es solo ilustrativo)
    pass  # No implementable en general

def diagonal(program):
    # Implementa la máquina D: toma la codificación de un programa
    if halts(program, program):  # Si el programa se detiene en sí mismo
        while True:  # Entra en un bucle infinito
            pass
    else:  # Si no se detiene
        return  # Se detiene

# Simulamos la paradoja ejecutando diagonal con sí mismo
def main():
    # No podemos ejecutar diagonal(diagonal) directamente en Python,
    # pero el código ilustra que si 'halts' existiera, llevaría a una contradicción
    print("Si halts(diagonal, diagonal) dice que se detiene, diagonal entra en bucle.")
    print("Si halts(diagonal, diagonal) dice que no se detiene, diagonal termina.")
    print("Esto es una contradicción, por lo que halts no puede existir.")

if __name__ == "__main__":
    main()
```

**Explicación del código**:
- La función `halts(program, input)` representa la hipotética Máquina de Turing \( H \) que decide si un programa se detiene. En la realidad, no puede implementarse.
- La función `diagonal(program)` simula la máquina \( D \), que usa `halts` para crear una contradicción.
- Al intentar ejecutar `diagonal` con su propia codificación, se produce una paradoja lógica, mostrando que `halts` no puede existir.
- En Python, no podemos codificar programas como entradas de manera directa como en una MT, pero el código ilustra la idea de la contradicción.

### 6. **Relación con el Entscheidungsproblem**
Turing relacionó el problema de la parada con el **Entscheidungsproblem** al mostrar que si pudiéramos resolver el problema de la parada, también podríamos resolver el Entscheidungsproblem (codificando afirmaciones lógicas como MTs). Dado que el problema de la parada es indecidible, el Entscheidungsproblem también lo es.

### 7. **Implicaciones prácticas**
- **Verificación de software**: No podemos crear una herramienta que garantice si cualquier programa termina.
- **Límites de la computación**: Hay problemas intrínsecamente irresolubles, incluso para sistemas avanzados como los LLMs.
- **Teoría de lenguajes**: El lenguaje del problema de la parada es de Tipo 0, pero su indecidibilidad lo distingue de lenguajes más simples.

## Aceptor de Lenguajes < 0
Se puede demostrar que siempre es posible resolver el problema de comprobación de pertenencia para GDC, GIC y GR, definiendo el siguiente algoritmo.

Dada una $G = <\Sigma_N, \Sigma_T, P, S> y una palabra $w$ con longitud $N$, ENTONCES:
1) $T_0 = {S}$
2) $T_k = T_{k-1} \cup \{\beta / |\beta| \leq N \space y \space \exists \alpha \in T_{k-1} \space y \space \alpha \Rightarrow \beta \}$
3) Repetir 2 hasta que:
	1) $T_k == {T_{k-1}}$
	2) $w \in T_k$

## Aplicación Resolubilidad y Complejidad
### Función Computable
Una función $f$ se dice Turing Computable, si para la misma existe una MT que es capaz de obtener el valor de $f(w)$ para todo $w \in domf$  
### Problemas de decisión
Son aquellos problemas cuyo resultado se puede representar con una función de rango binario con valores (falso / verdadero, si / no, 0 / 1)

## Resolubilidad o Decidibilidad
Cuando un problema de decisión es computable por una MT se dice que es decidible, de lo contrario se dice que es indecidible.
### Lenguajes Recursivamente Enumerables
Los lenguajes generados por GR de tipo 0, son los que son reconocidos como lenguajes recursivamente enumerables, debido a que sus palabras se pueden generar mediante la aplicación de reglas gramaticales recursivas sobre la cinta de una MT, esto a su vez permite que una MT sea capaz de reconocer las palabras, por lo que se dice que son **"aceptables"**.
Pero, existen secuencias del universo del lenguaje aceptado que pueden producir un bucle infinito, **esto significa que los complementos de algunos LRE no son aceptables por una MT, y por lo tanto no son LRE.**

## Lenguajes Recursivos
Los LRE cuyos complementos también son LRE son conocidos como **LENGUAJES RECURSIVOS**. Estos lenguajes son decidibles por una MT, ya que todas las palabras del universo provocan la detención o parada de la MT.
Osea, que el problema de decisión que plantea la pertenencia, siempre tiene solución algoritmica y por lo tanto es resoluble o decidible.
Por lo tanto, el conjunto de LDC (Tipo 1) es un subconjutno de los **Lenguajes Recursivos**

## Propiedades de los lenguajes aceptables y decidibles por MT

Los LRE son cerrados para las operaciones intersección, unión, concatenación y estrella de Kleene, no así para el complemento.

En el caso de los recursivos se puede demostrar que son cerrados para todas.

### Complejidad algorítmica
La complejidad de un algoritmo se puede medir en lo **temporal** y en lo **espacial**.
Desde un punto de vista teórico, la temporal se mide en la cantidad de pasos que lleva una MT asociada al algoritmo en detenerse.
Osea se cuentan los pasos que realiza la MT en función de la entrada n, identificando la función de crecimiento.

La complejidad espacial se mide en función de la cantidad de casilleros que utilizaria la MT para resolver un problema.