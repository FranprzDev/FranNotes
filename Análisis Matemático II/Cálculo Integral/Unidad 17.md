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
