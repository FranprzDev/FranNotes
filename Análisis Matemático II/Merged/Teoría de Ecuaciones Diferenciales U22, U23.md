# Unidad 22

# Ecuaciones diferenciales

## Definición 

Una ecuación diferencial es una expresión matemática que involucra al menos una derivada de una función desconocida. La expresión puede contener también a la función desconocida.

## Clasificación de Ec. Diferenciales

- **Según el tipo:** 
	- Si posee derivadas ordinarias entonces será una ecuación diferencial ordinaria.
	- Si posee derivadas parciales, entonces será una ecuación diferencial parcial.
- **Según el orden:**
	- El orden es el orden de la derivada de más alto orden que aparece en la ecuación.
- **Según el grado:**
	- Es el grado algebraico de la derivada de más alto orden de la ecuación.
- **Segun la linealidad o no linealidad:**
	- Es lineal si cada término de la ecuación es de primer grado en la variable dependiente y en todas sus derivadas.

## Forma General de una Ecuación Diferencial Ordinaria
La solución general de una ecuación diferencial puede ser escrita como:
$$
F(x, y, y', y'', \dots, y^{(n)}) = 0
$$
También una ecuación diferencial puede ser escrita de la siguiente forma:
$$
y^n =G(x, y, y', y'', \dots, y^{(n-1)})
$$
**Solución de una Ecuación Diferencial Ordinaria**

Decimos que una función $$y=u(x)$$ es solución de una ecuación diferencial $$F(x, y, y', y'', \dots, y^{(n)}) = 0$$en un intervalo I cuando las derivadas $$u', u'', \dots, u^{n}$$existen en I y si   $$F(x, u, u', u'', \dots, u^{(n)}) = 0$$ para todo x del intervalo I.

## Soluciones explícitas e implícitas
Una solución donde la variable dependiente se expresa tan solo en términos del as variable independiente y constante se llama **solución explícita**
Una **solución implícita** es una función dada implícitamente la función **u** y de sete modo satisface la ecuación diferencial.

## Tipos de Soluciones de la Ecuación Diferencial

**Solución General**
Una ecuación diferencial de primer orden puede tener infinitas soluciones las que se representan mediante una fórmula que contiene una constante arbitraria y se denomina solución general. Una ecuación diferencial de un orden x tendrá una cantidad x de constantes arbitrarias.

**Solución particular:**
Una solución particular de la ecuación diferencial es cualquier solución que se obtenga dando valores específicos a la constante arbitraria en la solución general

**Solución Singular:**
Son soluciones de la ecuación diferencial que no se obtienen para ningun valor de la constante arbitraria, es decir no están contenidas en la solución general.

## Representación gráfica de las soluciones de una ecuación diferencial. Familia de Curvas

Geométricamente la solución representa una familia de curvas, conocidas como curvas de solución; y hay una para cada valor de la constante arbitraria. Es decir cada solución particular de una ecuación **diferencial de primer orden** tiene asociada una curva en el plano cartesiano y la solución general tendrá como representación gráfica una familia de curvas.

## Cuatro tipos especiales de ecuaciones ordinarias de primer orden

**Forma general de una ecuación diferencial ordinaria de primer orden y de primer grado:**
$$ F(x, y, y') = 0 $$
**Está en forma ímplicita**
Si es posible a partir de esta expresión despejar la variable $$y'$$ y dejarla en términos de la variable x, es decir: $$y'=f(x,y)$$ Decimos que la ecuación está en su **forma explícita**

La ecuación también puede expresarse en **forma diferencial** como $$M(x,y)dx+N(x,y)dy=0$$
## Ecuación diferencial de Variables Separables
Dada una ecuación diferencial es cualquiera de sus formas (implícita, explícita o diferencial), si es posible mediante pasos algebraicos expresarla como $$g(y)*{dy/dx}=f(x) \space ó \space g(y) = f(x)dx$$
donde f y g son funciones continuas en un cierto intervalo I, la ecuación se llama de **Variables Separables** o simplemente **Ecuación Separable**

### Teorema 1 
Sea $$y = Y(x)$$ una solución cualquiera de la ecuación diferencial separable $$g(y)*{dy/dx}=f(x)$$ tal que $$Y'$$ sea continua en un intervalo abierto I. Suponga que f y la función compuesta $$g(Y(x))$$ son ambas continuas en I. Sea G cualquier primitiva de g, esto es cualquier función que se cumpla que: $$G'=g$$ Entonces la solución Y satisface la formula implicita $$G(y) = \int{f(x)dx}+ C$$para un cierto valor de C.

*El teorema asegura que, bajo las condiciones dadas, las soluciones de la ecuación diferencial pueden ser representadas de manera implícita mediante integrales. Esto nos permite encontrar soluciones explícitas o analizar el comportamiento de las soluciones.*

**Demostración**
# 

Sea \( y = y(x) \) una solución cualquiera de la ecuación diferencial separable
$$
g(y) \frac{dy}{dx} = f(x)
$$
tal que \( y \) sea continua en un intervalo abierto \( I \). Suponga que hay una función compuesta \( g[Y(x)] \) tal que \( g' \) es continua en \( I \), y \( G \) es cualquier primitiva de \( g \), es decir, \( G' = g \). Entonces:

1. Cualquier solución \( y \) satisface la fórmula implícita
   $$
   G(y) = \int f(x) \, dx + C,
   $$
   para un cierto valor de \( C \).

2. Recíprocamente, si \( y \) satisface (b) entonces \( y \) es una solución de (a).

---

*Notas:*
- Aquí, \( f(x) \) y \( g(y) \) son funciones continuas.
- La continuidad de \( y \) en \( I \) asegura la validez de las operaciones de integración y diferenciación.

## Ecuaciones Diferenciales con Coeficientes Homogéneos de Igual Grado
**Funciones Homogéneas**
Una función $$f(x,y)$$ se dice que es homogéneas de grado k en x e y si y sólo si $$f(\lambda x, \lambda y) = \lambda^kf(x,y)$$ donde k es un número real.

**Teorema 1**:
Si $$M(x,y) \space y \space N(x,y)$$ son ambas homogéneas y del mismo grado, la función $${M(x,y)}/{N(x,y)}$$ es homogénea de grado cero.

**Demostración**
![[Pasted image 20250220203423.png]]

**Teorema 2**
Si f(x,y) es homogénea de grado cero en x e y entonces f(x,y) es una función de y/x solamente.

**Demostración:**
![[Pasted image 20250220203708.png]]

## Definición de ecuación diferencial con coeficientes homogéneos de igual grado

Una ecuación diferencial $$M(x,y)dx + N(x,y) dy = 0$$ se llama coeficientes homogéneos de igual grado, si las funciones M y N son ambas homogéneas de igual grado k en x e y.

**Teorema: Cambio de variables en ecuaciones con coeficientes homogéneos**
Si $$M(x,y)dx + N(x,y)dy = 0$$ es con coeficientes homogéneos, entonces se puede transformar en una ecuación diferencial cuyas variables son separables por la sustitución $$ y = vx $$ donde v es una función de x.

**Demostración**
![[Pasted image 20250220205019.png]]

## Ecuaciones Diferenciales Exactas

Dada una ecuación diferencial $$ M(x,y)dx + N(x,y)dy = 0$$ se dice que es exacta, si el primer miembro es la diferencial total o exacta $$dU =  {(\partial {U}\div \partial x) \space * dx} + {(\partial {U}\div \partial y) \space * dy} $$ de alguna función U(x,y), y donde U(x,y) = C es una solución general.

**Teorema, Criterio De Exactitud**

Supongamos que las funciones M y N son continuas y que tienen primeras derivadas de primer orden continuas en un rectángulo abierto R. $$ Tal \space que \space el \space rectángulo \space tenga \space las \space siguientes \space medidas \space a<x<b, \space c<y<d $$
Entonces la ecuación diferencial es exacta en R si se cumple que 
$$ {\partial M(x,y) \div  \partial y} = {\partial N(x,y) \div  \partial x}$$
Esto significará que exista una función U, que la derivada parcial respecto a x sea la función M y esa misma función U la derivada parcial respecto a Y será la función N.

**Condición Necesaría**
![[Pasted image 20250220210235.png]]
![[Pasted image 20250220210214.png]]

**Condición suficiente**
![[Pasted image 20250220210257.png]]

![[Pasted image 20250305033930.png]]

## Ecuaciones Diferenciales Reducibles a Exactas
Dada una ecuación diferencial en su forma $$M(x,y)dx + N(x,y)dy = 0$$
Si esta no es exacta, puede que se transforme en exacta por medio de un factor apropiado **H(x,y)**, el cual lo llamaremos **factor integrante** de la ecuación diferencial, si bajo ciertas condiciones esto es posible así llevando la ecuación diferencial a una exacta.

### Teorema de los Factores Integrantes
![[Pasted image 20250305034815.png]]
![[Pasted image 20250305035758.png]]

![[Pasted image 20250305040615.png]]

# Unidad 23


[[Unidad 22]]

# Ecuación Diferencial Lineal de Primer Orden

Se dice que una ecuación diferencial ordinaria de primer orden es lineal si se puede escribir de la forma.
$$ \frac{dy}{dx} + p(x)*y = q(x) $$
Donde $$p(x) \space y \space q(x)$$
son funciones continuas de x.

- Si q(x) = 0, la ecuación ordinaria lineal de primer orden se denomina homogénea.
- Si q(x) es distinto de 0, la ecuación ordinaria lineal de primer orden se llama no homogénea

## Solución General de la Ecuación No Homogénea
![[Pasted image 20250306035006.png]]

Esta expresión representa la solución general de la ecuación homogénea.
En el caso de que no sea homogénea, entonces tendremos que encontrar una solución general para esto:

![[Pasted image 20250306040413.png]]

# Ecuación Diferencial de Bernoulli
Una ecuación diferencial de Bernoulli tiene la siguiente forma
$$ \frac{dy}{dx} + p(x)*y = q(x)*y^n 
$$
Donde: 
$$n \in R, \space n \neq 0\space y \space n \neq 1 $$

Si leemos esta ecuación es lineal y de variables separables si n es igual a 1, por lo tanto se supone que n será distinto de 0 y de 1.

## Solución de la Ecuación de Bernoulli
![[Pasted image 20250306041753.png]]

# Familia de Curvas y Trayectorias Ortogonales

Dada una ecuación $$F(x,y,C) = 0$$ que representa una familia uniparametrica donde C es el parámetro, queremos encontrar una segunda familia $$G(x,y,C) = 0$$ con la propiedad de que cada elemento de esta familia corte ortogonalmente a cada miembro de la otra familia.
La familia F y G se llamarán trayectorias ortogonales una respecto a la otra.

## Procedimiento para encontrar las Trayectorias Ortogonales
![[Pasted image 20250306042439.png]]
