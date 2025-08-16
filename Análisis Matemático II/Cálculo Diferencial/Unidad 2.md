# LÍMITES
## Distancia entre dos puntos de $R^n$ 


Sean $X_0$ y $X_1$ dos puntos $\in R^n$ donde resulta que $X_0 = (x_1^0, x_2^0, \dots , x_n^0)$ y $X_1 = (x_1^1, x_2^1, \dots , x_n^1)$ la distancia entre estos dos puntos estará determianda por:
$$
 \mid(X_{1}-X_{0})\mid = \sqrt{(x_{1}^1-x_{1}^0)^2 + (x_{2}^1-x_{2}^0)^2 + \dots +  (x_{n}^1-x_{n}^n)^2 }
$$

## Entorno de un punto en $R^n$ 
Sea $X_0$ un punto en $R^n$ y **r** un número positivo, llamaremos entorno de centro $X_0$ y  radio r al conjunto de todas las partes de X de $R^n$ tales que su distancia al punto $X_0$ sea menor que r.
En símbolos:
$$
 N(X_{0}, r) = { X \in R^n / \mid X - X_{0} \mid < r}
$$

## Definición de Límite:

Sea f una función de n variables definida en un entorno del punto $X_0$ excepto quizás en ese punto, entonces decimos que el límite de $f(X)$ se aproxima a $x_0$ es L y lo expresamos como:
$$
 Lim_{X\to X_{0}}(f(X)) = L
$$

Si para cualquier número $\epsilon > 0$, existe un número $\delta > 0$ tal que siempre se tenga que:
$$ 0 < \mid X-X_{0}\mid <  \delta$$
también entonces se tendrá:
$$ \mid f(X) - L\mid < \epsilon $$

Esta definición la podemos transmitir a la forma de entornos de la siguiente forma:
Para todo $N(L,\epsilon)$ debe existir un $N(X_0, \delta)$, y para que $X \in N^*(X_0, \delta)$, la función $f(x) \in N(L, \epsilon)$

¿Cuándo se puede asegurar que L es el límite de f(x,y) cuando (x,y) -> (x0, y0)?
**Solo podemos hacerlo categóricamente cuando sea posible establecer, en forma totalmente independiente de cualquier camino. Por lo tanto la única forma de independizarnos de los infinitos caminos, es utilizar la definición ε-δ de límite. Pero esto suele ser extremadamente laborioso y difícil.**


Métodos para el estudio de los límites en funciones de varias variables.

**Usando caminos:** 

Si:
$\lim_{\left(x,y\right)\to\left(x_0,y_0\right)} f(x,y)$ exista y sea L entonces los límites de:


$$
Lim_{x\to x_{0}}f(x,g_{1}(x)) \space y \space {Lim_{x\to x_{0}}f(x,g_{2}(x))}
$$

Si estos 2 límites existen donde $y = g_1(x)$ e $y = g_2(x)$ son dos curvas que pasan por $X_0 = (x_0, y_0)$, deben valer L.

Esto quiere decir que si $y=g_1(x)$ y $y=g_{2}(x)$ son dos curvas que pasan por $X_0$ y, si se puede demostrar que estos límites son diferentes entonces no el **límite no existe.**

**Limites Sucesivos o reiterados:** 
Otra alternativa es demostrar la no existencia del límite mediante límites sucesivos, para esto 
primero se evalua en una variable y después en la otra es decir.

$$

\lim_{y \to y_0} \left( \lim_{x \to x_0} f(x, y) \right) = \lim_{y \to y_0} \lim_{x \to x_0} f(x, y)
$$

$$


\lim_{x \to x_0} \left( \lim_{y \to y_0} f(x, y) \right) = \lim_{x \to x_0} \lim_{y \to y_0} f(x, y)

$$

## Teoremas
Sean $f(X)$ y $g(X)$ funciones de n variables definidas en un conjunto abierto D de $R^n$ y sea $X_0$ un punto de D, ó un punto frontera de D, y suponiendo que:
$$
 Lim _{X\to X_{0}}f(X) = L \space y \space  Lim _{X\to X_{0}}g(X) = M
$$
donde L y M son números reales, entonces:

**Estos teoremas se asumen sin demostración**

$$
a) \quad \lim_{x \to x_0} [f(X) \pm g(X)] = L \pm M
$$
$$
b) \quad \lim_{x \to x_0} [f(X) \cdot g(X)] = L \cdot M
$$
$$
c) \quad \lim_{x \to x_0} [K \cdot f(X)] = K \cdot L \quad \text{donde } K \text{ es un número real}
$$

$$

d) \quad \lim_{x \to x_0} \left[ \frac{f(X)}{g(X)} \right] = \frac{L}{M} \quad ; \quad M \neq 0
$$

$$
e) \quad \lim_{x \to x_0} [f(X)]^{r/s} = L^{r/s} \quad \text{donde } r \text{ y } s \text{ son números enteros y } s \neq 0
$$

