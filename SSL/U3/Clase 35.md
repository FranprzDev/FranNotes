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
