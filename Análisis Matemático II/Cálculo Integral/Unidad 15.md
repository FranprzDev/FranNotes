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
$$Si trabajamos con la formula del Jacobiano podemos llegar a deducir cual es, por una cuestión de que **me da paja**, el jacobiano es simplemente **r**.
Entonces se cumple que:
$$
\iint_R f(x,y) \, dA = \iint_R f(r*cos(\theta), \space r*sen(\theta)) \space r\space dA
$$
### Teorema de Integración en Coordenadas Polar Circular
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