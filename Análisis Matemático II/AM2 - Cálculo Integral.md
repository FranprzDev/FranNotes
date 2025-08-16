[[# Unidad 13]]

# Integrales dobles

## Definición de Integral Doble
Una **región cerrada** es cuando la frontera es parte de la región, es decir la definición incluye la frontera.
Una **región acotada** es cuando existe un rectángulo con la propiedad de que cada punto de la región sea un punto interior del rectángulo.

![[Pasted image 20250307224942.png]]

## Teorema de Existencia de las Integrales Dobles
Si f(x,y) es una función de dos variables independientes que es **continua** en una **región cerrada y acotada** de R y si la **frontera** de R es una **cerrada simple y  rectificable**, entonces la integral doble existe.
**Observaciones:**
- **Curva simple:**
	No pasa 2 veces por el mismo punto. (Ej: No es un infinito)
- **Curva rectificable**
	Se puede asignar un número real a la longitud de la curva.
	 
![[Pasted image 20250307231645.png]]
## Teorema de Evaluación
![[Pasted image 20250307232153.png]]



## Propiedades de las integrales dobles
![[Pasted image 20250218034354.png]]
![[Pasted image 20250218034425.png]]
![[Pasted image 20250218034434.png]]
![[Pasted image 20250218034443.png]]
![[Pasted image 20250218034453.png]]
![[Pasted image 20250218034501.png]]




# Unidad 14


[[Unidad 13]]

# Integrales Triples

## Definición 
![[Pasted image 20250308033606.png]]

## Región cerrada y acotada en R3
![[Pasted image 20250218034530.png]]

![[Pasted image 20250308034629.png]]

## Teorema de Existencia de la Integral Triple
Si f(x,y,z) es continua sobre una región cerrada acotada de R de R3, cuya frontera consiste en la unión de un número finito de superficies uniformes, entonces la integral triple en la región R existe.

## Clasificación de las Regiones de Integración
![[Pasted image 20250308041201.png]]


## Propiedades de las Integrales Triples

![[Pasted image 20250218034715.png]]

![[Pasted image 20250218034721.png]]
![[Pasted image 20250218034730.png]]
![[Pasted image 20250218034735.png]]
![[Pasted image 20250218034742.png]]


# Unidad 15


[[Unidad 14]]

## Transformación de R2 en R2
Si queremos pasar dos regiones de R2, **D** y **R**, utilizaremos una función **T** cuyo dominio será **D** y su rango será **R**, y será denominada como una **transformación de D sobre R**. Esta transformación la podemos ver como:
$$
\begin{align*}
T = \begin{cases}
x = X(u, v) \\
y = Y(u, v)
\end{cases}
\end{align*}
$$
Donde X e Y son funciones cuyos dominios están contenidos en D.

## Jacobiano de una Transformación de R2 en R2
Siendo T una transformación especificada por el sistema x = X(u,v), y = Y(u,v), el jacobiano de esta transformación T se representa por 
$$
J\left( \frac{X, Y}{u, v} \right) = 
\begin{vmatrix} 
\frac{\partial X}{\partial u} & \frac{\partial X}{\partial v} \\ 
\frac{\partial Y}{\partial u} & \frac{\partial Y}{\partial v} 
\end{vmatrix}
$$
De este modo podremos calcular el jacobiano para no alterar la función al hacer un cambio de variables.

## Inversa de una Transformación de R2 en R2 #skip

## Teorema de Integración con Cambio de Variables de R2 en R2
Suponiendo que la integral doble existe y sea T una transformación definida por x = X(u, v), y = Y(u, v), donde u y v pertenezcan a D que es una región de R2, la cual se transforma sobre R mediante T, y si las funciones X e Y tienen primeras derivadas parciales continuas en D, y si resulta que el Jacobiano es distinto de 0 para todos los puntos (u, v) que pertenezcan a D, entonces
$$

\iint_R f(x,y) \, dA = \iint_D f[X(u,v), Y(u,v)] \left| \frac{\partial(X,Y)}{\partial(u,v)} \right| \, dA
$$
Si el Jacobiano se hace 0 no pasa nada, el unico momento donde hay problemas es cuando el jacobiano cambia de signo en la región D.

## Integrales dobles en Coordenadas Polares Circulares
### Transformación de Coordenadas Polares Circulares a Cartesianas
Si queremos utilizar coordenadas polares circulares, utilizaremos la siguiente transformación
$$
\begin{align*}
T = \begin{cases}
x = r*cos(\theta) \\
y = r*sen(\theta)
\end{cases}
\end{align*}
$$

Si trabajamos con la formula del Jacobiano podemos llegar a deducir cual es, por una cuestión de que **me da paja**, el jacobiano es simplemente **r**.
Entonces se cumple que:
$$
\iint_R f(x,y) \, dA = \iint_R f(r*cos(\theta), \space r*sen(\theta)) \space r\space dA
$$
### Teorema de Integración en Coordenadas Polar Circular
$$x_{2}$$
Si la Región R (la que queremos integrar) está delimitada por las gráficas de 
$$
r = g_1(\theta)
$$
$$r = g_2(\theta)$$
$$a = \theta \space y \space b = \theta $$
Segun se muestra en la figura
![[Pasted image 20250308051219.png]]
Entonces la Región R, será la gráfica de:
$$ {(r, \theta) /\space  g_1(\theta)<= r <= g_2(\theta) \space , \space  a <= \theta <= b }$$
Entonces es una región de tipo $$T_\theta$$
Y su integral será definida como:
$$
\iint_R f(x,y) \, dA = \int_{a}^{b} \int_{g_1(\theta)}^{g_2(\theta)} f[rcos(\theta)), rsen(\theta))] rdr \, d\theta
$$

## Integrales Dobles en Coordenadas polares elipticas
### Transformación de Coordenadas Polares Elípticas a Cartesianas
Para utilizar esta transformación plantareamos la siguiente transformación:
$$
\begin{align*}
T = \begin{cases}
x = a*r*cos(\theta) \\
y = b*r*sen(\theta)
\end{cases}
\end{align*}
$$

Y el jacobiano de esta transformación es **abr**
Por lo tanto la integral quedaría:
$$
\iint_R f(x,y) \, dA = \iint_R f(a*r*cos(\theta), \space b*r*sen(\theta)) \space a*b*r\space dA
$$

### Teorema de Integración en Coordenadas Polares Elípticas
Si tenemos la ecuación canónica de una elipse:
$$ 
\frac{x^2}{a^2}+\frac{y^2}{b^2}=1
$$
Y la región R está limitada en coordenadas polares elipticas por las gráficas:
$$ r = 1 \space, \space \theta = c \space, \space \theta = d$$
Como lo indica la siguiente figura
![[Pasted image 20250308052045.png]]
Entonces la región R, definida por la gráfica de:
$$ (r, \space \theta) / \space 0 <= r <= 1 \space, \space c <= \theta <= d) $$

Si la integral doble existe y si R es una región que es la gráfica en coordenadas polares elípticas de 
$$ (r, \space \theta) / \space 0 <= r <= 1 \space, \space c <= \theta <= d) $$
donde ocurra que:
$$ d - c <= 2\pi$$
entonces:
$$
\iint_R f(x,y) \, dA = \int_{c}^{d} \int_{0}^{1} f[a*r*cos(\theta)), b*r*sen(\theta))] \space a*b*r *dr\,d\theta
$$

# Unidad 16


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
y se cumple que $$ r >= 0 $$
en D, entonces se tendrá 
$$
\iiint_R f(x, y, z) \, dV = \iiint_D f(r \cos \theta, r \sin \theta, z) \, r \, dV
$$

Los límites de integración los sacamos mediante un teorema, donde suponemos la existencia de la integral triple en una región **R** **cerrada y acotada** cuya proyección **R'** sobre el plano xy es del tipo T_(theta) y es la gráfica de:
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
z = k_2(r, \theta) 
$$
e inferiormente por la gráfica de
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

# Unidad 17


[[Unidad 16]]

# Aplicaciones de las Integrales Dobles

## Cálculo del área de una región plana
Sea R la región que queremos calcularle el área encerrada por **E**, partiremos a **E** mediante rectas paralelas a los ejes coordenados, así generaremos la partición interna tal que:
$$
P = \{R_0,R_1, ..., R_n \}
$$
Esto se puede ver representado de la siguiente forma:
![[Pasted image 20250309035437.png]]
Si observamos obtendremos muchos $R_i$, y el área de estos estará dado por:
$$ \Delta A_i = \Delta X_i * \Delta Y_i$$

Por lo tanto, si consideramos la sumatoria de Riemman, considerando todos los rectángulos, el área estará dada de forma aproximada por:
$$A_{R}=\sum_{i=1}^{n}\Delta A_{i}$$
Para encontrar el valor exacto lo que haremos será tomar el límite de esta sumatoria, es decir.

$$A_{R}=\lim_{\left\Vert P\right\Vert\to0}\sum_{i=1}^{n}\Delta A_{i}$$
Donde la función $f(\xi_i, \eta_i) = 1$ , sabiendo esto por definición de integral entonces
$$
A_R = \iint_R{1*dA}
$$

## Masa de una placa / lámina / hoja de densidad variable
Definimos como densidad superficial
$$ \delta(x,y) = \frac{dm}{dA} \ \ [\frac{Kg}{m^2}]$$

Por lo tanto, si despejamos:
$$ dm = \delta(x,y) * dA$$

Al aplicar la suma de riemman, por la interpretación fisica, tendremos que la masa total de la lámina plana es:
$$
M = \iint_R(\delta(x,y) * dA) 
$$

Si queremos calcular el peso, basta con recordad que el peso especifico $\rho$, es igual a la densidad por la aceleración de la gravedad g, es decir:
$$ \rho (x,y) = g * \delta(x,y) $$

Por lo que se puede concluir que :
$$ P = \iint_R \rho(x,y)*dA$$

Como g es una constante (la de gravedad), entonces:
$$ 
P = g\iint_R\delta(x,y) * dA 
$$
## Momentos Estáticos respecto a los ejes coordenados cartesianos de una lámina plana de densidad variable.
El momento estático es conocido como un **momento de primer orden**, dado que la distancia está elevada a la potencia 1.
Dado un $dM = \delta(x,y)dA$ producirá momentos estáticos elementos $dI_x \ y \ dI_y$ con respecto a los ejes coordenados.
![[Pasted image 20250309040813.png]]
Entonces:
1) $dI_x$ es el producto de $dM$ por la distancia "y" al eje x.
	Es decir:
		$dI_x = y * dM = y * \delta(x,y) * dA$
		Entonces el momento estático total de la lámina plana R respecto del eje X es:
		$I_x = \iint_R y * \delta(x,y) * dA$ 
2) $dI_y$ es el producto de $dM$ por la distancia "x" al eje y.
	Es decir:
		$dI_y = x * dM = x * \delta(x,y) * dA$
		Entonces el momento estático total de la lámina plana R respecto del eje X es:
		$I_y = \iint_R x * \delta(x,y) * dA$ 
## Momentos de Inercia con Respecto de los ejes coordenados cartesianos de una lámina plana de densidad variable.
Este momento se conoce como segundo orden, ya que la distancia se encuentra al cuadrado.
![[Pasted image 20250309041108.png]]
Entonces:
1) $dI_x$ es el producto de $dM$ por la distancia "y" al eje x.
	Es decir:
		$dJ_x = y^2 * dM = y^2 * \delta(x,y) * dA$
		Entonces el momento estático total de la lámina plana R respecto del eje X es:
		$J_x = \iint_R y^2 * \delta(x,y) * dA$ 
2) $dI_y$ es el producto de $dM$ por la distancia "x" al eje y.
	Es decir:
		$dJ_y = x^2 * dM = x^2 * \delta(x,y) * dA$
		Entonces el momento estático total de la lámina plana R respecto del eje X es:
		$J_y = \iint_R x^2 * \delta(x,y) * dA$ 
**Teorema:**
El momento de inercia de una lámina plana R de densidad variable, respecto del centro del sistema de coordenadas cartesianas (0,0), es igual a la suma de los momentos de inercia respecto a los ejes ortogonales del sistema, es decir: $J_0 = J_x + J_y$

**Hipotesis:**
- R es una lámina plana de densidad variable $\delta(x,y)$ con los momentos de inercia $J_x \  y \ J_y$ , respecto a los ejes coordenados y $J_0$ respecto del origen.
**Tesis:**
$J_0 = J_x + J_y$
**Demostración:**
Si consideramos la figura:
![[Pasted image 20250309041556.png]]
Vemos que el **dM** producirá en el centro de coordenadas un momento $J_0$, el cual es la distancia al cuadrado, por lo tanto
$$dJ_0 = d*2 * dM = d^2 \delta(x,y) * dA$$
Si aplicamos pitagoras, entonces sabemos que $d^2 = x^2 + y^2$,
por lo tanto si lo planteamos como una integral:
$$J_0 = \iint_R(x^2+y^2)*\delta(x,y)*dA$$
Por propiedad de las integrales podemos separarlas.
$$J_0 = \iint_R x^2 * \delta(x,y) * dA + \iint_R x^2 * \delta(x,y) * dA$$
Por lo tanto, sabemos que lo primero es $J_y$ y lo segundo es $J_x$, entonces simplemente remplazamos.
$$J_0 = J_y + J_x$$

## Coordenadas del centro de masa de una lámina plana de densidad variable
Por definición física, **en el centro de masa los momentos estáticos con respecto a los ejes paralelos a las coordenadas cartesianas con origen en el centro de masa son iguales a cero.**
Considerando la siguiente figura:
![[Pasted image 20250309042057.png]]
Entonces por la ley fisica tenemos que $I_y = 0$ y $I_x = 0$
**Si trabajamos con $I_y$**
$$\iint_R(x-x_c)\delta(x,y)dA=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iint_Rx\delta(x,y)dA-x_c\iint_R\delta(x,y)dA=0
$$
Como lo que queremos saber es $x_c$ lo despejamos
$$
x_c = \frac{\iint_Rx\delta(x,y)dA}{\iint_R\delta(x,y)dA}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_y$, es decir:
$$
x_c = \frac{I_y}{M}
$$
**Si trabajamos con $I_x$** (mismo procedimiento)
$$\iint_R(y-y_c)\delta(x,y)dA=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iint_Ry\delta(x,y)dA-y_c\iint_R\delta(x,y)dA=0
$$
Como lo que queremos saber es $y_c$ lo despejamos
$$
y_c = \frac{\iint_Ry\delta(x,y)dA}{\iint_R\delta(x,y)dA}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_x$, es decir:
$$
y_c = \frac{I_x}{M}
$$


# Unidad 18


[[Unidad 17]]

# Aplicaciones de las Integrales en Triples
## Cálculo de Volúmenes
Si definimos $f(\xi_i, \eta_i, \gamma_i) = 1$ entonces, esto no afectará al volumen de la partición de los n paralepipedos, por lo tanto podremos saber con exactitud el volumen.
Por lo tanto, efectivamente:
$$ V_R = \iiint_R dV$$
## Aplicaciones Físicas
# Masa y Peso de un Sólido de Densidad variable
Si un cuerpo tiene una densidad que varía punto a punto según los valores que toma la función $\delta = \delta(x,y,z)$ entonces:
$$ \delta(x,y,z) = \lim_{\Delta V\to0}\frac{\Delta M}{\Delta V}$$
entonces:
$$\delta(x,y,z) = \frac{dM}{dV}$$
Por lo tanto si despejamos $dM$
$$
dM = \delta(x,y,z) * dV$$
Entonces, si integramos miembro a miembro.
$$M =\iiint_R\delta(x,y,z)dV$$
Para el cálculo del peso, partimos de la definición que es la función delta por la gravedad, por lo tanto.
$$ P = g\iiint_R\delta(x,y,z)dV$$
## Momento Estático de un Sólido de Densidad Variable con respecto a los planos coordenados cartesianos

Cuando trabajamos con **alfajores triples**, hay que tener en cuenta que los momentos estáticos son en base a los planos, por lo tanto
- Con respecto al plano xy -> $dI_{xy}$
- Con respecto al plano xz -> $dI_{xz}$
- Con respecto al plano yz -> $dI_{yz}$

Por lo tanto: 
1) $dI_{xy}$ es el producto de $dM$ por la distancia "z" al plano xy.
	$dI_{xy} = zdM = z \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{xy}=\iiint_Rz \delta(x,y,z) dV$
2) $dI_{xz}$ es el producto de $dM$ por la distancia "y" al plano xz.
	$dI_{xz} = ydM = y \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{xz}=\iiint_Ry \delta(x,y,z) dV$
3) $dI_{yz}$ es el producto de $dM$ por la distancia "x" al plano yz.
	$dI_{yz} = xdM = x \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{yz}=\iiint_Rx \delta(x,y,z) dV$

## Momentos de Inercia de un Sólido de densidad variable respecto a los planos coordenados cartesianos
En este caso de vuelta, necesitaremos los planos xy, xz, yz y en este caso las distancias estarán al cuadrado.

Por lo tanto: 
1) $dJ_{xy}$ es el producto de $dM$ por la distancia "$z^2$" al plano xy.
	$dJ_{xy} = z^2dM = z^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{xy}=\iiint_Rz^2 \delta(x,y,z) dV$
2) $dJ_{xz}$ es el producto de $dM$ por la distancia "$y^2$" al plano xz.
	$dJ_{xz} = y^2dM = y^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{xz}=\iiint_Ry^2 \delta(x,y,z) dV$
3) $dJ_{yz}$ es el producto de $dM$ por la distancia "$x^2$" al plano yz.
	$dJ_{yz} = x^2dM = x^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{yz}=\iiint_Rx^2 \delta(x,y,z) dV$

## Coordenadas del centro de masa de un sólido de densidad variable
Como ya sabemos, los momentos estáticos respecto a los planos son 0.
Por lo tanto entonces:

**Si trabajamos con $I_{yz} = 0$**
$$\iiint_R(x-x_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Rx\delta(x,y,z)dV-x_c\iiint_R\delta(x,y,z)dV=0
$$
Como lo que queremos saber es $x_c$ lo despejamos
$$
x_c = \frac{\iiint_Rx\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{yz}$, es decir:
$$
x_c = \frac{I_{yz}}{M}
$$
**Si trabajamos con $I_{xz}$** (mismo procedimiento)
$$\iiint_R(y-y_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Ry\delta(x,y,z)dV-y_c\iiint_R\delta(x,y,z)dV=0
$$
Como lo que queremos saber es $y_c$ lo despejamos
$$
y_c = \frac{\iiint_Ry\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{xz}$, es decir:
$$
y_c = \frac{I_{xz}}{M}
$$
**Si trabajamos con $I_{xy}$** (mismo procedimiento)
$$\iiint_R(z-z_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Rz\delta(x,y,z)dV-z_c\iiint_R\delta(x,y,z)dV
$$
Como lo que queremos saber es $z_c$ lo despejamos
$$
z_c = \frac{\iiint_Rz\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{xz}$, es decir:
$$
z_c = \frac{I_{xy}}{M}
$$

# Unidad 19


[[unidad 18]]

# Campos escalares y vectoriales

# Este se SKIPEA FOERTE

# Unidad 20


[[Unidad 19]]

# Integrales de Línea

![[Pasted image 20250309050057.png]]

## Definición formal

  

Si f esta definida sobre una curva suave C dada por:

  

$$

\begin{align*}

C = \begin{cases}

x = x(t) \\

y = y(t) \\

\end{cases}

\end{align*}

$$

con $a \leq t \leq b$ ó dada por su forma vectorial $r(t) = x(t) i + y(t) j$ entonces la **integral de línea de f a lo largo de C** es:

$$

\int_Cf(x,y)ds=$\lim_{\left\Vert P\right\Vert\to0}\sum_{i=1}^{n}f\left(\overline{x}_{i},\overline{y}_{i}\right)\Delta S_{i}$

$$

Si este límite existe.

  

## Evaluación de Integral de linea.

Al parametrizar la ecuación llegamos a una integral definida común.

Si f es continua en D que contiene a la curva suave C, y si C viene dada por la parametrización:

$$

\begin{align*}

C = \begin{cases}

x = x(t) \\

y = y(t) \\

\end{cases}

\end{align*}

$$

Con $a \leq t \leq b$

Donde

$$dS = \sqrt{(x'(t))^2+(y'(t))^2}dt $$ entonces podemos reescribir la integral de línea como:

$$

\int_Cf(x,y)ds = \int_{a}^{b}f(x(t),y(t))*\sqrt{(x'(t))^2+(y'(t))^2}dt $$

- Se puede demostrar que cualquier parametrización produce el mismo valor de la integral, lo que importa son los valores de **a y b**.

- La definición se puede ampliar a la suma de varias curvas suaves que cumplan los requisitos.

- Si un parametro no cambia, entonces lo podemos mantener constante y por lo tanto solamente nos queda una integral izi pizi de 1 var.

  

## ¿Definiciones Raras?

**Hay un par de definiciones raras, pero no se entiende del todo para que sirven. Veliz las skipeo y por consiguiente yo también.**

  

## Aplicaciones de las Integrales de Línea

1) Si en la definición de la integral de línea la función $f(x,y) \geq 0$  la integral representará el **área de la cortina curva vertical**, que define el arco de curva C. Limitada inferiormente por el xy y por arriba por la superficie **f(x,y)**

2) Si $f(x,y) = 1$ entonces:

$$\int_CdS = \int_{a}^{b}\sqrt{[x'(t)]^2+[y'(t)]^2}*dt = L

$$

  Donde L será **la longitud de la curva plana C**

3) Esta extensión también es igual para tres variables.

  

## Aplicaciones Físicas

### Masa y peso de un alambre delgado de densidad variable

Si $\delta(x,y)$ representa la densidad lineal en cada punto $(x,y)$ de un alambre delgado en forma de curva, como se muestra en la figura

![[Pasted image 20250309052602.png]]

Tendremos que:

$$ \delta(x,y) = $\lim_{\Delta s\to0}\frac{\Delta M}{\Delta s}=\frac{dM}{dS}$$

Por lo tanto:

$$ \Delta M = \delta(x,y) \Delta s$$

Por lo tanto la masa del alambre es:

$$ M = \int_CdM = \int_C \delta(x,y)dS$$

Y el peso es:

$$

P = \int_C dP = g \int_C \delta(x,y)ds $$

### Momentos estáticos de un alambre delgado de densidad variable con respecto a los ejes coordenados cartesianos

Es el producto del $dM$ por la distancia al eje de referencia.

Por lo tanto:

![[Momentos Estáticos]]
### Momentos dinámicos de un alambre delgado de densidad variable con respecto a los ejes coordenados cartesianos
Como sabemos son momentos de segundo orden.
1) Con respecto al eje X será:
![[Pasted image 20250309055358.png]]
2) Con respecto al eje Y será:
 ![[Pasted image 20250309055435.png]]

### Centro de masa de un alambre delgado de densidad vari
Como ya sabemos el $C_m(x_c,y_c)$, y por la física los momentos estáticos son 0, entonces con la siguiente gráfica:
![[Pasted image 20250309055516.png]]

Si calculamos el momento estático respecto a $I_y$ 
![[Pasted image 20250309055815.png]]
Si calculamos el momento estático con respecto a $I_x$
![[Pasted image 20250309060011.png]]

# Unidad 21


[[Unidad 20- error]]
# Integrales de Superficie

## Definición
**Paso 1:**
Sea $f : u = f(x,y,z)$ una función continua en S, 
Se particiona la superficie S en n partes $S_1, S_2, S_3, ..., S_n$ cuyas áreas son $\Delta S_1, \Delta S_2, ..., \Delta S_n$ respectivamente. Como se ve en la figura
![[Pasted image 20250309064000.png]]
**Paso 2:**
Se elige un punto arbitrario $P_i(\xi_i, \eta_i, \theta_i)$ para cada partición respectiva.
**Paso 3:**
Consideramos la suma de Riemman
$$ f(\xi_1, \eta_1, \theta_1)\Delta s_{1} + f(\xi_2, \eta_2, \theta_2)\Delta s_{2} + \dots + f(\xi_i, \eta_i, \theta_i)\Delta s_{i} = \sum_{i=1}^{n}f\left(\xi_{i},\eta_{i},\theta_{i}\right)\Delta s_{i} $$
**Paso 4:**
Consideramos el límite de la suma cuando n -> $\infty$  y el mayor de los $s_i$ -> 0.
El valor del límite es por definición la **integral de la función $f(x,y,z)$ sobre la superficie S.**
$$
\iint_{S}f(x,y,z) ds = \lim_{ n \to \infty } \sum_{i=1}^{n} f(\xi_{i},\eta_{i},\theta_{i})\Delta s_{i} 
$$
## Teorema de Evaluación
Estas integrales se pueden calcular como integrales dobles, segun la porción de superficie que se proyecto sobre el plano x, y, ó el plano yz, ó el plano xz.
Por lo tanto tendremos 3 teoremas de evaluación.

### Teorema 1
Si S es una superficie de ecuación $z = g(x,y)$ y R es su proyección en el plano xy. Si $g \ , g_x \ , g_y$ son continuas en R y f es continua en S, entonces la integral de superficie de f sobre S es:
$$
\iint_{S}f(x,y,z)ds = \iint_{R}f(x,y,g(x,y))*\sqrt{ 1+\left[ \frac{\partial g}{\partial x} \right]^2 + \left[ \frac{\partial g}{\partial y} \right]^2} dA
$$

**Hipotesis**
- S es una superficie de ecuación $z = g(x,y)$
- $g \ , g_x \ , g_y$ son continuas en R
- f es continua en S
**Tesis**
$$
\iint_{S}f(x,y,z)ds = \iint_{R}f(x,y,g(x,y))*\sqrt{ 1+\left[ \frac{\partial g}{\partial x} \right]^2 + \left[ \frac{\partial g}{\partial y} \right]^2} dA
$$
**Demostración**
**QUE LA HAGA DIOS POR QUE ES MUY ENGORROSA HDP**

### Teorema 2
Si S es una superficie de ecuación $x = g(y, z)$ y R es su proyección en el plano yz. Si $g \ , g_y \ , g_z$ son continuas en R y f es continua en S, entonces la integral de superficie de f sobre S es:
$$
\iint_{S}f(x,y,z)ds = \iint_{R}f(g(y,z),y,z)*\sqrt{ 1+\left[ \frac{\partial g}{\partial z} \right]^2 + \left[ \frac{\partial g}{\partial y} \right]^2} dA
$$

### Teorema 3
Si S es una superficie de ecuación $y = g(x,z)$ y R es su proyección en el plano xz. Si $g \ , g_x \ , g_z$ son continuas en R y f es continua en S, entonces la integral de superficie de f sobre S es:
$$
\iint_{S}f(x,y,z)ds = \iint_{R}f(x,g(x,z),z)*\sqrt{ 1+\left[ \frac{\partial g}{\partial x} \right]^2 + \left[ \frac{\partial g}{\partial z} \right]^2} dA
$$

## Aplicaciones de las Integrales de Superficie
### Área de superficie
Si consideramos el caso particular donde la función $f(x,y,z) = 1$, entonces la integral de superficie proporcionará el **área de la superficie S**
Se sigue el paso a paso nada más que la función será igual a 1.

### Teorema de Evaluación para área de superficie
#### Teorema 1
**Hipotesis:**
- S es una superficie de ecuación $z = g(x,y)$
- $g \ , g_x \ , g_y$ son continuas en R
- f(x,y,z) = 1 y continua en S
**Tesis:**
$$A_{s} = \iint_{R} \sqrt{ 1+\left[ \frac{\partial g}{\partial x} \right]^2 + \left[ \frac{\partial g}{\partial y} \right]^2} dA
$$

#### Teorema 2
**Hipotesis:**
- S es una superficie de ecuación $y = g(x,z)$
- $g \ , g_x \ , g_z$ son continuas en R
- f(x,y,z) = 1 y continua en S
**Tesis:**
$$A_{s} = \iint_{R} \sqrt{ 1+\left[ \frac{\partial g}{\partial x} \right]^2 + \left[ \frac{\partial g}{\partial z} \right]^2} dA
$$

#### Teorema 1
**Hipotesis:**
- S es una superficie de ecuación $x = g(y,z)$
- $g \ , g_z \ , g_y$ son continuas en R
- f(x,y,z) = 1 y continua en S
**Tesis:**
$$A_{s} = \iint_{R} \sqrt{ 1+\left[ \frac{\partial g}{\partial z} \right]^2 + \left[ \frac{\partial g}{\partial y} \right]^2} dA
$$]()]()