[[Unidad 15]]

# Cambios de variables en Integrales Triples

## Transformación de R3 en R3
![[Pasted image 20250308220133.png]]

## Jacobiano de una  Transformación
Teniendo la transformación planteada anteriormente, el jacobiano de esta transformación estará representado por:
$$
J(X, Y, Z) (u, v, w) = \begin{vmatrix} 
\frac{\partial X}{\partial u} & \frac{\partial X}{\partial v} & \frac{\partial X}{\partial w} \\
\frac{\partial Y}{\partial u} & \frac{\partial Y}{\partial v} & \frac{\partial Y}{\partial w} \\
\frac{\partial Z}{\partial u} & \frac{\partial Z}{\partial v} & \frac{\partial Z}{\partial w} 
\end{vmatrix}
$$
Cumple las mismas propiedades que en las transformaciones para dobles.

## Teorema de Integración con Cambio de Variable de R3 en R3
Suponiendo que existe la integral triple, y sea T una transformación definida por lo anteriormente mencionado, y las funciones X, Y, Z tienen primeras derivadas parciales continuas en D y si el jacobiano es distinto de 0 para todos los puntos que pertenezcan al conjunto D entonces:

$$
\iiint_R f(x,y,z) \, dV = \iiint_D f[X(u,v,w), Y(u,v,w), Z(u,v,w)] \left| J \left( \frac{X,Y,Z}{u,v,w} \right) \right| \, dV
$$
Este teorema aun es verdadero si el jacobiano es 0, el unico problema es cuando cambia de signo en D.

## Integrales Triples en Coordenadas Cilíndricas Circulares
### Transformación de Coordenadas Cilíndricas Circulares a Cartesianas
![[Pasted image 20250308220950.png]]

## Teorema de Integración en Coordenadas Cilíndricas Circulares
Si **D** se mapea sobre **R** mediante la transformación
$$
\begin{align*}
T = \begin{cases}
x = r*cos(\theta) \\
y = r*sen(\theta) \\
z = z
\end{cases}
\end{align*}
$$
y se cumple que $$ r >= 0 $$ en D, entonces se tendrá 
$$
\iiint_R f(x, y, z) \, dV = \iiint_D f(r \cos \theta, r \sin \theta, z) \, r \, dV
$$Los límites de integración los sacamos mediante un teorema, donde suponemos la existencia de la integral triple en una región **R** **cerrada y acotada** cuya proyección **R'** sobre el plano xy es del tipo T_(theta) y es la gráfica de:
$$
\{(r, \theta) \mid g_1(\theta) \leq r \leq g_2(\theta), \, a \leq \theta \leq b, \, k_1(r,\theta) \leq z \leq k_2(r, \theta) \}
$$
Además se cumple que:
$$
b - a \leq 2\pi \quad \text{y} \quad g_1(\theta) \geq 0
$$
Entonces:
$$
\iiint_{R} f(x, y, z) \, dV = \int_{a}^{b} \int_{g_1(\theta)}^{g_2(\theta)} \int_{k_1(r, \theta)}^{k_2(r, \theta)} f(r \cos \theta, r \sin \theta, z) \, r \, dz \, dr \, d\theta
$$


## Integrales Triples en Coordenadas Cilindricas Elipticas
$$
\begin{align*}
T = \begin{cases}
x = a*r*cos(\theta) \\
y = b*r*sen(\theta) \\
z = z
\end{cases}
\end{align*}
$$
El Jacobiano de esta transformación será:
$$J (\frac{x,y,z}{r, \theta, z}) = a*b*r
$$

## Teorema de Integración en Coordenadas Cilíndricas Elípticas
Si D se mapea en R mediante la transformación:
$$
\begin{align*}
T = \begin{cases}
x = a*r*cos(\theta) \\
y = b*r*sen(\theta) \\
z = z
\end{cases}
\end{align*}
$$
Si $$ r >= 0$$
en D entonces, de acuerdo al teorema especificado, se tendrá.
$$
\iiint_R f(x, y, z) \, dV = \iiint_D f(a*r*\cos \theta, b*r*\sin\theta, z) \, r \, dV
$$
Los límites de integración se los puede obtener del siguiente teorema.

Suponiendo que la integral triple existe, y una región **R** **cerrada y acotada** cuya proyección **R'** sobre el plano **xy** es una región que es la gráfica de coordenadas polares elípticas en el plano; tal que:
$$
\{(r, \theta) / 0 \leq r \leq 1 \, c \leq \theta \leq d\}
$$
Donde se cumpla que:
$$
d - c \leq 2\pi
$$
Entonces si R seta limitada superiormente por la gráfica de:
$$
z = k_2(r, \theta) $$e inferiormente por la gráfica de
$$
z = k_1(r, \theta) 
$$
Entonces podemos concluir que:
$$
\iiint_{R} f(x, y, z) \, dV = \int_{c}^{d} \int_{0}^{1} \int_{k_1(r, \theta)}^{k_2(r, \theta)} f(a * r \cos \theta, b * r\sin \theta, z) \, r \, dz \, dr \, d\theta
$$

## Integrales Triples con Coordenadas Esféricas
Sea una transformación **T** dada por:
$$
\begin{align*}
T = \begin{cases}
x = \rho*cos(\theta)*sen(\phi) \\
y = \rho*sen(\theta)*sen(\phi) \\
z = \rho * cos(\theta)
\end{cases}
\end{align*}
$$
De modo tal que la gráfica de la función queda de la siguiente forma:
![[Pasted image 20250308230858.png]]
Donde:
- $\rho$ será el radio.
- $\theta$ será la rotación en el plano xy
- $\phi~$ será la rotación en el eje Z

El jacobiano de esta transformación será igual a:
$$
J (\frac{x,y,z}{r, \theta, z}) = -\rho^2 *sen(\phi)
$$
## Teorema de Integración en Coordenadas Esfericas
Entonces si se cumple lo anteriormente mencionado,  donde D se mapea en R mediante la transformación T y si $\rho^2 * sen(\phi)$ no cambia de signo en D se tendrá:

$$
\iiint_R f(x, y, z) \, dV = \iiint_D f(\rho cos\theta sen\phi, \rho sen\theta  sen \phi, \rho cos\phi) \, \rho^2 sen\phi \, dV
$$
Para el cálculo de los límites entonces sabemos que $\rho \geq 0 \ y \ 0 \leq \Phi \leq \pi$
entonces el jacobiano $\rho^2 * sen(\Phi) \geq 0$  en cualquier región de D. Los límites de integración además los sacaremos del plano en coordenadas esfericas.

**Teorema:**
Suponiendo que la integral triple existe, y que también están definidas las funciones $k_1 \ y \ k_2$ de dos variables independientes, dos funciones $g_1 \ y \ g_2$ de una variable independiente y numeros reales **a** y **b** con la propiedad que R es acotada por las gráficas de

$$
\begin{align*}
\begin{cases}
\rho = k_1(\theta, \phi) \\
\rho = k_2(\theta, \phi) \\
\theta = g_1(\phi) \\
\theta = g_2(\phi) \\
\phi = a \\
\phi = b
\end{cases}
\end{align*}
$$
Si el jacobiano no cambia de signo en R, entonces:
$$
\iiint_{R} f(x, y, z) \, dV = \int_{a}^{b} \int_{g_1(\phi)}^{g_2(\phi)} \int_{k_1(\theta, \phi)}^{k_2(\theta, \phi)} f(\rho cos\theta sen\phi,\rho sen\theta sen\phi, \rho cos \phi) \, \rho^2 sen \phi\, d \rho \, d\theta \, d\phi
$$

Se puede establecer dicha integral sin problemas.