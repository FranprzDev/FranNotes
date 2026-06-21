Utilizamos las distribuciones de probabilidad ya que en ellas todo está demostrado. Si no podemos ir a una básica tenemos que recurrir a distribuciones empíricas.
En este caso, se ven 3 continuas y 2 discretas.

## Distribución Uniforme
Se caracteriza por ser constante en el intervalo (a,b) y afuera de él ser cero.
Matemáticamente lo podemos expresar como
$$
f(x) =
\begin{cases}
\frac{1}{b - a}, & \text{si } a < x < b \\
0, & \text{fuera del } (a,b)
\end{cases}
$$
Básicamente para obtener el valor utilizando una distribución de probabilidad de utilizaremos la siguiente formula:
$$
x = a + (b-a) * u
$$

Donde u es la variable aleatoria, y (a,b) son los límites del intervalo.
## Distribución Exponencial
Cuando utilizamos una variable aleatoria con dist. exponencial indicamos **"Cuánto continuo hasta el primer éxito**. Es como en PyE, si definimos que el "éxito" es básicamente que pase un **auto de color rojo**, podemos contar en un peaje cuantos autos pasan hasta eso. Esta variable cuenta cuanto tiempo pas desde que empieza el experimento hasta que pase el primer éxito, desde el lado de la observación.
Para los valores de las vars aleatorias del tipo exponencial se deben satisfacer las siguientes suposiciones:
1. La probabilidad de que ocurra un evento en le intervalo $\ [t, (t + \delta t)\ ]$   es $\delta t$  
2. $\delta$ es una constante que no depende de t, ni de ningún otro factor (independiente)
3. La probabilidad de que durante el intervalo ocurra más de un evento, tiende a 0 a medida que $\delta t$ tiende a 0

Esto se da en muchas cosas, como por ejemplo que lleguen pedidos a una compañía, se registren pacientes o que un transitor sobreviva 800hs si ya tiene 700hs que lo mismo que sobreviva sus primeras 100hs. Por lo tanto, un transitor nuevo no es mejor que uno que ya trabajó 700hs

Se dice que una var. aleatoria X tiene una dist exponencial, si se puede definir una fdp como:
$$
f(x) = \alpha e^(-\alpha x)
$$
Siendo:
- $\alpha \ > 0$ 
- $x >= 0$

La dist exp es una func de un único parámetro $\alpha$ donde este es cualquier constante positiva. Concretamente este alpha es el mismo parámetro que el de la distri de Poission; y se define como **"Cantidad de eventos por continuo"**
Ej: Si se considera llegada de clientes -> 5 Clientes por hora -> $\alpha = 5 \ Clientes \ por \ Hora$ 

Y podemos decir que el valor esperado para la variable aleatoria resulta ser:

$$
E(X) = \frac{1}{\alpha}
$$
Por lo tanto esto cumple a la siguiente formulita:

$$
x = - EX * ln (u)
$$

## Distribución Normal
Es las más utilizada de todas generalmente en la vida cotidiana
¿xd?
