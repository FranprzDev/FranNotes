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
$$