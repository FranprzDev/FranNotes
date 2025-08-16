---
excalidraw-plugin: parsed
tags:
  - excalidraw
---
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
1) Si en la definición de la integral de línea la función $f(x,y) \geq 0$  la integral representará el **área de la cortina curva vertical**, que define el arco de curva C. Limitada inferiormente por el xy y por arriba por la superficie **f(x,y)**
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
1) Con respecto al eje x será:

==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


## Drawing
```compressed-json
N4IgLgngDgpiBcIYA8DGBDANgSwCYCd0B3EAGhADcZ8BnbAewDsEAmcm+gV31TkQAswYKDXgB6MQHNsYfpwBGAOlT0AtmIBeNCtlQbs6RmPry6uA4wC0KDDgLFLUTJ2lH8MTDHQ0YNMWHRJMRZFAA5FAGYyJE9VGEYwGgQAbQBdcnQoKABlALA+UEl8PGzsDT5GTkxMch0YIgAhdFQAayKuRlwAYXpMenwEEABiADMx8ZAAX0mgA
```
%%
