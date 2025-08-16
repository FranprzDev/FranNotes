## Proceso de Compilación

### Traductor
Se define como un programa que traduce o convierte desde un texto o programa escrito en un lenguaje fuente hasta un texto o programa equivalente en un lenguaje destino, produciendo si existe un error.
Existen distintos tipos de traductores
- **Preprocesadores**
	Permite modificar el programa fuente antes de la verdadera compilación.
- **Compiladores**
	Es aquel traductor que tiene como entrada sentencias de un lenguaje formal y como salidas un fichero en un lenguaje de bajo nivel, es decir de lenguaje de alto nivel a código máquina.
- **Interpretes**
	Es un traductor que toma como entrada sentencias escritas en un lenguaje formal y como salida las ejecuta sin almacenarlas, es decir traduce sentencia por sentencia y las ejecuta sin crear un archivo donde se guarde.
- **Pseudo interepretes**
	El código fuente pasa por un pseudocompilador que genera un pseudoejecutable, para esto utilizan un motor de ejecución como lo es Java.
- **Interpretes de comandos**
	Traduce sentencias simples o invocaciones a programas de una biblioteca, utilizado por ejemplo en la shell de linux con el comando **cd**
- **Ensambladores**
	Es un compilador sencillo, en el que el lenguaje fuente tiene una estructura simple que permite la traducción de cada sentencia fuente a una única instrucción  en código máquina. Ej: mandarlo en assembler, **MOV**
- **Transpiladores**
	Permiten traducir de un lenguaje de alto nivel a otro lenguaje de alto nivel, así consiguiendo portabilidad entre lenguajes. Por ejemplo **TypeScript**
- **Traductores de idioma**
	Son traductores de lenguajes naturales, es decir tienen como entrada un texto escrito en un idioma y como salida un texto escrito en otro idioma.

### Fases de ejecución 
#### Compilación
Un compilador no suele producir un fichero ejecutable, sino que el código se estructura en modulos que se almacena en un fichero de tipo objeto (.obj), estos poseen infromación relativa tanto al código máquina como a una tabla de símbolos que almacena la estructura de las variables y tipos utilizados por el programa
![[Pasted image 20250622222545.png]]
#### Enlace
Es un único bloque que **unifica todos los módulos** generados por el compilador y las integra en un único bloque coherente código máquina, además **organiza el espacio en memoria** que se utilizará para la ejecución, y es el encargado de generar el **ejecutable final** 
![[Pasted image 20250622223006.png]]
#### Carga
El cargador que es parte del S.O coloca diferentes segmentos del fichero ejecutable en las direcciones de memoria disponibles, de tal modo que las direcciones relativas del código se le suma la dirección base del segmento correspondiente, y así obteniendo los valores que tomará el procesador para acceder una variable o realizar una acción.
![[Pasted image 20250622223111.png]]