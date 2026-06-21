## Modelo de inventario de periodo único con demanda probabilística

Todos los modelos anteriores se basaron en el supuesto que la tasa de demanda es constante y **determinística** durante todo el año. Pero existen situaciones donde la tasa de demanda no es determinística y se trata como **probabilística**, es decir que está descripta mejor por una distribución de probabilidad; por esto tenemos este tipo de modelo.

Este se da en situaciones en las que se coloca un pedido del producto, al final del periodo; el producto **se vendió en su totalidad** o el excedente de artículos no vendidos se venderá a un **"valor de rescate"**
Se aplica en situaciones que implican artículos de temporada o percedereos que no pueden ser conservados en el inventario y vendidos en el futuro. Ejemplo la ropa de temporada, la leche, etc. se maneja con este tipo de periodo. 
El comprador hace un pedido antes de la temporada de cada artículo y experimenta un agotamiento de existencias o realiza una liquidación del excedente al final de temporada, ningún artículo se conserva y se vende al año siguiente.
Los periódicos también, osea si no vendes un periódico del día, nadie te lo querrá comprar mañana, por que ya es otro.
Es obvio, que si la demanda no sería random; sería mucho más fácil, pero no; cada periodo distinto y puede tener distinta demanda. Para poder llevarlo al entendimiento, analizaremos el problema de inventario de manera cuantitativa, mediante la información sobre las probabilidades asociadas con los valores de la demanda. Por esto es de **demanda probabilística**.

La primera pregunta para poder empezar es **¿Cuáles son los posibles valores de la demanda del producto X?** Probablemente esta pregunta sea respueta por medio de una distribución de probabilidad específica, en el ejemplo del libro estamos hablando de una **distribución de probabilidad uniforme** como la siguiente
![[Pasted image 20260502220927.png]]
(Es una compañía de zapatos y el contexto es que se compran zapatos para una temporada y se los vende a un precio x, si sobran a un precio mas barato y)

Como se ve en la imagen, la demanda variaría entre 350 y 650 siendo la demanda esperada promedio de 500 unidades.
El **análisis adicional** es un método que puede utilizarse para determinar la cantidad óptima de pedido con un modelo de inventario de periodo único. El ánalisis aborda la pregunta de cuánto ordenar comparando el costo o pérdida de ordenar de más o ordenar de menos, implicando los siguientes costos:
- $c_0$ Es el costo por unidad por **sobreestimar** la demanda. Este costo representa la pérdida de ordenar una unidad adicional y de ver que no se puede vender.
- $c_u$ Es el costo por unidad por **subestimar** la demanda. Representa la pérdida de la oportunidad de no ordenar una unidad adicional y de ver si pudo haber sido vendida.

### Distribución de probabilidad Uniforme para el caso de Johnson Shoe Company
Dado los datos para la empresa **Johnson Shoe Company**

Los zapatos cuestan $40 el par y se venden a $60 el par en temporada, cuando pase la temporada se venderá a $30 el par excedente.

En este caso procederemos a calcular los costos por unidad de sobreestimar la demanda dado por:
$$
c_0 = $40-$30 = $10
$$
(Pierdo $10 dolarukos si los vendo fuera de temporada)
El costo por subestimar la demanda será de:
$$
c_u = $60 - $40 = $20
$$
(Pierdo $20 dolarukos por cada unidad que no vendí dentro de la temporada)

Entonces al igual que EOQ, la idea es obtener el óptimo para $Q^*$, por lo tanto buscaremos esto con los valores que tenemos. _La lógica para demostrarla la dejo en el libro, es bastante xd_
Pero básicamente llegamos a la siguiente formula que nos indica cual sería la óptima:
$$
P(demanda \leq  Q^*)= \frac{c_u}{c_u+c_o}
$$
Si reemplazamos con los valores que tenemos disponibles $c_0 = 10$ y $c_u = 20$, el resultado de la ecuación es $\frac{2}{3}$

Es bastante compliquete el PORQUE pero básicamente dependiendo del tipo de distribución de probabilidades que tengamos vamos a obtener de distintas maneras el $Q^*$, por lo tanto tenemos la de este ejemplo (Uniforme) pero podemos tener otras.
En el caso de la distribución de probabilidad uniforme, se da de la siguiente forma,
- Para obtener realmente el valor de $Q^*$ lo que hacemos es encontrar el área bajo la **curva de densididad de probabilidad acumulada hasta ese punto, es decir la CDF**; igualada a la fracción critica demostrada más arriba.
Bajo este concepto entonces:
Siendo $a=350$ y $b=650$ la CDF para una distribución uniforme continua sería:

$$
f(D) = \frac{1}{b-a} = \frac{1}{300}
$$
Si procedemos a derivar esa $f(D)$ para obtener la CDF:
$$
F(Q)= \int_{350}^Q\frac{1}{300}dD
$$
Esto cuando lo resolves sale como:
 $$
 F(Q) = \frac{Q^*-350}{300}
$$
Por lo tanto, lo que tenemos que hacer es igualar ese valor a la fracción crítica y así obtendremos el $Q^*$ 
$$
\frac{Q^*-350}{300} = \frac{2}{3}
$$
Si resolvemos esto nos queda:
$$
Q^* = \frac{2*300}{3}+350 = 200+350=550
$$

Por lo tanto el $Q^* = 550$ y esta es la cantidad óptima de pedido, que serían 550 pares de zapatos

_Ojo, lo que hace el villero del libro es básicamente decir bueno entre 650 y 350 que son los límites hay una diferencia de 300, si la fracción crítica son 2/3, y decimos que cada tercio son 100 pasitos entonces 2 * 100 son 200 y le sumo al mínimo y esa es la cantidad. Pero no entiendo bajo que lógica lo hace, por eso hice el desarrollo. Pero como dije todo depende de la CDF de la distribución de probabilidad sobre la cual estamos trabajando._ 

### Distribución de probabilidad Normal para el caso de Nationwide Car Rental
Distribución normal con una media de 150 automóviles y una desviación estándar de 14.

El costo de un excedente, es el costo de sobreestimar la demanda $c_0$ y es de $80 por automóvil. El faltante da un costo de subestimación de $200$ es decir $c_u = \$200$ 
Realizamos el cálculo de la fracción crítica.
$$
P(demanda \leq Q^*) = \frac{c_u}{c_u+c_0} = \frac{200}{200+80}=0.7143
$$
Esta es la distribución de probabilidad que utilizaremos (la figura asociada)
![[Pasted image 20260502224407.png]]

Con este valor de $0.7143$ vamos a la tabla de la distribución normal a buscar.
_SI NO TE ACORDAS UN PINGO AL IGUAL QUE YO TE EXPLICO COMO SE USA:

EL VALOR CRÍTICO TENES QUE BUSCARLO EN ALGÚN LADO, LA TABLA TIENE LA DISTRUBUCIÓN DE PROBABILIDAD ACUMULADA, ENTONCES TENES QUE BUSCARLO? ¿Cómo? A pelo y a ojo creo no me aceurdo nada.
Lo importante es que encuentren el valor 0.7143 en algun lado o el más cercano, en este caso en la normal fijense es el 0.57
![[Pasted image 20260502225428.png]]
Entonces utilizamos una formulita falopa que vaya  a saber dios de donde sale:

$$
Q^* = \mu + 0.57\sigma
$$
Donde:
- $\mu$ es la demanda media, igual a 150.
- $0.57$ es la probabilidad encontrada en la normal. (o eso creo)
- $\sigma$ es la desviación estándar

Entonces procedemos a los cálculos:
$$
Q^* = 150 + 0.57*14 = 158
$$

Por lo tanto, la empresa deberá planear tener 158 automóviles disponibles para el fin de semana del día del trabajador.

-----------------------------
En este caso, es mejor:
- Nationwide calcula que el costo de **sobrar autos** es menor que el costo de **quedarse corto**.
- Por eso, el modelo les sugiere arriesgarse a **sobreestimar la demanda** (probabilidad 0.7143 de excedente).
- Y aceptar una menor probabilidad de **subestimar** (0.2857 de quedarse sin autos).

Para mógolicos:
👉 Sobreestimar = pedir de más, sobran autos.  
👉 Subestimar = pedir de menos, faltan autos.



## Cantidad de pedido, modelo de punto de reorden con demanda probabilística
Ahora ampliamos el análisis a un modelo de inventario de punto de reorden, con cantidad de pedido multiperiodo con demanda probabilística.
En este modelo, el sist. de inventario opera de forma continua con muchos periodos repetitivos o ciclos; el inventario puede ser conservado de un periodo al siguiente. 
Siempre que se alcanza el punto de reorden, se vuelve a pedir una cantidad **Q de unidades**; El patrón de este, será el siguiente:
![[Pasted image 20260502230116.png]]

Los incrementos ocurren siempre que llega un pedido nuevo de **Q unidades**. El inventario se va reduciendo a una tasa constante basada en la demanda probabilística, y se coloca un nuevo pedido cada vez que se llega al **punto de reorden**. Como en otros modelos se debe determinar la cantidad de pedido **Q** y el punto de reorden del sistema de inventario.
LAS MATES LES CHUPA 3 PINGOS AL PANA ANDERSON (PRIMEE)

### Dabco Industrial Lighthing Distributors
- $K = \$12$ 
- El precio unitario de cada foco es de $6
- Costo de retención anual de 20%.

Por lo tanto: $h = IC = 0.2 * \$6 = \$1.2$
El tiempo de espera es de una semana (7 días)

La  demanda se puede describir bajo una distribución de probabilidad **NORMAL** con una media de 154 focos y una desviación estándar de 25. De la siguiente forma:
![[Pasted image 20260502230559.png]]
Teniendo en cuenta el EOQ clásico podemos tomar la formulaque nos aporta, y podemos calcular la demanda anual esperada con los datos proporcionados.
$Demanda \space anual \space esperada = 154 * 52 = 8008$ unidades por año 
Utilizando la formula de la cantidad óptima
$$
Q^* = \sqrt{\frac{2*8008*12}{1.20}} = 400 \space unidades
$$
Si obtenemos cuantos pedidos deberíamos hacer sería $\frac{D}{Q}$ que sería $\frac{8008}{400} = 20$ que serían la cantidad de pedidos por año con un promedio de 12.5 días hábiles entre pedidos.

Pero aquí la pregunta sería, **cuándo ordenamos?**
Podemos determinar la probabilidad de que se agoten las existencias por medio de la distirbución de la demanda durante el tiempo de espera para calcular la probabilidad de que la demanda excederá r.
Para esto abordaremos el problema, definiendo un **costo por agotamiento de existencias** e incluyendolo en la ecuación del costo total. También podemos incluir una especificación del número de agotamientos de existencias promedio que puede ser tolerado por año. En este caso, diremos que la gerencía permitirá solamente que la demanda sea mayor a r un 5% de las veces. (Como se ve en la gráfica)
![[Pasted image 20260502231651.png]]
Esta decisión hace que no incluyamos en puntos altos de reorden, un inventario muy grande o altos costos de retención, por eso es algo que define la gerencia según que tanto les convenga.

En este caso, como buscamos al revés del ejercicio anterior, buscamos el 5% ese de la derecha, entonces buscamos el valor mas parecido a $\frac{95\%}{100} = 0.95$ en la tabla, donde estan computados todos los valores, en este caso es 1.65 (en el libro aparece como 1.645 por que es una diferencia con la tabla que se toma o algo así)

![[Pasted image 20260502232441.png]]

Con este valor procedemos a utilizar la formulita:
$$
r = 154 + 1.65(25) = 195
$$

Por lo tanto, el punto de reorden (osea volveremos a pedir cuando tengamos) 195 unidades.

En general, ordenaremos 400 unidades siempre que el inventario descienda a 195 unidades.

Con los datos de la distribución de probabilidad sabemos que la demanda promedio es de 154 unidades por lo tanto, si restamos el punto de orden menos la demanda promedio $195-154=41$ obtendremos lo que se conoce como la **existencia de seguridad** que en este caso son 41 unidades.
Y esta es la que está destinada a absorber la demanda más alta que la usual en el 95% del tiempo de espera. 

Por lo tanto el costo anual anticipado del sistema es el siguiente.

$$
Costo \space de \space retención = (\frac{Q}{2})h = (\frac{400}{2})1.20 = $240
$$
$$
Costo \space de \space retención = Existencia \space de \space seguridad * h = 41*1.2 = \$49
$$
$$
Costo \space de \space ordenar = \frac{D}{Q}K=\frac{8008}{400}*12= \$240
$$

Por lo tanto si sumamos todos los costos el TC sería de $\$529$ 
En este caso, para esta empresa basamos en 5% la probabilidad de un agotamiento de existencias durante el tiempo de espera; por lo tanto en el 95% de todos los ciclos de pedido, la empresa será capaz de satisfacer la demanda de los clientes sin que se agoten las existencias, si definimos el nivel de servicio como el porcentaje de todos los ciclos de pedidos que no experimentan agotamiento de existencias; podemos decir que **Dabco tiene un nivel de servicio de 95%**. Por lo tanto, puede haber diferencias en quien te hable sobre el nivel del servicio.

## Modelo de revisión periódica con demanda probabilística
Los modelos previamente analizados requieren un **sistema de inventario de revisión continua**. Es decir, la posición del inventario se monitorea de forma continua, los sist. de inventarios por computadora proporcionan está facilidad, pero podemos encontrar una alternativa mediante el **sistema de inventario de revisión periódica**.
Con este tipo, el inventario se revisa y vuelve a ordenar sólo en puntos especificados en el tiempo. Por ejemplo, el inventario puede ser revisado y los pedidos hechos cada semana, cada dos semanas y cada mes; o con alguna periodicidad.
Esto sirve cuando una empresa trabaja con varios artículos, de modo que múltiples artículos se pueden pedir en la misma fecha, con los anteriormente revisados para distintos productos serán en distintos momentos haciendo que sea difícil la coordinación de múltiples pedidos.

### Empresa: Dollar Discounts
Varias tiendas minoristas de productos de uso doméstico, su revisión periódica es cada 2 semanas; los pedidos de todos los productos se combinan en un solo envío
Cuando se decide la cantidad a ordenar de cada producto, no se vuelve a ordenar hasta el próximo periodo.
Entonces la ecuación será la siguiente para cualquier periodo:
$$
Q = M - H
$$
Donde:
- Q = cantidad de pedido
- M = nivel de reemplazo
- H = inventario disponible en el periodo de revisión

Como la demanda es probabilística el inventario disponible en el periodo de revisión H variará, por lo tanto la cantidad del pedido debe ser suficeinte para regresar a la posición del inventario a su máximo nivel de reposición M.
El ejemplo fácil es $H = 12$ y $M = 50$ entonces $Q = M - H$ > $Q = 50 - 12 = 38$ Por lo tanto hay que pedir 38 unidades. Aquí tenemos el patrón de este.
![[Pasted image 20260503020029.png]]


Para poder determinar una ecuación del costo total, el objetivo es determinar un nivel de reposición que satisfaga un nivel de desempeño de existencias o un número bajo de agotamientos de existencias por año.
Por ejemplo, en este caso supongamos el nivel de reposición del 1% de probabilidad de agotamiento de existencias.

Por lo tanto en este modelo, el Q debe ser suficiente para satisfacer la demanda durante el periodo de revisión más la demanda durante el siguiente tiempo de espera para llegar a un nuevo nivel cercano a M. La duración del tiempo es igual al periodo de revisión más el tiempo de espera.
Supongamos la siguiente distribución de probabilidad para este caso.
![[Pasted image 20260503020301.png]]
Supongamos que también definimos el 1% de agostamiento de existencias permitido.
![[Pasted image 20260503020316.png]]
Buscamos el 0.9900 (o el más cercano) en la tabla de la normal y nos dará que z = 2.33
Por lo tanto aplicamos la formulita.
$$
M = \mu + z\sigma
$$

$$
M = 250 + 2.33*45 = 355
$$
Si queremos saber el stock de seguridad bastará con restar al valor de M la media, es decir $355-250 = 105$  y esta es la existencia de seguridad para absorber cualquier demanda más alta de lo usual durante el periodo de revisión más la demanda durante el tiempo de espera.

-------------
Segun el libro existen otros modelos de revisión más complejos, pero no serán tomados en cuenta, al menos no en el libro de Anderson.

## Glosario Adicional (Servirá para los videos)
- **Cantidad económica del pedido (EOQ):** La cantidad de pedido que reduce al mínimo el 
	costo de retención anual más el costo anual de ordenar. 
- **Tasa de demanda constante:** Un supuesto de muchos modelos de inventario que estable
	ce que el mismo número de unidades se toma del inventario cada lapso de tiempo. 
- **Costo de retención:** Costo asociado con el mantenimiento de una inversión de inventario, 
	incluidos el costo de la inversión de capital en el inventario, seguros, impuestos, gastos 
	generales de almacenamiento, etc. Este costo puede establecerse como un porcentaje de la 
	inversión en el inventario o como un costo por unidad. 
- **Costo de capital:** Costo en que incurre una empresa para obtener capital para una inver
	sión. Puede formularse como una tasa porcentual anual, y es parte del costo de retención 
	asociado con el mantenimiento del inventario. 
- **Costo de ordenar:** Costos fijos (salarios, papel, transporte, etc.) asociados con la coloca
	ción del pedido de un artículo. 
- **Posición del inventario:** Inventario disponible más el inventario solicitado. 
- **Punto de reordenar (o punto de reorden):** Posición del inventario en la cual se deberá 
	hacer un nuevo pedido. 
- **Tiempo de espera:** Tiempo entre la colocación de un pedido y su recepción en el sistema 
	de inventario. 
- **Demanda durante el tiempo de espera:** Número de unidades demandadas durante el 
	tiempo de espera. 
- **Tiempo de ciclo:** Lapso de tiempo entre la colocación de dos pedidos consecutivos. 
- **Tasa de demanda constante:** Una situación en la cual el inventario se incrementa a una 
	tasa constante durante un periodo de tiempo.
- **Tamaño de lote:** Cantidad de pedido en el modelo de inventario de producción. 
- **Costo de preparación:** El costo fijo (mano de obra, materiales, producción perdida) aso
	ciado con la preparación de una nueva fase de producción. 
- **Falta de existencias** Demanda que no puede ser surtida con el inventario. 
- **Pedido en espera:** Recibo del pedido de un producto cuando no hay unidades en el inven
	tario. Estos pedidos en espera se convierten en faltantes, lo que con el tiempo se satisface 
	cuando un nuevo abasto del producto está disponible. 
- **Costo de plusvalía:** Costo asociado con un pedido en espera, una venta perdida o cualquier 
	forma de agotamiento de existencias o demanda no satisfecha. Este costo puede usarse 
	para refl ejar la perdida de utilidades futuras, porque la demanda de un cliente no fue satis
	fecha.
- **Descuentos por cantidad:** Descuentos o bajos costos ofrecidos por el fabricante cuando 
	un cliente adquiere grandes cantidades del producto. 
- **Modelo de inventario determinístico:** Modelo donde la demanda se considera conocida 
	y no sujeta a incertidumbre. 
- **Modelo de inventario probabilístico:** Modelo donde la demanda no se conoce con exac
	titud; las probabilidades se asocian con los posibles valores de la demanda. 
- **Modelo de inventario de periodo único:** Modelo de inventario en el cual sólo se hace un 
	pedido del producto, y al fi nal del periodo el producto se vendió en su totalidad o quedó 
	un excedente de productos no vendidos que se venderá a un precio de rescate. 
- **Análisis adicional:** Método utilizado para determinar una cantidad óptima de pedido, al 
	comparar el costo de ordenar una unidad adicional con el costo de no hacerlo. 
- **Distribución de la demanda durante el tiempo de espera:** Distribución de la demanda 
	que ocurre durante el tiempo de espera. 
- **Existencia de seguridad:** Inventario mantenido para reducir el número de agotamientos de 
	existencias, ocasionado por una demanda mayor que la esperada. 
- **Sistema de inventario de revisión continua:** Sistema en el cual la posición del inventario 
	se vigila o revisa de forma continua, de modo que pueda colocarse un nuevo pedido en 
	cuanto se llega al punto de volver a ordenar. 
- **Sistema de inventario de revisión periódica:** Sistema en el cual la posición del inventario 
	se revisa o vuelve a revisar en puntos en el tiempo periódicos predeterminados. Pedidos de 
	reabastecimiento se colocan sólo en puntos de revisión periódicos.