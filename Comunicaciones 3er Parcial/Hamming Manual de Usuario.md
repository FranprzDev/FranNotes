# Hamming Paso a Paso
**Hecho por Francisco Miguel Perez - 56355 - Comunicaciones 3K2**

## Hamming:
El código Hamming es un sistema de detección y corrección de errores que fue desarrollado por Richard Hamming en 1950. Este código agrega bits de paridad a los datos para detectar y corregir errores que pueden ocurrir durante la transmisión o almacenamiento de información digital. La innovación clave del código Hamming es su capacidad para corregir automáticamente errores de un solo bit y detectar errores de dos bits, lo que lo hace especialmente útil en sistemas de comunicación y almacenamiento de datos donde la integridad de la información es crucial.
## Introducción
Este proyecto tiene la idea de poder ayudar a entender como funciona el algoritmo del código de hamming. Siguiendo los pasos de como se hace paso a paso.

## Descripción del Programa
El programa acepta como entrada hasta 10 caracteres (cualquiera) y estos serán convertidos a código de Hamming en el Emisor T(x) y serán transmitidos al receptor T'(x) donde anteriormente se podrá generar un error y el código muestra donde estará el error. Este programa está excepto a más de dos errores, y no se asegura su correcto funcionamiento en estos casos.

### Entrada de datos
Se pueden ingresar cualquier tipo de caracteres, hasta 10.

### Salida de Datos
Dependerá de la cantidad de bits de paridad que se agreguen y la entrada de datos. Como mínimo son **7 bits de datos** y por lo tanto **4 bits de paridad**. Como máximo son **70 bits de datos** por lo tanto serán **7 bits de paridad**. No es recomendable llevarlo a los máximos, ya que la tabla será totalmente ilegible y será poco eficiente para su uso, la recomendación está entre **1 y 3 caracteres**.
## Instalación del Proyecto

### Formas de usar el proyecto

#### Forma Web
Utilizando una web deployada en Vercel (Emp. Argentina) podemos correrlo de forma fácil solamente ingresando al link. https://hamming-step-by-step.vercel.app
##### Requisitos
- Contar con un navegador web, preferiblemente Chrome o variaciones de este (Mozilla Firefox, Edge, etc). Preferiblemente no utilizar Safari ni Internet Explorer.
#### Forma local
Ejecutar de manera local la web, así de esta forma poder utilizarlo sin conexión a internet (Para la instalación, si se debe poseer internet).

##### Requisitos
- Contar con un navegador web, preferiblemente Chrome o variaciones de este (Mozilla Firefox, Edge, etc). Preferiblemente no utilizar Safari ni Internet Explorer
- Tener instalado Visual Studio Code
- Tener instalado un empaquetador de paquetes de javascript (npm)

##### Paso a paso para la instalación
1) Descargar git, https://git-scm.com/downloads (Elegir el sistema operativo y la versión en bits que corresponda). (OPCIONAL)
2) Abrir git bash o una consola de comandos para poder ejecutar lo siguiente:
	1) git clone https://github.com/FranprzDev/HammingStepByStep.git
	2) cd HammingStepByStep
	3) code .
3) Ejecutar los siguientes comandos en la consola de visual studio code (CTRL + Ñ) donde está el proyecto.
	1) npm install
	2) npm run dev
	3) Ir a [http://localhost:5173/](http://localhost:5173/) (o el localhost con el puerto que lo tengamos configurado, la misma consola lo indica).
4) Disfrutar!

## Ejemplo de Uso

Por alguna razón quiero transmitir mi nombre **francisco** y para esto, tengo que asegurar que llegue bien y sin errores, por ello entonces primero tendré que cambiar cada letra de mi nombre por código ascii, luego pasarlo a binario y proximamente juntar toda la cadena.

Esto quedará de la siguiente forma:
![[Pasted image 20241205232821.png]]

Al hacer click en **"Codificar Hamming"** nos llevará a la sección donde podremos calcular la cantidad de **bit de paridad** que necesitaremos con la formula que se indica ahí..
Podremos sumar 1 en la cantidad de bits de paridad o podemos llegar directamente a p, según lo que elijamos habrá más pasos.
Entonces nos quedará de la siguiente forma:
![[Pasted image 20241205234023.png]]

Ahí podremos ver, cuantos bits de paridad necesitaremos; en este caso serán 7, ya que se cumple la igualdad de la formula.
Seleccionaremos **'Ir a la Tabla'**
Donde podremos ver como se codificará la secuencia de digitos binarios agregándole los bits de **paridad p**, mediante un algoritmo específico.

Si le damos al botón **terminar codificación** se hará mucho más rápido, y la última línea es la que muestra la codificación de hamming, agregándole los bits de paridad respectivos.
![[Pasted image 20241205234228.png]]

Proximamente, al darle terminar de transmitir tendremos otro botón donde podremos clickear **Transmitir** para así de este modo llevarlo al Emisor, antes de esto nos dará un aviso para saber cual es la cadena que transmitiremos. Al darle click en continuar; nos mostrará la secuencia que transmitiremos y podremos seleccionar algún bit especifico (haciendo click sobre este bit) para forzar un error en el transmisor.
![[Pasted image 20241205234719.png]]
Como se muestra en la imagen se puede reproducir un error en cualquier bit, y de este modo al darle a **"Ir a la tabla"**, luego de esto nos mostrará la tabla del lado del receptor, donde podremos ver exactamente cuales son los errores que agregamos a la secuencia; de este modo mostraremos una nueva tabla, que es la tabla del lado del receptor; en este caso la tabla del receptor será la siguiente:
![[Pasted image 20241206000850.png]]

Donde se mostrará que hubo un error, ya que habíamos forzado este error; y nos mostrará específicamente la posición de este error, tanto en binario como en decimal.

## Conclusiones

Este proyecto sirvió para aprender más acerca de Hamming, y para ayudar a las próximas personas que cursen la **materia de Comunicaciones** aportando un método efectivo para el cálculo y demostrando los conocimientos adquiridos durante la cursada.