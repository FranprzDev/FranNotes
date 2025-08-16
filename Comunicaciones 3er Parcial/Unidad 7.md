# Unidad 7 - Técnicas de Transmisión de Información
Los datos en las computadoras comunes siempre estarán en forma de **datos digitales**, esto quiere decir que son digitales, pero podemos transmitir de dos formas:
- Transmitir por medio de señales digitales.
- Transmitir por medio de señales analógicas.
Para tomar esta decisión, lo más común es que venga determinada por el **medio de transmisión** que utilizaremos.
Ya que este tiene limitaciones, no todos los medios de comunicaciones permiten **señales analógicas** ni todos **señales digitales**, pero nuestros datos siempre serán digitales; por lo tanto necesitaremos un proceso para poder adaptar nuestros datos a por donde queremos transmitir.
Por lo tanto tenemos dos formas de transmitir.
- **Información digital y transmisión de señal digital:** 
	- Para obtener la secuencia que tiene la señal digital a partir de los datos digitales tenemos que realizar el proceso de la **codificación**.
	- Existen muchos métodos para codificar. como por ejemplo **Transmisión en Banda Base**, **Codificación de Línea** o **Transmisión de Banda Angosta**.
- **Información digital y transmisión de señal digital**
	- Al proceso de convertir nuestros datos digitales en una señal analógica para transmitir lo llamaremos **modulación**
	- Esta señal puede ser transmitida, pero el receptor deberá realizar el proceso contrario llamado demodulación para poder recuperar la información.
	- El **modem** es el laburante que hace eso.

### Transmisión de datos, códigos de línea
Este es el proceso que se lleva a cabo para transmitir información digital, podemos pensar una señal digital como una hilera de pulsos rectangulares de amplitudes discretas.
![[Pasted image 20241106230423.png]]

Llamaremos **codificación y decodificación de línea** la representación de datos digitales utilizando señales digitales.
Esta conversión involucra tres técnicas:
1) **Codificación de línea**
2) **Proceso de convertir datos digitales en señales digitales:** Los datos son almacenados en un nodo o servidor como una secuencia de bits, estos números se convierten en señales digitales, a través de niveles de voltaje (M) para poder transmitirlos
3) **Convierte una secuencia de bits codificándolos a una señal digital**
#### Bits y símbolos
- **Bit** en las comunicaciones el objetivo es enviar bits de datos; un bit es la entidad más pequeña que puede representar un elemento de información.
- **Símbolo** es la forma en la cual se transportan los bits (variaciones de voltaje). Un símbolo es la unidad más corta (en cuanto a tiempo) de una señal digital.
- Es decir podemos decir que los bits son transportados y los simbolos son los portadores.
#### Tasa de bits y Tasa de símbolos
- Tasa de bits: Es el número de bits enviados en 1 segundo, medida en **bps**, conocida como tasa de datos, velocidad de transmisión o **R**
- Tasa de símbolo: Es el número de símbolos enviados en 1 segundo, su unidad es el **Baud**, denominado también tasa de señal, tasa de pulso, tasa de modulación, o tasa de **Baud r**
- #IMPORTANTE  **Un objetivo en la comunicación de datos es incrementar la tasa de bits, al mismo tiempo que se reduce la tasa de símbolos**
	- Si aumentamos **R**, incrementamos la velocidad de transmisión
	- Si reducimos **r**, reducimos los requisitos para **B**
	- Todo esto se deduce de la siguiente formula:
	- ![[Pasted image 20241106231959.png]]
	- Recordando también que n = log_2(N)
- **Baudio** es el número de cambios altos / bajos que se hacen en la línea de transmisión por segundo y describe la cantidad de veces que la línea de transmisión cambia de estado por segundo.
#### Medida de la velocidad de transmisión
- Velocidad de transferencia de datos: Es el número medio de bits por unidad de tiempo que se transmiten entre equipos. 
	![[Pasted image 20241106232401.png]]
- Velocidad efectiva de transferencia de datos (Throughput): Es el número medio de bits por unidad de tiempo que se transmiten entre los equipos ![[Pasted image 20241106232412.png]]
#### Ancho de Banda
Recordemos que es un recurso finito y que cuesta dinero y que precisamente es bastante caro; siempre queremos tener más ancho de banda.
#IMPORTANTE **Una señal digital que transporta información NO ES PERIODICA por lo tanto, su B es continuo con un rango infinito.**
Sin embargo, cualquier señal digital tendrá un **B Finito** a pesar de que sea infinito, pero muchas componentes no aportan absolutamente nada, por lo tanto, el **B efectivo** es finito y debería poseer la mayoría de la energía de la señal digital para poder ser detectada.
- **Ancho de Banda Real:** El que utiliza toda la señal, calculado por medio de fourier.
- **Ancho de Banda Efectivo:** El que realmente necesitamos transmitir para poder reconocer la señal como tal.

#### Ancho de Banda Digital
Llamamos así a la cantidad de datos que se pueden transmitir en una unidad de tiempo.
El ancho de banda es la cantidad máxima de datos que pueden ser transmitidos a través de una conexión a Internet en un tiempo determinado.

#### Tipo de Transmisión de Datos (Paralelo y Serie)
##### Paralelo 
Los bits que componente un byte se transmiten en un solo ciclo de reloj, para esto utilizaremos **n** hilos para enviar **n** bits simultáneamente a cada pulso de reloj
###### Características principales
- La transferencia interna de datos se hace así.
- Cada conjunto de bits es separado por un espacio de tiempo.
- Se usa para transmisiones de altas velocidades.
###### **Ventaja**
- Velocidad de transferencia superior en un factor **n** a la transmisión en serie.
###### **Desventaja**
- Es bastante caro y es limitado a distancias cortas.

##### Serie
Los bits que componen cada carácter se transmiten en "n" ciclos de 1 bit cada uno.
###### Características principales
- Se envía un bit después de otro, hasta completar un carácter.
- Se usa un solo hilo
- Se utiliza en las comunicaciones
- Se utiliza la deserialización.
###### **Ventaja**
- Se reducen los costes en un factor n y puede ser utilizado en mayhores distancias
###### **Desventaja**
- Se reduce la velocidad de TX (transmisión, supongo) en un factor n

#### Concepto de Sincronismo.
Se utiliza para describir una transferencia de bloques de datos con temporización continua y coherente, esto sirve para transferir grandes cantidades de datos con gran rapidez.
Para la interpretación de las señales correctas, los intervalos de bits del receptor deben corresponder exactamente con los intervalos de bits del transmisor.
Si alguno de los relojes está desfazado, esto ocasionará problemas en la interpretación de las señales.
Una señal con **auto-sincronización** incluye información sobre el tiempo en los datos transmitidos; esto se consigue modificando la señal al comienzo, la mitad o el fin del pulso.
Entonces el concepto se basa en **que tanto la fuente y el receptor tengan una base de tiempo común para poder reconocer de forma inequivoca la transmisión de un 1 y un 0**.

#### Transmisión en Serie - ASÍNCRONA
Los datos son enviados **byte a byte** a intervalos variables de tiempo; la sincronización se consigue marcando cada byte que se envía con un bit de arranque **(start bit)**, y un bit de parada **(stop bit)**. La función del bit de arranque es avisar al receptor que llegan datos y hacer que se ponga en marcha la lectura de los siguientes 8 bits; la función del **bit de parada** es justamente pasar del reposo para asegurar un cambio de estado e identifique los siguientes bits de arranque.
- La línea de comunicación siempre estará en 1 **(tensión máxima)**
- Se transmiten los bits de datos, y se almacenan en una memoria intermedia.
- El bit de parada se encarga de volver a colocar la señal en el nivel máximo para arrancar de vuelta el proceso.
#### Transmisión en Serie - SINCRÓNICA
Se envían un bit detrás de otro, sin bit de inicio o parada. La agrupación de estos es responsabilidad del receptor; **la sincronización es a nivel byte**, y se lleva acabo en el enlace de datos, es utilizado para comunicaciones de alta velocidad.
- La trama de datos se transmite en un flujo continuo de bits; sin retardo entre cada elemento de 8 bits.
- Entre tramas podemos utilizar bytes de sincronismo y caracteres para iedntificar las tramas.
- La idea es poder transmitir bloques grandes con tasas de bits altas.
- El byte de sync es especial, en este acso es **10010110** (Esto no importa, solo lo dejo para que se sepa que existe uno específico para el propósito).
##### Alternativas a la comunicación sincrónica #Skipea
- Transmisión orientada al CARÁCTER
	- El bloque es tratado como una secuencia de caracteres, y toda la información de control se utiliza con caracteres especiales de control.
	- ![[Pasted image 20241107004720.png]]
- Transmisión orientada al BIT
	- El bloque es manejado como una secuencia de bits.
	- Los mecanismos de control se realizan mediante solo parones de bits.
	- ![[Pasted image 20241107004733.png]]		![[Pasted image 20241107004757.png]]

#### Tipos de transmisión: Asincrónica vs Sincrónica
- El coste de usar dispositivos síncronos es mayor que los dispositivos asíncronos, ya que utilizan más circuitos.
- La transmisión sincrónica se utiliza típicamente cuando la eficacia de la transmisión es importante.
- La transmisión asincrónica tiene un 20% de **overhead**, mientras que el % de overhead de la otra es menor mientras más grande es la cantidad de datos a enviar.
#### Tipo de transmisión de datos:  #Skipea
##### Simplex (SX)
Es unidireccional, ocurre en una dirección solamente; Deshabilita al receptor de responder al transmisor, como por ejemplo la radiodifusión.
Una comunicación, es simplex , si están perfectamente definidas las funciones del emisor y del receptor y la transmisión de datos siempre se efectúa en una dirección y la transmisión de los datos siempre se realiza en una dirección
Gráficamente:
![[Pasted image 20241107005143.png]]
##### Half-Duplex (HDX)
Permite transmitir en ambas direcciones; sin embargo, la transmisión puede ocurrir solamente en una dirección a la vez. Por ejemplo los Woki tokis (handies) donde solo se puede recibir o enviar audio; una sola a la vez.
Gráficamente:
![[Pasted image 20241107005308.png]]
##### Full-Duplex (FDX)
Permite transmitir en ambas direcciones, pero simultáneamente por el mismo canal; para esto existen dos frecuencias, una para transmitir y otra para recibir. El caso más típico es el de la telefonía.
Gráficamente:
![[Pasted image 20241107005527.png]]

#### Códigos de Línea - Banda Base
##### **Características que deben cumplir los códigos de línea** #IMPORTANTE
Literalmente, este Diagrama de Venn es bastante importante, lo recuerdo con bastante claridad que carrasco habló sobre él; para un multiple choices seguro sea clave.

![[Pasted image 20241107005637.png]]

#### Esquemas de Codificación de Línea #IMPORTANTE
##### Unipolar - NRZ
- Todos los niveles de la señal se encuentran a un lado del eje del tiempo, o por encima (+) o por debajo (-)
- **Ejemplo:** Un voltaje positivo define un bit a 1 y un voltaje a cero define un bit a 0 
- Se denomina **NRZ** debido a que la señal **No Retorna a Cero** en la mitad del bit.
- ![[Pasted image 20241107010637.png]]
###### Problemas
- **Posee componente DC** (valor medio distinto de 0).
	- Esto se debe a que si sumas todos los 1 y todos los 0,  no dará un 0 como tal, si no una componente continua, que es difícil de enviar a través de algunos medios, entonces habrá que invertir para poder enviarlo.
- **No compatible para algunos equipos y medios de transmisión.** 
- **Inmunidad al ruido** 
- **Auto sincronización**
	- Si la señal no varía, el receptor puede no tomar correctamente el inicio y el fin de los bits. Entonces si tenemos largas series de 1 o de 0 estamos jodidos.
- **Transparencia**
##### Polar - NRZ
- Los voltajes se encuentran a ambos lados del eje del tiempo, se utiliza dos niveles de tensión (+ y -) 
- **NRZ-L (Level):** El nivel de voltaje determina el valor del bit 
- **NRZ-I (Invertido):** La inversión o falta de inversión en el nivel de voltaje determina el valor del bit, si no hay cambio, el bit es cero y si hay cambio, el bit es uno.
- ![[Pasted image 20241107010621.png]]

###### Problemas
- **Posee componente DC** (valor medio distinto de 0).
- **Auto sincronización**
- **Transparencia**

##### Polar - RZ (Retorno a Cero)
- Utiliza tres valores: positivo, negativo y cero. 
- La señal cambia durante el tiempo del bit 
- Se soluciona el problema de Autosincronización de los esquemas NRZ. 
- No hay problemas con la componente de DC
- ![[Pasted image 20241107010609.png]]
###### Problemas
- **Ocupa mayor ancho de banda al requerir dos cambios de la señal para codificar un bit**
- **Codificación compleja de crear y discernir**
##### Comparativa #Skipea
![[Pasted image 20241107010752.png]]
##### Polar - Bifásica
- La señal cambia en el medio del intervalo del bit, pero sin retorno a cero, continuando el resto del intervalo en el polo opuesto. 
- La primera mitad del periodo determina el valor del bit y la segunda mitad sincroniza. 
- **Manchester:** Combina las ideas de RZ y NRZ-L, el voltaje permanece en un nivel durante la primera mitad y transiciona a otro nivel en la segunda mitad. Se utiliza en redes LAN Ethernet  
- **Manchester Diferencial:** Combina las ideas de RZ y NRZ-I. Siempre hay transición en la mitad del bit. Se utiliza en redes LAN Token Ring.
- ![[Pasted image 20241107010914.png]]
###### Características de la Bifásica
![[Pasted image 20241107011011.png]]

##### Bipolar - AMI (Alternate Mark Inversion)
- Se utiliza tres niveles: positivo, negativo y cero 
- **AMI (Inversion de marca alternada)**, marca proviene de la telegrafía y significa “1”.
- Es la inversión de “1” alterno, los 1s se representan con valores alternados positivos y negativos. El “0” se representa con cero voltios. 
- **Pseudo Ternaria:** Variación de AMI en la que un “1” se codifica como un voltaje cero y un “0” se codifica alternando voltajes positivos y negativos. 
- El esquema bipolar que se desarrollo como **alternativa al NRZ** 
- Se utilizan en comunicaciones de larga distancia
##### Características de AMI
![[Pasted image 20241107011313.png]]

##### Bipolar - AMI con Aleatorización (Es un B8ZS primitivo)
- Modifica la codificación AMI, resolviendo el problema de la autosincronización ante la presencia de una larga secuencia de “0”
- El sistema inserta los pulsos requeridos de acuerdo a las unas reglas de aleatorización definidas. 
- La aleatorización se realiza al mismo tiempo que la codificación

##### B8ZS - Bipolar con sustitución de ocho ceros
- Utilizada normalmente x yankees 
- Sustituye 8 ceros consecutivos con 000VB0VB, B indica señal Bipolar valida y V indica Violación Bipolar AMI 
	- Si aparece un octeto con todo ceros y el último valor de tensión anterior a dicho octeto fue positivo, se codifica dicho octeto como 000+-0-+ 
	- Si aparece un octeto con todo ceros y el último valor de tensión anterior a dicho octeto fue negativo, se codifica dicho octeto como 000-+0+- 
	- El receptor detecta e interpreta las violaciones como un octeto de todos “0”
	- ![[Pasted image 20241107011557.png]]
##### HDB3 - Bipolar de alta densidad con tres ceros
- Utilizada normalmente fuera de Norte América (sin yankees culos rotos) 
- Cuatro “0” consecutivos son reemplazados por 000V o B00V, la razón para dos sustituciones diferentes es mantener un numero par de pulsos distintos de “0” después de cada sustitución. 
- Si el numero de pulsos distintos de “0” después de la ultima sustitución es impar, el patrón de sustitución será 000V 
- Si el numero de pulsos distintos de “0” después de la ultima sustitución es par, el patrón de sustitución será B00V
- ![[Pasted image 20241107011707.png]]

##### ¿Cuál es mejor?
Todo dependerá de lo que queremos transmitir como tal, pero podemos concluir.
- Utilizando **esquemas bifásicos Manchester** son adecuados para enlaces dedicados para LAN, pero no sirven para largas distancia por que requieren mucho B.
- Utilizando la **codificación bipolar AMI** tenemos menos B, no crea componente DC, pero tenemos problemas con secuencias largas de 0 provocando problemas de **auto sincronización** corrigiéndolo con **AMI con aleatorización (El de los yankees o el de los europeos)**