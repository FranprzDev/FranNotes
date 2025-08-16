## Expresiones Regulares
Es una forma algebraica que se define sobre un alfabeto base $\Sigma$ y un alfabeto especial $\Sigma' = {+,*,.,\Phi, \lambda,(,)}$ con $\Sigma$ y $\Sigma'$ disjuntos mediante las siguientes clausulas.

1) $\Phi, \lambda, x \in \Sigma \space son \space ER$ 
2) Si $E_1 \space y \space E_2$ son ER, entonces $E_1+E_2 \space y \space E_1.E_2$ también son ER.
3) Si E es una ER entonces $E*$ Y (E) también son ER
4) Toda ER se puede definir mediante las cláusulas 1, 2 y 3

Los simbolos actúan como operadores; en ese orden de prioridad.
Obviamente existe una relación entre ER y LR

En general las ER se asocian con los LR, las GR y los AF, y tienen distintas aplicaciones por ejemplo:
1) Para describir patrones textuales
	1) Búsquedas por Regex
	2) Datos de prueba random
	3) Criterios de Busqueda para DB
	4) grep, findstr o awk en gnu/linux
2) Para formalización de diagramas.
3) Para describir el léxico de un lenguaje de programación

## Propiedades de las ER

1) $\Phi* = \lambda$ 
2) $E.E*=E*.E$
3) $E*=\lambda+E.E*$
4) $(E_1^*.E_2^*)* = (E_1+E_2)*=(E_1^*.E_2^*)^*.E_1^*$
5) $E* = (\lambda+E+E^2+E^3+...E^N-1).(E^N)^*$

## Sistemas de Ecuaciones Características de una GR

Dada una GR por derecha, se pueden obtener un conjunto de definiciones regulares de la forma $X = R + T.X$ donde $X \in \Sigma_N$ y (R,T) son ER sobre el alfabeto Sigma de la Gramática Regular.
Para resolver debemos:
1) Agrupar todas las reglas que tengan igual parte izquierda
2) Igualar cada no-terminal X con la unión de todas las partes derechas correspondientes, usando el conectivo **"+"**
3) Sustituir la yuxtaposición de símbolos con la concatenación del mismo usando el conectivo **"."**

La yuxtaposición es la acción de colocar dos o más elementos uno al lado del otro.
Lo más fácil para entenderlo es un ejemplo:

$G = <\Sigma_N, \Sigma_T, P, S>$
$\Sigma_N={\{S,A,B,C\}}$ 
$\Sigma_T=\{a,b,c\}$
$P: S \rightarrow aA | bB | cC$
$A \rightarrow bA | aB$
$B \rightarrow cB | a$
$C \rightarrow cC | c$

Entonces vamos a hacer los pasos para obtener el sist de ecuaciones caracteristicas, como no hay reglas iguales; no agrupamos nada si no que pasamos al paso 2; remplazamos los | por +
$P: S \rightarrow aA + bB + cC$
$A \rightarrow bA + aB$
$B \rightarrow cB + a$
$C \rightarrow cC + c$

Una vez hicimos esto, entonces lo siguiente es agregar el operador concatenación; es decir, si no están juntos entonces lo hacemos que esten juntos.

$P: S \rightarrow a.A + b.B + c.C$
$A \rightarrow b.A + a.B$
$B \rightarrow c.B + a$
$C \rightarrow c.C + c$

**Es obvio, que tiene que ser una gramática regular en fnc3 para que sea posible hacerlo**

## Solución de la Ecuación genérica
Se realizan un par de pasos para deducir la solución; que cumpla con la igualdad que tomaremos como base.
$$ X = R + T.X$$
1) Sabiendo que X es un no-terminal y que R y T son expresiones regulares, entonces aplicamos a T la operación estrella de kleene (el asterisco)
$$ T* = \lambda + T.T*$$
2) Si ahora hacemos una postconcatenación es decir "multiplicamos ambos miembros"
$$T*.R=(\lambda+T.T*).R$$
3) Por la propiedad distributiva podemos escribir el segundo miembro como:
$$T*.R=(\lambda.R+T.T*.R)$$
4) Por culpa de que $\lambda$ no hace nada en la concatenación podemos reescribir como:
$$T*.R=R+T.T*.R$$
5) Ahora revisamos a lo que queríamos llegar $X=R+T.X$ y lo comparamos.
6) La diferencia es clara $T*.R$ es igual a $X$ , entonces lo remplazamos.
7) $$T*.R=x \space \rightarrow X =R+TX$$
8) Entonces quedó demostrado lo que se conoce como el Lema de Arden.

## Obtención de la ER del lenguaje generado por una GR.
1) Se plantea el sistema de ecuaciones características
2) Se resuelve el sistema mediante
	1) Método de sustitución
	2) Solución de la ecuación genérica (lema de arden)
3) La ER del lenguaje generado por la GR es la solución correspondiente al axioma de la gramática.

## Ejemplo
$P: S \rightarrow a.A + b.B + c.C$
$A \rightarrow b.A + a.B$
$B \rightarrow c.B + a$
$C \rightarrow c.C + c$

Entonces si pasamos a las ecuaciones características
$C = c*.c$ 
$B=c*.a$ 
$A=b*.a.c*.a$
$S = a.b*.a.c*.a+b.c*.a+c.c*.c$
