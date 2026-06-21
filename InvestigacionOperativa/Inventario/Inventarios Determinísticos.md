# Modelo de Inventarios
El inventario son las mercancías o materiales que tenemos en reservas para una organización para utilizar en el futuro. Sean cualquiera los articulos contenidos. Las razones porque mantener en el inventario son simples; pues es dificil saber la precisión de la demanda y las necesidades de uso. Y el inventario sirve como reserva en caso de que estos materiales sean requeridos. En definitiva, utilizar inventarios respondemos a dos preguntas importantes.
- **¿Qué tanto debe ordenarse cuando se renueva el inventario?** *Cuánto*
- **¿Cuándo se debe renovar el inventario?** *Cuándo*

Para esto existen distintos modelos, que intentan predecir esto. En este caso el primero que se ve es:

## Modelo de Cantidad Económica del Pedido (EOQ)

Es pertinente cuando la **demanda de un artículo** muestra una tasa **constante** o **casi constante** (es decir no cambia con el tiempo); y cuando la cantidad solicitada llega al inventario en un momento dado. 
Lo más fácil para entender esto, es sacar el gráfico del libro.
![[Pasted image 20260502190542.png]]
Es cierto que la cantidad demandada cambia semana a semana, pero es tan infimo el cambio que podríamos decir que es constante.

La decisión de **cuánto** ordenar implica seleccionar una cantidad que constituya un compromiso entre 
1) Mantener inventarios pequeños y ordenar con freucencia
2) Mantener inventarios grandes y ordenar de vez en cuando.

La primera alternativa es un golazo, por que ordeno mucho y los voy acomodadno a medida que se me acaba, pero produce costos de pedidos altos y la segunda es también un golazo, pero el costo de retención (tener los artículos) te termina matando. En definitiva, saber **cuánto** se basa en maximizar esto.
Para esto utilizamos la matemática, como el costo total como la suma de costos de retención y el costo de ordenar.

**Los costos de retención** son los costos asociados con el mantenimiento del inventairo en un nivel determinado, los costos dependen del tamaño del inventario. El primer costo viene de financiar la inversión del inventario, es decir poner la plata en comprar inventario en vez de invertir en algo más.
El siguiente a determinar es el **costo de ordenar** es un costo considerado fijo, que sin importar la cantidad solicitada siempre está presente.

El costo de **retención**, el costo **de ordenar**, y la información sobre la **demanda** son los tres datos indispensables para el modelo EOQ.
 Por esto definimos la variable **Q** como la cantidad a ordenada, entonces buscamos hacer que el valor de Q reduzca al mínimo la suma de los costos de retención y pedido.
Algo lógico, son las gráficas, en este caso está ejemplificado pero da igual que sea siempre en un EOQ clásico será de la siguiente forma.
![[Pasted image 20260502191127.png]]
Q es la cantidad que ordenaremos, la mitad de esto, es el inventario promedio $\frac{1}{2}Q$  y esto bajo la variable independiente T.

También, si lo ponemos esto a medida que avanza el tiempo obtenemos un gráfico como el siguiente.
![[Pasted image 20260502191235.png]]

Generalmente los costos de retención se expresan en porcentajes anuales, y se basan en desarrollos anuales; por lo tanto el costo anual de mantener una unidad en el inventario está dado por:
$$
C_h = IC
$$
Donde:
- $I$ tasa de costo de retención anual
- $C$ costo unitario del artículo en el inventario
- $C_h$ = costo anual de mantener una unidad en el inventario.

La ecuación general del costo de retención anual de un inventario promedio $\frac{1}{2}Q$ es de:

$$
Costo \space de \space Retención \space anual = \space (Inventario \space anual) (Costo \space de \space retención \space anual \space por \space unidad)
$$

Que si lo ponemos en números sería:
$$
Costo \space de \space Retención \space anual = \frac{1}{2}QC_h
$$

Para completar el modelo de lo que hablamos, tenemos que agregar el costo de ordenar, para esto tenemos que saber cuántos pedidos haremos en el año; para calcular esto es simplemente D/Q  pedidos por año, si llamamos $C_0$ el costo de colocar un pedido (Llamado en la materia como K) entonces la formula nos queda:
$$
Costo \space anual \space de \space ordenar = (Número \space de \space pedidso \space por \space años) (Costo \space por \space pedido)
$$
Que traducido a variables sería:
$$
Costo \space anual \space de \space ordenar = \frac{D}{Q}C_0 
$$

Donde $C_0$ puede ser traducido como K


Por lo tanto, si hacemos el costo anual total, denotado por la bibliografía como TC sería:

$$
TC = \frac{1}{2}QC_h+\frac{D}{Q}C_0
$$
Que si lo pasamos a las variables que usamos:

$$
TC = \frac{1}{2}Q*h+\frac{D}{Q}K
$$
Esto es genial, por que nos da todo , pero es impractico, si lo derivamos respecto a Q obtendriamos $Q^*$ que podríamos llamarlo "Q óptimo" o "La cantidad óptima" y nos daría la siguiente formula:

$$
Q^* = \sqrt{\frac{2DC_0}{C_h}}
$$

Que si lo pasamos a nuestras variables sería
$$
Q^* = \sqrt{\frac{2DK}{h}}
$$

**Que sería la formula que utilizamos siempre**
El resultado de poner los valores en dicha fórmulas responde al a pregunta de **cuánto**
Ahora nos queda solamente saber **¿Cuándo?**

Para esto se introduce el concepto de **posición del inventario** es la cantidad de inventario disponible más la cantidad de inventario pedida; La decisión de ordenar se expresa en función de un **punto de reorden**, es la posición del inventario donde se debe colocar el pedido.
Pero también tenemos que tener en cuenta, que si pedimos algo tiene una especie de **tiempo de espera**, obviamente por que no llega al toque. Si bien es cierto que para este tipo de modelo (EOQ clásico) donde se tienen las premisas que la tasa de demanda es constante y existe un tiempo de espera fijo, el punto de reorden es el mismo que la demanda de tiempo de espera, por lo tanto la expresión sería:
$$
r = dm
$$
Donde:
- $r$ punto de orden
- $d$ demanda por día
- $m$ tiempo de espera de un pedido nuevo en días

Con esto podemos responder a la pregunta de qué tan frecuentemente colocamos un nuevo pedido; y lo conocemos como el **tiempo de ciclo**; previamente definimos $\frac{D}{Q}$ como el número de pedidos que colocaremos en el año; por lo tanto podemos calcular el tiempo de ciclo como:

$$
T = \frac{250*Q^*}{D}
$$
Sabiendo que Q* es la cantidad óptima (calculada previamente) y D es la demanda también calculada o dada como dato y el "250" corresponde a la cantidad de días hábiles, **OJO** puede ser 365 en vez de 250.


### Análisis de sensibilidad del EOQ

Por un análisis precedente a medida que cambie el valor de las variables (esto es la sensibilidad) el modelo EOQ es insensible a las pequeñas variaciones o errores en las setimaciones de costos. Esta insensibilidad es una propiedad de los modelos EOQ, eso significa que si tenemos casos razonables de los costos; es de esperar que obtengamos una aproximación buena a la cantidad de pedido que nos da el costo minimo.

### Supuesto s sobre el Modelo EOQ
![[Pasted image 20260502192757.png]]


## Modelo de tamaño del lote de producción económico
Este modelo es parecido ciertamente al EOQ, y también suponemos que la demanda es constante; pero en vez de suponer que en el pedido llega un envío de tamaño Q*, como en el modelo EOQ; suponemos que se suministran unidades al inventario a una tasa constante durante un periodo.
El supuesto de **tasa de suministro constante** implica que el mismo número de unidades se suministra en el inventario durante periodo dado, (10 x día x ej)
El **tamaño del lote** es el número de unidades en un pedido.
Pues bajo esta idea, es básicamente lo mismo que el EOQ pero ahora tenemos producción, entonces tenemos que construir un modelo donde el costo total este en función del tamaño del lote en producción; por esto determinamos el tamaño del lote que reduzca al minimo el costo total.
En este caso, son los mismos costos nada más que el costo de ordenar es diferente; por que en una situación de producción hablamos de un costo denominado correctamente **costo de preparación** de la producción.
Por ejemplo , aqui podemos tener un patrón de este modelo a lo largo del tiempo.
![[Pasted image 20260502194943.png]]

### Modelo de costo total
Para esto podemos primero determinar el punto de inventario máximo para esto tenemos la siguiente ecuación.
$$
Inventario \space máximo = (p-d)*t
$$
Donde:
- $p$ es la tasa de producción diaria
- $d$ es la tasa de demanda diaria
- $t$ número de días de una fase de producción.

Para poder llegar una formula útil, podemos cambiar ese t, por que sabemos que estamos produciendo $Q$ unidades a una tasa de producción diaría de $p$ por lo tanto:
$$
t = \frac{Q}{p} días
$$
Si lo reemplazamos podemos obtener el valor del inventario máximo.

$$
Inventario \space máximo = (1 - \frac{d}{p})*Q 
$$
El inventario promedio será dividir el inventario máximo por la mitad.
Como nuestro objetivo es obtener uno de los costos que componen el modelo, vamos a obtener el **costo anual de retención** que tenemos una retención unitaria de $C_h$ o $h$, entonces la ecuación es:
$$
Costo \space anual \space de \space retención = \frac{1}{2}(1-\frac{d}{p})*Q*h
$$
Una vez que ya tenemos un costo, quedaría determinar simplemente el otro, suponiendo que D es la demanda anual del producto y K es el costo de preparación de una fase de producción entonces el costo es exactamente el mismo que el EOQ.
Por lo tanto:
$$
Costo \space de \space preparación \space anual = \frac{D}{Q}K
$$
Por lo tanto si realizamos la suma de los 2 costos, obtenemos que el costo anual total (TC) es:
$$
TC = \frac{1}{2}(1-\frac{d}{p})*Q*h \space + \space \frac{D}{Q}K
$$

Básicamente haciendo un **par de villereadas** podemos llegar a reescribir y no depender de las tasas (d y p) quedandonos de la siguiente forma: 
$$
TC = \frac{1}{2}(1-\frac{D}{P})*Q*h \space + \space \frac{D}{Q}K
$$

### Tamaño del lote de producción económico
Como nos encanta ser mogolicos entonces hay que derivar esto respecto a Q, vaya dios a saber como chota se deriva esto pero queda lo siguiente

$$
Q^* = \sqrt{\frac{2DK}{(1-\frac{D}{P})h}}
$$
Y ese es el valor de la cantidad óptima a pedir para este tipo de modelo.


## Modelo de inventario con faltantes planeados

Un **faltante** o **falta de existencias** es una demanda que no puede ser satisfecha. Los faltantes muchas veces no son deseables, pero a veces pueden ser deseables y para que no sean un problema debemos pleanearlos y permitirlos correctamente. Un caso simple es un inventario de repuestos, por ejemplo por que tendrías una caja de cambios para un auto random? el cliente está dispuesto a esperar y entonces lo podes llegar a pedir.

El modelo toma en cuenta un tipo de faltante conocdio como **pedido en espera**, es cuando el cliente hace un pedido y el proveedor no lo tiene en existencia, entonces el cliente espera a que llegue dicho pedido y cuando el proveedor lo entrega el pedido se completa. La idea es que este periodo de espera sea relativamente corto; prometiendole prioridad al cliente.
El modelo que utilizamos es una extensión del EOQ, es un modelo en el cual todas las mercancías llegan al inventario a la vez y se someten a una tasa de demanda constante. **S** indica el número dep edidos en espera acumulados cuando se recibe un nuevo envío del tamaño **Q**, entonces el caso de este tipo de pedidos en espera tiene las siguientes características.
- Si existen **S** pedidos en espera cuando llega un nuevo envío de tamaño **Q**, entonces S pedidos se envían a los clientes apropiados y las $Q - S$ unidades restantes se colocan en el inventario; por esto $Q - S$ es el inventario máximo.
- El ciclo de inventario de $T$ días se divide en fases distintas; $t_1$ días cuando el inventario está disponible y los pedidos se entregan cuando se hacen, y $t_2$ días cuando se agotan las existencias y todos los pedidos nuevos se colocan en espera.

Con el patrón del inventario definido, se puede determinar el modelo del costo total; por esto tenemos los costos de retención y pedidos habituales, pero tenemos un costo de ordenar en espera en función de los costos de mano de obra y entrega especial, directamente asociados con el manejo de los pedidos en espera. Existe un **costo de plusvalía** (era re marxista el culiao que escribio esto).
Definiremos al **costo de plusvalía** como qué tnato tiempo tenga que esperar un cliente, y por esto se expresa el costo del pedido en espera en función del costo de tener una unidad en espera durante un lapso de tiempo establecido.
Se da el siguiente patrón de un modelo de inventario con pedidos de espera.
![[Pasted image 20260502210046.png]]
Como mencionamos el inventario máximo es Q-S unidades, dado en el tiempo $t_1$ pero no habrá inventario en el tiempo $t_2$ (es decir cuando es negativo); por lo tanto durante el ciclo total $T = t_1 + t_2$ podemos calcular el inventario promedio:
$$
 Inventario \space promedio = \frac{\frac{1}{2}(Q-S)t_1+0t_2}{t_1+t_2}= \frac{\frac{1}{2}(Q-S)t_1}{T}
$$
Ahora si queremos desglosarlo y llevarlo hacia un número de pedidos que nos convenga tenemos que encontrar otra sformas de expresar $t_1$ y $T$, el inventario máximo es $Q - S$ y $d$ representa la demanda diaria constante, entonces:
$$
t_1 = \frac{Q-S}{d} días
$$
Es decir el inventario máximo se agotará en $t_1$ días, y como en cada ciclo solicitamos $Q$ unidades, entonces la duración de un ciclo debería ser:
$$
T = \frac{Q}{d} días
$$
Si combinamos dichas ecuaciones, entonces podemos calcular el inventario promedio de la siguiente forma. (Se hacen un par de pasos algebraicos reemplazando, pero dan igual)
$$ 
Inventario \space promedio = \frac{(Q-S)^2}{2Q} 
$$
Entonces el inventario promedio se expresa en función de dos decisiones.
- **Cuánto ordenaremos (Q)**
- **El número máximo de pedidos en espera (S)**

La fórmula del número anual de pedidos colocados utilizando este modelo, es idéntica al EOQ, con D la demanda anual.
$$
Número \space anual \space de \space pedidos = \frac{D}{Q}
$$

Por lo tanto tenemos que desarrollar la expresión para el nivel de promedio de pedidos de espera, el máximo de pedidos de espera es S. _Calculos algebraicos aparte se llega a la sig form_
$$
Pedidos \space en \space espera = \frac{0t_1 + (S/2)t_2}{T} = \frac{(S/2)t_2}{T}
$$
Con: $t_2 = \frac{S}{d}$ por lo tanto reemplazando
$$
Pedidos \space en \space espera = \frac{S^2}{2Q}
$$

Ahora para obtener la ecuación que nos interesa $TC$, la del costo anual total es:
$$
TC = \frac{(Q-S)^2}{2Q}h \space + \space \frac{D}{Q}*K \space + \space \frac{S^2}{2q}C_b
$$
Donde:
- $K$ costo por pedido
- $h$ costo de retener una unidad en el inventario por un año
- $C_b$ costo de mantener un pedido de una unidad en espera durante el año

Ahora tenemos una ecuación que representa el problema que queremos resolver, para minimizar usamos calculo diferencial y obtenemos las siguientes formulas (Respecto a Q y Respecto a S)
$$
Q^* = \sqrt{\frac{2DK}{h}*(\frac{h+C_b}{C_b})}
$$
Y para el caso de $S^*$ es:
$$
S^* = Q^*(\frac{h}{h+C_b})
$$

## Descuentos por cantidad en el modelo EOQ

Los **descuentos por cantidad** ocurren en muchas situaciones en que los proveedores te dan incentivos por las cantidades de pedidos, ofreciendo menor costo cuanto más compres, la tabla lo específica.
![[Pasted image 20260502211522.png]]
Lo que se hace en este es (raro) básicamente utilizamos la ecuación básica para obtener $Q^*$ del EOQ, cambiando el valor de $h$, sabiendo que $h = I*C$ donde I es la tasa del costo de retención anual y C es el costo unitario del producto, como se ve en la tabla sería 5, 4.85 y 4.75, para este ejemplo.
La formula con la que comparemos será la siguiente
$$
Q_i^* = \sqrt{\frac{2DK}{h}}
$$
Iremos variando $i$ según la cantidad de costos unitarios distintos que tengamos, y  comparemos y luego lo llevaremos al mínimo del intervalo si es que está excedido, como ejemplo.
![[Pasted image 20260502212732.png]]
Como se ve, para el 1 la cantidad óptima está comprendida en el rango (0,999) pero tanto para $i=2,3$ no está comprendida en el rango óptimo, entonces vamos al extremo del intervalo más chico es decir, deberíamos pedir $Q_2=1000$ y $Q_3=2500$ cantidades para poder obtener el descuento correspondiente.


Las únicas diferencias con un modelo de EOQ clásico vienen de diferencias mínimas en el costo de retención, las cantidades del pedido son aproximadamente las mismas. Bajo la misma idea que las anteriores veces llegamos a la siguiente ecuación para el costo total de compra.
$$
TC = \frac{Q}{2}h \space + \space \frac{D}{Q}K \space + \space DC
$$
Con esta ecuación podemos determinar la cantidad óptima de pedido para el EOQ con descuentos, para esto podemos calcular las cantidades lo que nos interesa es obtener el valor para cada uno de los $Q_1, Q_2, Q_3$ de $TC$ y compararlos entre ellos, y el más chico será el que más nos convenga.
En este caso, se puede ver que el que más nos conviene es $Q_1$ en la siguiente tabla.
![[Pasted image 20260502213029.png]]
(Hay un error en la columna 3 "Cantidad del pedido" en la fila 3, debería decir 2500 pero dice 500).

Fíjate que el 2do que más nos conviene es la opción $Q_3$

