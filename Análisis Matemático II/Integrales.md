## Integrales Dobles 
### De donde sale
Sea f una función de 2 variables definida en la región cerrada y acotada $R \in R^2$, y R este dentro del rectángulo $S$ tal que, la formula de S es:
$$
S = \{(x,y) / a \leq x \leq b, c \leq y \leq d\}
$$
Entonces se definen los pasos:
1) Particionamos el rectángulo S mediante rectas paralelas a los planos coordenados, esto nos dará un conjunto de todos los rectángulos, que será **la partición interna P de R**.
	La norma de la partición $||P||$ será la diagonal del rectángulo particionado más grande.
	Las áreas de c/u de los n rectángulos de la partición serán representadas por $\Delta A_1, \Delta A_{2}, etc$ es decir $\Delta A_i$ 
2) En cada rectángulo elegimos un punto arbitrario $(\xi_{i}, \eta_{i})$ de modo que este dentro de los rectángulos.
3) Consideramos la suma de Riemman, es decir se forma la suma de los productos de la función evaluada en ese punto con el área de los rectángulos.
$$
f(\xi_{1}, \eta_{i})*\Delta A_{1} + \dots + f(\xi_{i}, \eta_{i})* \Delta A_{i} = \sum_{i=0}^n{f(\xi_{i}, \eta_{i})*\Delta A_{i}}
$$
4) Finalmente consideramos el limite de la suma de Riemman cuando la norma de la partición $||P|| \to 0$.
Es decir:
$$
Lim_{||p||\to_{0}}\sum_{i=0}^n{f(\xi_{i}, \eta_{i})*\Delta A_{i}} = \iint_{R} f(x,y)dA
$$

### Definición teórica
Sea f una función de dos variables definida en una región R cerrada y acotada de $R^2$. La integral doble de f sobre R se denota como $\iint_{R}f(x,y)dA$ y se define como:
$$
Lim_{||p||\to_{0}}\sum_{i=0}^n{f(\xi_{i}, \eta_{i})*\Delta A_{i}} = \iint_{R} f(x,y)dA
$$
Si este límite existe.


### Teorema de Existencia de Integrales Dobles
Si $f(x,y)$ es una función de dos variables independientes que es continua en una región cerrada y acotada R, y si la frontera de R es una curva cerrada simple y rectificable entonces $\iint_{R}f(x,y)dA$ existe.

### Clasificación de las Regiones de Integración
#### Región del Tipo T1
Sea R una región cerrada y acotada de $R^2$ cuya frontera es una curva cerrada simple y rectificable, si R es la gráfica de:
$$
R = \{(x,y) / g_{1}(x) \leq y \leq g_{2}(x), a \leq x \leq b\}
$$
Entonces es de tipo T1.
#### Región del Tipo T2
Sea R una región cerrada y acotada de $R^2$ cuya frontera es una curva simple, cerrada y rectificable, si R es la gráfica de:
$$
R = \{(x,y) / c \leq y \leq d, f_{1}(y) \leq x \leq f_{2}(x)\}
$$

Entonces es de tipo T2.
### Integrales Iteradas
Sea $f: z = f(x,y)$ una función continua en R, y supongamos que R es una región del tipo $T1$, sea $F(x,y)$ una función tal que $F_y(x,y) = f(x,y)$, la integral parcial de f con respecto a y es:
$$
\int f(x,y)dy = F(x,y) 
$$
Si extendemos el concepto de integral definida sería:

$$
\int^{g_{2}(x)}_{g_{1}(x)} f(x,y) dy = F(x,y) |^{g_{2}(x)}_{g_{1}(x)}=F(x,g_{1}(x))-F(x,g_{2}(x))
$$

Esta es la integral parcial de la función $f(x,y)$ con respecto a  y en el intervalo $[g_{1},g_{2}]$
Esto resulta en la función $F(x,g_{1,2}(x))$ que solo depende de X.
Por lo tanto, podemos decir que:
$$
\int^{g_{2}}_{g_{1}}f(x,y)dy = k(x)
$$
pero si calculamos la integral definida entre a y b para k, obtendremos la **integral iterada de la función f(x,y)**
$$
\int^{b}_{a}\int^{g_{2}}_{g_{1}}f(x,y)dydx
$$

Se puede hacer lo mismo, en el otro sentido.

### Teorema de Evaluación de Integrales dobles
Sea $f: z = f(x,y)$ una función continua cerrada y acotada de R, entonces:
1) Si R es del tipo T1 y es la gráfica de $R = \{(x,y) / a \leq x \leq b, g_{1} \leq y \leq g_{2}\}$ donde $g_{1,2}$ son continuas en el $[a,b]$ entonces:
$$
\int_{R} f(x,y)dA = \int^{b}_{a} \int^{g_{2}}_{g_{1}}f(x,y)dydx
$$
2)  Si R es del tipo T2 y es la gráfica de $R = \{(x,y) / f_{1} \leq x \leq f_{2}, c \leq y \leq d\}$ donde $f_{1,2}$ son continuas en el $[c,d]$ entonces:

$$
\int_{R} f(x,y)dA = \int^{b}_{a} \int^{g_{2}}_{g_{1}}f(x,y)dydx
$$
### Propiedades de las Dobles
1) $$ \iint_{R}kf(x,y)dA  = k \iint_{R}f(x,y)dA$$
2) $$ \iint_{R}f(x,y)+g(x,y)dA  = \iint_{R}f(x,y)dA \pm \iint_{R}g(x,y)dA$$
3) $$ \iint_{R}f(x,y)dA \leq \iint_{R}g(x,y)dA \space |  \space Si f(x,y) \leq g(x,y) \forall (x,y) \in R$$
4)  $$ \iint_{R}f(x,y)dA  = \iint_{R_{1}}f(x,y)dA + \iint_{R_{2}}f(x,y)dA \space | \space R \space es \space union \space de R_{1} \& R_{2} \space siendo \space disjuntos.$$