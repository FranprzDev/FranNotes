#### Técnicas de Modulación
- Denominamos modulación al proceos de colocar información contenida en una señal de **baja frecuencia** (banda base), sobre una señal de **alta frecuencia**.
- La señal de alta frecuencia que denominaremos **portadora** sufrirá la modificación de alguno de sus parámetros, así está modificación será proporcional a la amplitud de la señal de baja frecuencia que será denominada **moduladora**.
- El proceso de modulación implica adaptar una señal al medio de transmisión por el cual se propagará.
- Normalmente implica la alteración de su banda de frecuencias para transmitirlo en una banda de adecuada.
- La **demodulación** es el proceso inverso, mediante el cual es posible recuperar la señal de datos de la señal modulada.
- El **modem** es el dispositivo que tiene el modulador y el demodulador.

Es necesario modular las señales por las siguientes razones:
- Si todos los usuarios transmiten sobre la frecuencia original, será complciado reconocer la información de dicha señal debido a la interferencia entre las señales transmitidas.
- A altas frecuencias se tiene mayor eficiencia en la transmisión
- Se aprovecha mejor el espectro electromagnético, ya que permite **multiplexar por frecuencias**.

**Por lo tanto la modulación permite aprovechar mejor el canal de comunicación ya que posibilita transmitir más información en forma simultánea por un mismo canal y así proteger la información de posibles interferencias y ruidos.**

Las técnicas de modulación pueden ser clasificadas según el tipo de señales que se utilicen para la señal moduladora y la portadora, dependiendo ed que sean **ANALÓGICAS O DIGITALES**.

##### Tipos de Modulaciones
![[Pasted image 20241107024556.png]]

##### Modulación Digital d(t) y Pa(t) #IMPORTANTE
Aquí se ven la transmisión de datos digitales a través de la red telefónica; esta red fue diseñada para recibir  y transmitir señales analógicas en el rango de frecuencias de la voz (300 a 3400Hz), por ende esta red no es muy adecuada para transmitir **señales digitales**. Pero usando modems podemos utilizarla.
Los modems telefónicos, se utilizan para producir señales en el rango de las frecuencias de voz.
Dentro del grupo de transmisiones con **señales de transmisión analógicas** y **datos digitales** tenemos las siguientes técnicas de modulación o codificación dependiendo del parámetro de la señal portadora que es afectada:
- Desplazamiento de Amplitud {ASK} - (Amplitudes-shift keying)
- Desplazamiento de Frecuencia {FSK} - (Frequency-shift keying)
- Desplazamiento de Fase {PSK} - (Phase-shift keying)
- Si combinamos ASK + PSK obtendremos QAM - Quadrature amplitude modulation

###### ASK (Amplitud Shift Keying)
- La amplitud de una señal portadora se conmuta entre dos valores en respueta a un código binario de entrada manteniendo constante la freucencia y la fase.
- Utilizar ASK es un tipo de modulación digital de **baja calidad y bajo costo**, por lo tanto seusa poco en sistemas de comunicaciones de gran capacidad y alta eficiencia.
- ASK es sensible a cambios repentinos de la **ganancia** de snr, es bastante **ineficaz**
- ASK se utiliza para transmitir datos digitales en **fibras ópticas**.
- El ancho de banda para ASK es de **2B**
###### FSK (Frequency Shift Keying)
- Consiste en variar la frecuencia de la portadora entre dos valores diferentes de acuerdo con los datos de entrada; manteninedo constante la amplitud y la fase de la señal portadora.
- Para un "1" asignaremos una **Frecuencia 1** y para un "0" asignaremos una **Frecuencia 2**.
- Generalmente las **frecuencias 1 y 2** corresponden a desplazamientos iguales pero de distintos signos.
- El ancho de banda para FSK es de 2B + 2{delta}f
- ![[Pasted image 20241107025651.png]]

###### Ventajas de ASK vs FSK
- ASK ofrece mejor eficiencia en el ancho de banda.
- ASK es más fácil de diseñar.
- La modulación ASK se puede utilizar para transmitir datos digitales a través de la fibra óptica.
- ASK es más económico
- Ofrece menor eficiencia energética
- La modulación ASK es muy susceptible a la interferencia del ruido, ya que modulamos en amplitud; si aumentamos la amplitud también aumentamos el ruido.
###### Desventajas de ASK vs FSK
- Tiene menor probabilidad de error
- Proporciona una alta SNR
- Tiene mayor inmunidad al ruido (FSK)
- Las implementaciones de FSK son simples para bajas velocidades de datos
- FSK utiliza más ancho de banda que ASK
###### PSK (Phase Shift Keying)
- Consiste en variar la fase de la portadora de acuerdo a los datos, para el caso binario las fases variarán entre 0 y pi.
- Su ancho de banda es **2B**, el mismo que ASK

###### Modulación M-arias
Las técnicas de modulación digital mencionadas anteriormente solo emplean un bit para modular la señal portadora, pero podemos considerar más símbolos para hacer las modificaciones a las portadoras según necesitemos.
Un sistema M-ario es un sucesor de los sistemas binarios, donde la letra M representará la cantidad de símbolos posibles, para una cantidad de valores binarios, teniendo en cuenta que podemos usar M > 2 en estos casos.
Además; tendremos asociada la siguiente **ecuación** que permitirá relacionar el número de bits con el número de símbolos en un sistema **M-ario** #IMPORTANTE
![[Pasted image 20241107030352.png]]
Siendo "n" la cantidad de bits y "M" la cantidad de condiciones posibles de salida con un número "n" de bits.
En este tipo de modulaciones, **B** estará limitado por una relación entre números de bits y velocidad de transmisión.
![[Pasted image 20241107030501.png]]
###### Revisar las distintas modulaciones M-arias en el PP #IMPORTANTE 

###### QPSK (Modulación por Desplazamiento de fase en cuadratura)
Esta modulación se construye a partir de un BPSK utilizando desplazamientos de 90º y codificando dos bits por cada uno de los desplazamientos, es decir pi/4 donde M = 4. Obteniendo lo siguiente.
![[Pasted image 20241107030739.png]]

Si extrapolamos más aún el concepto podemos llegar a la modulación de tipo **nQAM**
- Es la combinación de modular en fase y en amplitud
- Significa combinar ASK + PSK de modo que haya un contaste máximo entre cada bit, dibit, tribit, etc.
- Como los cambios en Amplitud (A) son más susceptibles al ruido que los cambios de fase, lo ideal es tener más desplazamientos de fase que de amplitud.
- Podemos encontrar distintas versiones. **4-QAM, 8-QAM, 16-QAM, 32-QAM, 64-QAM, N-QAM...**

###### nQAM Adaptativo
**SNR en nQAM**
Las tasas de modulación de orden superior (4,8,16,32,...) ofrecen velocidades de datos mucho más rápidas y mayores niveles de eficiencia espectral para el sistema de comunicaciones tiene un precio, y este es su resistencia al ruido y las interferencias.
Como resultado a esto, se utilizan **técnicas de modulación dinámicas**, que adaptan la modulación para obtener la **máxima velocidad** de datos para las **condiciones dadas** de un canal de comunicación en ese momento

#Skipea
Modulaciones de más alto nivel proporcionan mayor número de bits eficaces por símbolo eso significa mayor R, pero son constelaciones más complejas y sensibles a interferencias, para poder manejar esto se creó el **EVM (Error Vector Magnitude)**
Es bastante difícil de explicar, carrasco no le da mucha bola y prefiere skipearlo un poco... Pero básicamente el chirimbolo calcula el EVM sabiendo que datos son correctos y lo que se recibió y si ve que el EVM es muy grande entonces te **baja de nivel la constelación** (Por ej pasa de 8-QAM a 4-QAM) de este modo hace que se tenga más precisión y exista disponibilidad. Ahora como lo hace; tal vez lo explico en clase, no recuerdo.

![[Pasted image 20241107031433.png]]

Esto puede ser bastante útil para algún ejercicio pero también puede ser #Skipea
![[Pasted image 20241107031642.png]]


##### Modulación por Pulsos a(t) y Pd(t) #IMPORTANTE
Sirve para muestrear señales de información analógicas y luego convertir estas muestras en pulsos discretos y transporte de los pulsos de una fuente a destino a través de un medio de transmisión físico.
Aquí tenemos los siguientes:
- **PAM (Pulse Amplitude Modulation)** #Skipea
- **PWM (Pulse Width Modulation)** #Skipea
- **PPM (Pulse Position Modulation)** #Skipea
- **PCM (Pulse Code Modulation)** #IMPORTANTE

Para basarnos en este tipo de modulación primero tendremos que basarnos en el **teorema de Nesquik** quien dice que podemos muestrear una señal si resulta que la frecuencia de muestreo es 2 veces mayor o igual que la frecuencia máxima.
###### PAM (Pulse Amplitude Modulation)
Es una modulación por la amplitud, y se produce al multiplicar una señal que contiene la información por un tren de pulsos periódicos que actue como portadora. Al realizar dicho producto se escalará en magnitud la amplitud de la señal.

**Métodos de muestreo** 
![[Pasted image 20241107032323.png]]

**Ventajas:**
- Fácil de generar y de detectar
- Permite enviar más de un canal usando TDM
**Desventajas:**
- Resulta dificil eliminar el ruido aditivo incorporado a la señal sin modificarla; ya que la amplitud tiene la información. 
- El ancho de banda de la transmisión es muy grande.
- Es bastante ineficaz en comunicaciones.

######  PWM (Pulse Width Modulation)
Lo que hacemos aquí es variar el ancho **(porción activa del ciclo de trabajo)** de un pulso de amplitud constante. Es decir variamos el tamaño del palito digamos teniendo en cuenta:
- La Amax de la señal analógica será el pulso más ancho
- La Amin de la señal analógica será el pulso más estrecho
- Todos los pulsos tiene la misma longitud.

**Ventajas:**
- Inmune al ruido
- Se puede distinguir la señal (pulso) del ruido en amplitud.
**Desventajas:**
- El ancho de banda requerido es mayor que el requerido por el PAM

######  PPM (Pulse Position Modulation)
La posición de un pulso de ancho constante dentro de un intervalo de tiempo, se varía de acuerdo con la amplitud de un muestro de la señal analógica. Mientras mayor sea la amplitud de la muestra, el pulso se colocará más a la derecha dentro de la ranura de tiempo, la muestra de amplitud más alta dará un impulso pegado a la derecha y al revés pegado a la izquierda.

**Ventajas:**
- Muy alta inmunidad al ruido
- Se puede distinguir fácilmente la señal (pulso) del ruido en amplitud

**Desventajas:**
- El proceso y la circuitería son complejos.

######  PCM (Pulse Code Modulation) #IMPORTANTE
Este consta de 3 procesos:
1) Muestreo y retención de la señal (PAM)
2) Cuantificación
3) Codificación

Es decir utilizar PCM es realizar todo un proceso para poder obtener la mejor modulación.
![[Pasted image 20241107033127.png]]

- **Cuantificación:**
	En este proceso la señal analógica se divide en un determinado número de niveles de cuantificación M = 2^n, siendo n el número de bits que se emplearan en la transmisión.
	El bit más significativo será el bit de signo.
	La señal se distribuye uniformemente dentro del intervalo de cuantificación.
	Al terminar este proceso la señal cuantificada, será una aproximación de la señal analógica.
	Se considera que la señal que será cuantificada no presentar componente continua y alcanza una amplitud máxima.
	![[Pasted image 20241107033442.png]]
	**Vas bajando y poniendolo según corresponda, la salida es lo que está en rojo.**

**PCM es la forma más frecuente de la modulación de impuslso** #IMPORTANTE

**Cuantificación Uniforme:**
- Hay que utilizar un **número finito** de **valores discretos** para representar la forma aproximada la amplitud de las muestras.  Para ello, toda la gama de las muestras se divide en amplitudes con intervalos iguales, y a toda muestra cuyo valor caiga dentro de ese intervalo se le da el mismo valor.
- El proceso de cuantificación introduce de por sí un error, llamado **error de cuantificación.**
- El error de cuantificación disminuye, si aumentamos el número de intervalos de cuantificación M, pero existen limitaciones de tipo práctico para que M no pase cierto valor.
- Si todos los intervalos tienen la misma amplitud se llama **cuantificación unfirome**

Soluciones para la cuantificación uniforme y sus problemas:
1) Si aumentamos la cantidad de intervalos M habrá menos errores, pero necesitaremos más bits para transmitir algo, por lo tanto necesitamos más ancho de banda B.
2) Utilizando una **cuantificación no uniforme**, en la cual se toma un número determinado de intervalos y se distribuyen de forma no uniforme, y asignando correspondientemente los intervalos, así disminuimos la cantidad de errores.

**Cuantificación NO UNIFORME**
- Se utiliza en los codificadores PCM de voz.
- Consiste en ecualizar con intervalos más pequeños las señales de menor potencia, y con niveles más espaciados las muestras de mayor energía de la señal.
- La distorsión de la señal se evita haciendo el proceso inverso en el receptor.
- Hay que seguir los estándares, **Ley A en el mundo**, **Ley Mu en Yankeelandia**

**Ley A y Ley Mu** #Skipea
Parecen bastante raras de explicar, dudo que las tomen.

El dispositvo que realiza la cuantificación y la codificación se llama codificador.

######  Ventajas de la transmisión digital
- La ventaja principal es la **inmunidad al ruido**.
- Almacenamiento y procesamiento, las señales digitales pueden guardarse y procesarse más fácilmente que las señales analógicas. Así también se puede utilizar algoritmos de comprensión de datos para ahorrar espacio y ancho de banda. 
- Se utiliza la **regeneración de las señales** antes que la amplificación, por lo tanto son mejores.
- Los sistemas digitales están mejor equipados para evaluar un rendimiento de error que los analógicos.
- Los equipos que procesan señales digitales consumen menos potencia y son más pequeños, y también son más económicos.
**Desventajas de la transmisión digital**
- Las señales analógicas codificadas de manera digital requiere más ancho de banda, que transmitiéndola como señal analógica.
- Las señales analógicas si o si deben convertirse en códigos digitales.
- Requiere sincronización entre los relojes del transmisor y receptor.
- Los sistemas de transmisión digital son incompatibles con las instalaciones analógicas actuales.

**Ventajas del PCM**:
- En comunicaciones a largas distancias, la señal con PCM puede regenerarse por completo sin problemas.
- Los efectos del ruido no se acumulan y solo hay que preocuparse por el ruido de la transmisión entre repetidoras y siguientes.
- Las señales pueden almacenarse y ponerse a escala en tiempo.
- Puede usarse un código para reducir la redundancia de los mensajes
**Desventajas del PCM:**
- La gran desventaja es el ancho de banda en comparación con el ancho de banda que requiere la señal analógica original, sin embargo con sus ventajas es lo mejor que hay.

![[Pasted image 20241107035215.png]]

##### Técnicas de Multicanalización - Multiplexación #IMPORTANTE
**Estas técnicas permiten un mejor aprovechamiento de los recursos específicamente del medio físico de transmisión**

![[Pasted image 20241107035448.png]]

**EL MULTIPLEXOR** 
 - Combina (multiplexa) los datos (servicios) de las líneas de entrada 
 - Los transmite a través del enlace de mayor capacidad

**EL DEMULTIPLEXOR** 
- Acepta la cadena de datos multiplexada 
- Separa (demultiplexa) los datos (servicios) conforme al canal al que pertenece. 
- Los distribuye a la línea apropiada de salida

###### Tipos Básicos de Multiplexación #IMPORTANTE
1) Por división de Frecuencia (FDM)  {Las señales pueden ser analógicas o digitales}
2) Por división de tiempo (TDM) {Solo para señales digitales}
	1) TDM Síncrona: Señal digital / señal analógica digitalizada
	2) TDM Asíncrona / Estadística / Inteligente
3) Por Divisón de Código (CDM) 
4) Por División de Longitud de Onda (WDM) {Utilizada en fibra óptica para transmitir varias señales, cada una con distinta longitud de onda, es un caso especial de FDM}

**FDM**
El ancho de banda disponible se divide en un número determinado de slots o segmentos independientes, donde cada segmento lleva una señal de información; como por ejemplo un canal de voz.
![[Pasted image 20241107035923.png]]
Ejemplo:
![[Pasted image 20241107035941.png]]

**TDM**
Este principio consiste en utilizar un solo canal de alta capacidad y dividirlo en sub canales lógicos definidos en base al tiempo. A cada uno de las entradas se le asigna un tiempo donde tendrá todo el ancho de banda disponible (B). Por rotación o por estadística se define quien tendrá el ancho de banda disponible, este mecanismo se basa en la técnica llamada **interleaving**.

**TDM SINCRÓNICA:**
Asigna secuencialmente una ranura de tiempo a cada dispositivo **aún en el caso de que alguno de los no tenga nada que transmitir**, por esto no se aprovecha toda la capacidad del camino ya que algunas ranuras de tiempo pueden quedar vacías.
![[Pasted image 20241107040233.png]]
![[Pasted image 20241107040327.png]]

La implementación de TDM no es tan sencilla como FDM, La sincronización entre el Multiplexor y el Demultiplexor es un problema importante; si no están sincronizados, un bit puede ocasionar muchos problemas; debido a esto se añaden uno o más bits de sincronización al comienzo de cada trama; así permitiendo que se sincronicen entre ellos, pero esto hace que mandemos bits que no son información.

**TDM Asincrónica:**
- No envía ranuras vacías si no hay nada que enviar.
- El multiplexor sondea las entradas y recoge los datos hasta completar el ciclo, para que monte la trama y enviarla.
- Necesita un direccionamiento en cada ranura para reconocer la salida correspondiente.
- Gráficamente sería así:
- ![[Pasted image 20241107040628.png]]
![[Pasted image 20241107040747.png]]
![[Pasted image 20241107040802.png]]Ejemplo:
![[Pasted image 20241107040818.png]]

**Jerarquías Digitales PDH (E1 y T1)**
En la transmisión de señales digitales se recurre a la multiplexación TDM con el fin de agrupar varios canales en un mismo vínculo. La velocidad base está en 64Kbps, pero las velocidades de los órdenes de la multiplexación crea jerarquías.
Nació la jerarquía **PDH (Plesiochronous Digital Hierarchy).** #IMPORTANTE
- En europa se utiliza la PDH del sistema 'E', utilizando la agrupación básica E1; 30 canales + 2 de servicio y sincronismo y transmite a 2048 Kbps.
- En Norteamérica y Japón se utiliza 'T' que tiene en base T1 con 24 canales + 1 bit y transmite a 1544Kbps
![[Pasted image 20241107041243.png]]
**PDH-E** (Leer en pp)
**PDH-T** (Leer en pp)

**Problemas de la jerarquía PDH** #Skipea
- **Incompatibilidad intercontinental:** YANQUEES CULIAOS HACEN TODO MAL
- No pensada para fibra óptica
- Capacidades máximas bajas: Las capacidades máximas previstas resultan insuficientes para las capacidades de los equipos actuales
- Carece de herramientas de gestión y de mecanismos de tolerancia a fallos
- Los relojes no están perfectamente sincronizados. 

**SDH (Synchronous Digital Hierarchy)** #Skipea
- Es un conjunto de protocolos de transmisión de datos.
- Se puede considerar como la revolución de los sistemas de transmisión, como consecuencia de la utilización de la fibra óptica como medio de transmisión, así como de la necesidad de sistemas más flexibles y que soporten anchos de banda elevados.
En **SDH**, cada trama va encapsulada en una estructura denominada contenedor, y se organiza como un marco, con campos de carga útil y encabezados de control para identificar el contenido de la estructura. La transmisión de una trama comienza en la esquina superior izquierda y termina en la inferior derecha. Se transmiten **8.000 tramas** por segundo **(una cada 125 µs)**
![[Pasted image 20241107041758.png]]
**SDH no nace para sustituir a PDH, sino para ser usado en conjunto como medio de transporte en los enlaces que requieren mayor capacidad**
**El papel de SDH es gestionar la transmisión eficiente a través de la red óptica, con mecanismos internos de protección.**

**Ventajas de SDH**
- Reducción de coste de los equipos de transmisión
- Mayor velocidad de transmisión
- La compatibilidad ( se pusieron de acuerdo, por fin )

**WDM (Wavelength Division Multiplexing)**
Es una tecnología que transporta varias señales sobre una fibra óptica, empleando para cada señal una longitud de onda diferente. Esta basada en FDM; diseñada para utilizar la capacidad de altas tasas de datos de la fibra; conceptualmente es lo mismo que FDM, solo que involucra señales luminosas.
![[Pasted image 20241107042213.png]]
Hace esto, simplemente.
![[Pasted image 20241107042301.png]]

**Tipos de WDM** #Skipea 
**Topologías de WDM** #Skipea 
Si bien, están ahí en el PDF; son las mismas que en el primer parcial,  solo que es para fibra...
No creo que sea importante ni si quiera leerlo.
