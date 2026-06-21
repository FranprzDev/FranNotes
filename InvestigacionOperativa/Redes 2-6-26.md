![[Pasted image 20260602174753.png]]
Red realizada:


## Consignas:

Preguntas: Segun esta red:
1) Topología física
2) Topología Lógica
3) Elementos constitutivos de la red
4) Armar la tabla Mac del Switch 1
    Teniendo en cuenta las siguientes acciones:
        a) PC1 envia a PC11
        b) PC2 envia a PC20
        c) PC20 envia a PC1
        d) PC11 envia a PC10
5) ¿Dónde se crean los usuarios y los grupos de usuairos del dominio? 


## Resolución

Esto que está dibujadio representa una red LAN basada en un sistema operativo del tipo DEDICADO (Osea es una red de servidor dedicado),
no es por lo único que haga cumplir el rol del servidor, si no que se dedica a administrar o generar las herramientas necesarias para que se administre de manera centralizada la red.

Active directory -> Base de datos que utiliza el sistema opreativo para la administración centralizada.

Nuestra red LAN está conectada con una red WAN.

Preguntas: Segun esta red:
1) **Topología física (forma que están conectados los nodos a la red)** 3 Switches y un Router | 20 PC | 1 Servidor => 20+3+1+1
	La Red tiene una topología física en estrella.
2) **Topología Lógica**
	Por no tener acceso a la placa de red, suponemos que es una topología lógica basada en una norma de comunicación como Ethernet, FastEthernet, GigabitEthernet
	Quien lo determina son los protocolos de acceso al medio que tienen, y estos corren en la propia placa de red.
3) **Elementos constitutivos de la red**
	Los elementos consitutivos de esta red son:
		a) Los dispositivos finales son las PC de la 1 a la 20
		b) El servidor principal es el dispositivo final que provee los servicios centralizados a la red
		c) Los switches de acceso, 1 y 2
		d) El swithch principal, este actua como switch de distribución nucleo local que interconecta los otros switches
		e) El router que interconecta la red local con las redes externas (Wan)
		f) Internet la red externa WAN a la cual se accede a través del router
		g) Medio de transmisión: Las líneas de conexión, el cableado físico, como tiene topología fisica a partir de la norma comunicación del paso anterior podemos deducir que tiene "par trenzado" cat5 superior (cat5e)
		h) Placas de red que tiene cada uno de los nodos (junto con sus estándares)
		i) Los distintos sistemas operativos (en el servidor, y en las PC para poder conectarse con el servidor) 
4) **Armar la tabla Mac del Switch 1 (Inunda, aprende)**
    Teniendo en cuenta las siguientes acciones:
        a) PC1 envia a PC11
        b) PC2 envia a PC20
        c) PC20 envia a PC1
        d) PC11 envia a PC10
	
	Pasos para armar la tabla:
	1) Armar una tabla donde tenga el puerto cada dispositivo
	2) La identificación del dispositivo (osea la mac)
		(Hablando a nivel de la capa de enlace)  
		![[Pasted image 20260602174929.png]]

	En el punto d: Se actualiza el puerto "X"
	![[Pasted image 20260602182312.png]]


**Sobre lo que escribimos en el otro bloc de notas (como se va inundando paso a paso)**

![[Pasted image 20260602175243.png]]

**Primero: PC1 -> PC11**
a) ¿En mi tabla mac está la PC11? -> La tabla está vacía
b) Inundo al resto de los puertos (PC1 - PC10 | PCX)
c) Aprendo (agrego al Puerto 1 a la tabla y vinculo con PC1)

**Segundo: PC2 -> PC20**
a) Inundo todo
b) Aprendo el puerto de la PC2

![[Pasted image 20260602175305.png]]

**Tercera: PC20 -> PC1**
a) Envio directo al P1 (ya tengo la dirección guardada)
b) Aprendo el puerto X


Dirección Origen | Dirección destino | Datos
PC11		           | PC10		        | ...
Cuarto: PC11 -> PC10
a) Inundo desde el Switch 1 **(Al inundar ya envía)**
b) Aprendo PC11 (Puerto X) 
	Se agrega en la Tabla MAC

## Aclaración de la profesora:
Si el analisis es sobre el switch principal, este irá construyendo su tabla MAC, aprendiendo y vinculando de acuerdo a las tramas que le lleguen. El puerto X podra estar vinculado con  las direcciones Mac que provengan de ese puerto y el puerto Y con las direcciones que provengan de ese puerto.



