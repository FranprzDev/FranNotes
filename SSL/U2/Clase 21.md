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