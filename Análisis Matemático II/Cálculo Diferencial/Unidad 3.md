[[Unidad 2]]

# Continuidad

## Continuidad en un punto
Sea f una función de n variables definida en un conjunto abierto D de $R^n$, Decimos que f es continua en el punto $X_0$ de D, si y sólo si se cumple que:
$$
\lim_{ _X \to X_{0} }f(X) = f(X_{0})
$$
donde $X = (x_1,x_2, \dots, x_n)$ y $X_0 = (x_1^0, x_2^0, \dots, x_n^0)$ son dos puntos n dimensionales.

Esta definición implica que:
1) Existe $f(X_0)$
2) Existe el $\lim_{ X \to X_{0} }f(X)$
3) $\lim_{ X \to X_{0} }f(X) = f(X_{0})$ 

## Tipos de Discontinuidades
Las discontinuidades se clasifican en evitables y no evitables.
- Si existe el límite la discontinuidad en $X_0$ es evitable.
- Si no existe el límite, la discontinuidad en $X_0$ es inevitable.

Cuandol a discontinuidad es de tipo evitable se puede redefinir la función de tal forma que $f(X_0) = \lim_{ X \to X_{0} }f(X)$ entonces f se vuelve continua en $X_0$

## Propiedades de las funciones continuas:
Sean f(X) y g(X) funciones de n variables definidas en un conjunto abierto D de $R^n$, si f y g son continuas en el punto $X_0$ de D, también son continuas en $X_0$ las funciones
1) Suma algebraica de las funciones.
2) Producto de las funciones
3) Función por constante.
4) División de las funciones siempre y cuando la división sea distinta de 0.

## Demostración de las propiedades
### Propiedad I 
**Tesis:**
Sean f(X) y g(X) funciones de n variables definidas en un conjunto abierto D de $R^n$, si f y g son continuas en el punto $X_0$ de D, también son continuas en $X_0$ las funciones
**Hipótesis:**
$f(X) + g(X) es continua en X_0$ 
**Demostración**
Como f es continua entonces:
$$
\lim_{  X \to X_{0} }f(X) = f(X_{0}) 
$$
Como g es continua entonces:
$$
\lim_{  X \to X_{0} }g(X) = g(X_{0})
$$
Por propiedad de los límites
$$
\lim_{  X \to X_{0} }[f(X)+g(X)] = \lim_{ X \to X_{0} }f(X)+\lim_{ X \to X_{0} }   g(X)
$$
Como dijimos anteriormente estos son $f(X_0) \space y \space g(X_0)$ respectivamente, por lo tanto

$$
\lim_{  X \to X_{0} }[f(X)+g(X)] = f(X_{0}) + g(X_{0})
$$
Con esto se demuestra que la suma es continua.
El resto de propiedades se demuestra de la misma forma.

### Continuidad de una función compuesta
Suponga que f es una función de una variable y que g y es una función de n variables tal que g es continua en $X_0$ y f es continua en $g(X_0)$, entonces la función compuesta $f[g(X)]$ es continua en $X_0$ 