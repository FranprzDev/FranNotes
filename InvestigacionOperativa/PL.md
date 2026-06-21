![[Pasted image 20260519164223.png]]

Primero debemos determinar si la demanda es probabilistica o detemrinistica, para este caso podemos sumar la demanda. para saberlo teniendo en cuenta 12 meses

La sumatoria de meses daría igual a 9000 si lo dividimos en 12 nos daria que 
$$
\mu \approx  750 \space unidades
 $$
Ahora para saber, como cambia en promedio debemos sacar el valor de sigma, para esto lo que debemos hacer es lo siguiente:

$$
\sigma = \sqrt(\frac{\sum_{i=1}^n(x_i-\mu)^2}{n})
$$
Que para este caso específico sería:
(600-750)^2 + 800-750^2 + ... (770-750)^2

Todo esto nos dara un valor de 78800
Si lo dividimos en 12 como dice el enunciado nos dará el valor que va dentro de la raiz por lo tanto:
$$
\sigma = \sqrt{6566.67} \approx 81.03
$$
En este caso como la demanda entonces con todos losd atos podemos sacar el coeficiente de variación:

$$
CV = 81/750 = 10.8\% \approx 11\%
$$

Por lo tanto, podemos permitirnos tratar la demanda como deterministica, pero con una excepción, dice que la producción de Perfil-L25 es IMPORTANTISIMO no quedarse con el, entonces lo ideal sería tratarla como probabilistica, pero se puede hacer esta acotación. 

Si tratamos la demanda como deterministica aplicando un **EOQ CLÁSICO**

Pero por las dudas como es un producto que debería estar siempre, entonces vamos con un probabilistico para esto. Analizo los datos:

K : $200 por pedido
h : $4 u/a
costo unitario : 25 unidad
Lead time : 5 días 
Días habiles: 250 días
Demanda promedio : 750 +- 81

En este caso, yo aplicaría EOQ 
Calculamos le Q*

$$
Q* = \sqrt{\frac{2DK}{h}} = \sqrt{\frac{2*400*9000}{4}} \approx 1341,64 unidades
$$

Para la longitud del ciclo calculamos:
$$
t_0^* = 1341,64/9000 = 0,149 año * 250 = 37,25 días.
$$
Cantidad de pedidos al año:
$$
N = D/Q* = 9000/1341,64 = 6,70 pedidos.
$$

$$
CT^* = \frac{DK}{Q*} + DC + \frac{Q*h}{2}
$$

Para esto eliminamos DC por que no nos interesa.

En este acso lo resolvemos.
$$
CT^*=(9000*200)/1341,64 + 1341,64*2
$$
Por lo tanto el CT = $4024,92 seria el costo de mantener estos productos.
Para el punto de reorden utilizamos:

R = d*L 
$$
R = 9000*5 = 45000
$$
Osea cuando tenga 45k de estos vuelvo ap edir.