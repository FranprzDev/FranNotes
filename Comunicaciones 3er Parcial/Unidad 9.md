### Modem
El modem es un dispositivo que convierte las señales digitales procedentes de un emisor en señales analógicas, para su transmisión a través de un medio que puede ser un circuito telefónico o un circuito punto a punto.
![[Pasted image 20241107044416.png]]
**El equipo terminal de datos ETD:** A nivel físico puede ser un terminal, una computadora, una impresora o cualquier dispositivo que genere o consuma datos digitales.

**El modem o Equipo de Terminación de Circuito de Datos ETCD:** Incluye cualquier unidad funcional que transmita o reciba datos a través de una red en forma de señal digital o analógica. 

**Clasificación de los Modems**
1) Modem Analógico
	1) Modem externos
	2) Modem internos
2) Modem Digital
3) Cable Modem

#### Modem Analógico #Skipea
Se caracteriza por convertir las señales digitales propias de una computadora a señales telefónicas de tipo analógico, y a la inversa. De esta manera permite que la transmisión y recepción de datos a través de la línea. Su velocidad oscila entre 9.5 Kbps y los 56Kbps (Muy baja, utiliza el canal de voz)
Estos modems se clasifican a su vez en:
- Externos: Se ubican cerca de la PC, conectandose a la misma y a la red telefónica, sus condiciones se pueden ver a través de las luces.
- Internos: Presentan forma de tarjeta y son ubicados en ranuras de expansión


#### Modem Digital #IMPORTANTE 
Los modems digitales precisan una línea telefónica de carácter digital denominada **RDSI**, alcanzan hasta 128kbps.
La RDSI es la evolución natural de las líneas telefónicas convencionales para el modem analógico.

#### Cable Modem #IMPORTANTE 
Este termino alude a un dispositivo que permite acceder a internet a una velocidad superior. Consitituyen cajas de caracter exterior las cuales se conectan a la PC, se conectan a la red y a la PC por medio de ethernet.

#### Velocidad de Transmisión en los Modems #Skipea
Leer las diapo en el pp.

#### Estándares de la ITU-T para modems (Series V) #Skipea
Leer las diapo en el pp.

### Modem Banda Ancha
![[Pasted image 20241107045233.png]]
Así eran las conexiones anteriores, pero resulta que los muchachos se dieron cuenta que eran unos boludos, estaban garpando por ancho de banda pero no lo estaban utilizando.
![[Pasted image 20241107045307.png]]

Entonces de aquí surge la duda **¿Cómo lo utilizamos de forma eficiente?**
Y de aquí saltan las siguientes formas de utilizarlo:

#### POTS (Plain Old Telephone Service - Telefonía Básica) 
![[Pasted image 20241107045357.png]]
Tengo la central, tengo un armario y lo encajo por la línea común y lo mando a la casita de los muchachos, pero como no teníamos la tecnología aquí aparecio la familia de **xDSL**

**xDSL:**
Es un grupo de tecnologías de comunicación que permiten transportar información multimedia a mayores velocidades, que las que se obtenían anteriormente, utilizando las líneas telefónicas convencionales.
El **DSL** se refiere a la línea de abonado digital, que ya está instalada actualmente.

**MODEM ADSL (Asymmetric Digital Subscriber Line o Línea de Abonado Digital Asimétrica):**
Es una tecnología que basada en el par de cobre de la línea telefonica normal, lo convierte en una línea de alta velocidad. Empleando los espectros de frecuencia que no son utilizados para el transporte de la voz.
En esto pasará por un **Splitter** el cual se encargará del redireccionameinto en el usuario y en la central para saber si tiene que ir para el lado de datos o el lado de voz.
![[Pasted image 20241107045731.png]]

Así es como ADSL utiliza técnicas de codificación digital que permiten ampliar el rendimiento; estableciendo tres canales independientes sobre la línea telefónica estándar.
1) Dos canales de alta velocidad
	1) Recepción de datos (Bajada)
	2) Envío de datos (Subida)
2) Un canal para la comunicación normal de voz, (POTS - 64kbps)
![[Pasted image 20241107050058.png]]
La idea es que estos dos canales sean asimétricos, es decir sin la misma velocidad.
**Ventajas ADSL**
- Uso simultáneo de Internet y de teléfono.
- Conexión permanente a gran velocidad.
- Tarifa plana de conexión a internet
- + Seguridad
- Acceso a servicios y contenido de ancho de banda.

A la vez que avanzó la tecnología, la velocidad que aporta ADSL común nos quedabamos cortos, 1Mb bajada y 80Khz subida, por lo tanto utilizando Multiplexación con FDM (Evolucionado después a QAM) crearon DMT (Discrete Multi Tone) el que permitió mejorarlo.
Así es como, si modulamos **distantas freucencias portadoras** usando **QAM**, haciendo que las frecuencias esten espaciadas de forma constante y cada portadora tenga su propia SNR para saber el máximo de QAM que puede tener siendo:
- Mínimo -> 4-QAM -> 2bits/símbolo
- Máximo -> 16384-QAM -> 14bits/símbolo
Hacer esto se denominó **DMT (Discrete Multi Tone)**
Para hacer esto utiliza el **showtime**  que mide el SNR en todas las portadoras en intervalos regulares de 10 seg.

**EXPLICACIÓN DE DMT y como funciona** #IMPORTANTE
EN EL PP LO EXPLICA PERFECTO.

La cuestión, es que esto fue buenísimo. Hizo un gran UP en las comunicaciones y en las velocidades como tal.
Por lo tanto si miramos el espectro de freucencias que tenemos; podemos concluir lo siguiente:
![[Pasted image 20241107050648.png]]

Nos fuimos al carajo, pero como avanzó la tecnología y necesitábamos más mb se inventaron otras cosas, por lo tanto y por ende aparecen ADSL2 y ADSL2+ que se basan en el principio de **"che no estamos usando ciertos canales, los usemos y que se haga agua el helado"**, y así fue como utilizaron los canales que no estaba usando en ADSL común pasando de 8/1 a 12/2 y 24/2 Mbps.
Como se ve en el gráfico:
![[Pasted image 20241107050823.png]]

Ahora el drama; es que mientras más lejos estes de la central menos posibilidad de conectarte con ADSL2+/ADSL2 tenes, por lo tanto era muy propenso a perder calidad.  (- Calidad -> + Ruido y + Atenuación)

**DSLAM (Digital Subscriber Line Access Multiplexer)**
Es un multiplexor localizado en la central telefónica que proporciona a los abonados acceso a los servicios DSL sobre cable de par trenzado de cobre.
![[Pasted image 20241107051033.png]]

**VDSL (Very high-bit-rate Digital Subscriber Line)**
Una alternativa para alcanzar altas velocidades de transmisión de datos, es la combinación de cables de fibra óptica alimentando a las unidades ópticas de red
En los sectores residenciales con la conexión final a través de la red telefónica de cobre. Dentro de éstas topologías se incluyen las llamadas FTTx (fiber-to-the, “Fibra hasta”), donde se llega con fibra a localidades cercanas al usuario final. Tenemos los siguientes:
- FTTN (hasta el Nodo)  
- FTTB (hasta el edificio) 
- FTTC (hasta la acera)

Básicamente estos usan VDSL, que no es más que ADSL2+ donde agregamos más frecuencia para laburar, con la bajda y la subida; por lo tanto tenemos más velocidad.
![[Pasted image 20241107051244.png]]
Esto permitió
- VDSL 300MBPS/100MBPS

**HDSL (High bit rate Digital Subscriber Line)** #Skipea

#### Redes de acceso #IMPORTANTE
Para ofrecer los servicios de banda ancha antes citados, se hizo necesario el despliegue de nuevas redes de comunicaciones basadas en el cable coaxial y en la fibra óptica.
![[Pasted image 20241107051533.png]]

**Tecnología PON:**
Son redes de fibra óptica que no utilizan ningún otro dispositivo activo entre la central y el terminal. Permite compartir una misma fibra entre múltiples usuarios con múltiples servicios.
Se compone de:
- Un terminal de línea óptica – OLT (Optical Line Terminal) 
- Varios dispositivos de división óptica pasivos – Splitter 
- Varias terminales de red óptica – ONU (Optical Network unit)![[Pasted image 20241107051724.png]]

![[Pasted image 20241107051758.png]]

Algunas configuraciones quedan ahí para ver, pero son lo mismo casi todas, no está de más leerlas. #IMPORTANTE
