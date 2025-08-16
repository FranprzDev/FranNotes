# Manual de Usuario
![[Pasted image 20241122015834.png]]
## Formas de usar el proyecto:
- Forma Web: 
	- Ingresar al siguiente link (https://transmission-mode.vercel.app)
- Forma local: (Leer los siguientes requisitos).
## Requisitos
- Es necesario tener instalado Node.js en una versión actual para poder correr el proyecto en local.
- Es necesario tener descargado Git en la computadora.
- Es necesario tener el 'git bash' en nuestra computadora.
- Es necesario tener espacio de almacenamiento.
- Es necesario tener visual studio code descargado.

## Paso a paso para descargar el proyecto desde github.
1) Ingresar a una terminal de bash ya sea de gitbash, cmd, powershell, o cualquier otro parecido.
2) Si no tenemos git descargado, no nos funcionará; es importante tenerlo.
3) Ejecutar los siguientes comandos:
	1) git clone https://github.com/FranprzDev/TransmissionMode
	2) cd TransmissionMode
	3) code .
4) Esto nos abrirá github, donde cerraremos la pestaña actual de la línea de comandos y apretaremos la extensión **Ctrl + Ñ** para abrir la terminal integrada de VSC. Ahí pondremos el siguiente comando:
	1) npm install
		1) Esperaremos a que termina de instalar todo los modulos y proximamente ejecutaremos:
		2) npm run dev
5) Debemos abrir una pestaña en localhost:3000 (Es el puerto por defecto para páginas webs, pero está sujeto al equipo).

## Limitaciones:

El proyecto solo muestra los tipos de transmisión de datos (Simplex, Half-Duplex y Full-Duplex); y de una forma divertida; y animada como estos funcionan; no tiene más funcionalidad que enseñar a los nuevos alumnos de comunicaciones como esto funcionan de una manera interactiva.