[[Unidad 4]]

# Derivadas parciales

Sea f una función de dos variables x e y, **la derivada parcial de f con respecto de x** es aquella función representada por $f_x$ tal que su valor en cualquier punto (x,y) en el dominio de f está dado por:
$$
\lim_{  \Delta x \to 0 }(\frac{f(x+\Delta x, y)-f(x,y)}{\Delta x}) 
$$
si este límite exsite.
También podemos calcularlo para el otro lado es decir **la derivada parcial de f con respecto a y** de la siguiente forma:
$$
\lim_{  \Delta y \to 0 }(\frac{f(x, y+\Delta y)-f(x,y)}{\Delta y}) 
$$
Si es que este límite existe.

## Incremento parcial de la función

El númerador $f(x + \Delta x, y) - f(x,y)$ se lo denominada **incremento parcial de la función con respecto a x** y se lo denota como $\Delta_xZ$, así mismo podemos reescribir el límite con el incremento parcial de la función.

Osea podemos decir que una derviada parcial es **el límite del cociente incremental parcial de la función con respecto a una variable cuando el incremento de esa variable considerada tiende a cero**

Gráficamente esto se puede ver como:
**Respecto a X**
![[Pasted image 20250322185943.png]]
Esto quiere decir que la altura del $Z_0$ es teniendo en cuenta $f(x,y)$ mientras el otro que está más abajo, es teniendo en cuenta $f(x+ \Delta x, y)$, donde se ve el cambio.
Y una derivada parcial es la pendiente de la recta tangente de la curva en cuya parametrización se tiene en cuenta el plano $x = x_0 \space o \space y = y_0$ donde esta "derivada parcial" es la pendiente de la recta tangente de la curva C en el punto P.



# **Derivadas parciales de primer ORDEN**


![[Pasted image 20250217030910.png]]


## **Incremento total de una función en dos variables**
(cambian los 2, x ^ y)

Sea f una función de dos variable x, y entonces el incremento total de la función $(x_0, y_0)$ denotado por $\Delta z_0$ está dado por:
$$\Delta z_0 =\Delta f(x_0, y_0) = f(x_0 + \Delta x, y_0 + \Delta y) - f(x_0, y_0)$$

Gráficamente esto se puede ver como cambian en las dos variables, es decir hay un cambio tanto en x e y, por consiguiente esto impacta en el valor de z, haciendo que el valor de $\Delta z_0$ este en diagonal.


## Teorema del Valor medio del Cálculo Diferencial
### Para dos variables
Sea f una función de dos variables independientes x e y, que admite derivadas parciales continuas en su dominio. Entonces el incremento total de f cuando se incrementan simultáneamente todas las variables sin salir de su dominio es:

$$
\Delta z_{0} = \Delta xf_{x}(\xi _{1},\eta_{1}) + \Delta yf_{y}(\xi _{2},\eta_{2})
$$
Con:
$$
x_{0} \leq \xi_{i} \leq x_{0} + \Delta x \space y \space y_{0} \leq \eta_{i} \leq y_{0} + \Delta y \space con \space i = 1,2
$$

**Hipotesis:**
- En f están definidos los puntos $P_0(x_0,y_0) \space y \space P_{1}(x_{0} + \Delta x,y_{0} + \Delta y)$
- F es una función de variables independientes x e y.
- F admite derivadas parciales continuas en su dominio $f_x \space y \space f_y$
**Tesis:**
Lo de arriba
**Demostración:**
![[Pasted image 20250322192344.png]]

##  Generalización para N variables del TVM.

Sea f una función de n variables independientes $x_1, x_2, \dots, x_{n}$ que admite derivadas parciales continuas en su dominio. Entonces el incremento total de f cuando se incrementan simultáneamente todas las variables sin salir de su dominio es.
$$
\Delta z_{0} = \Delta x_{1}f_{x_{1}}(\xi_{1}^1,\xi_{2}^1,\dots,\xi_{n}^1) + \Delta x_{2}f_{x_{2}}(\xi_{1}^2,\xi_{2}^2,\dots,\xi_{n}^2) + \dots + \Delta x_{n}f_{x_{n}}(\xi_{1}^n,\xi_{2}^n,\dots,\xi_{n}^n)
$$
Donde esto lo podemos reescribir como una sumatoria de la siguiente forma:
$$
\Delta z_{0} = \sum_{i=1}^{n}\Delta x_{i}f_{x_{i}}\left(\xi^{i}_{1},\xi^{i}_{2},\dots,\xi^{i}_{n}\right)
$$
Donde los $\xi$ están comprendidos entre:
$$
x_{1}^0\leq \xi^i_{1}\leq x_{1}^0 + \Delta x_{1} \space ; x_{2}^0\leq \xi^i_{2}\leq x_{2}^0 + \Delta x_{2} \space ; \dots ; x_{n}^0\leq \xi^i_{n}\leq x_{n}^0 + \Delta x_{n} \space \space i = 1,2,3,\dots,n
$$

