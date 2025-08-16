# Clase 1

La palabra lenguaje tiene su origen en el término **lenguagtge**, sus significados son:
- Facultad del ser humano de expresarse y comunicarse con los demás a través del sonido articulado o de otros sistemas de signos.

## Introducción al Lenguaje
**Signo** algo que evoca o representa una cosa o concepto.
Pueden tener distintos tipos.
- **Sin intención comunicativa:** No existe la pareja emisor-receptor
	- **ÍNDICE** son signos que dan indicios de alguna entidad o hecho.
- **Con intención comunicativa:** Hay un emisor-receptor del mensaje
	- **ÍCONO** son signos que por sus aspectos se asemejan a lo que representan
	- **SÍMBOLO** Son signos meramente convencionales que no guardan ningún parecido con lo que representan.

### Tipos de Lenguaje
**Formal:** 
- Se formaliza antes de usar
- No es ambiguo
- De dominio específico
- Para humanos y/o máquinas
- Ej: Programación, Música, etc.
**Natural**
- Se usa antes de formalizar
- Es ambiguo
- De dominio general
- Para humanos
- Ej: Oral, Escrito, Lenguaje de Señas.

### Niveles de un Lenguaje
Existen 4 dimensiones del lenguaje, para que así podamos analizar de manera correcta un texto escrito en un lenguaje determinado.
- **Nivel Léxico**
	Es la dimensión del lenguaje que trata sobre la relación entre los símbolos que representan las distintas palabras que se utiliza para formar una frase válida. Es lo que llamamos diccionario. Cada palabra se forma por un componente léxico.
- **Nivel Sintáctico**
	Es la dimensión del lenguaje que estudia la forma en la que se organizan los componentes léxicos para formar una frase válida, es decir la estructura de la secuencia de componentes que conforman dicha frase. 
	Este nivel es independiente del contexto, tanto en los lenguajes naturales como en los formales.
- **Nivel Semántico**
	Es la dimensión del lenguaje que analiza el significado o connotación de los componentes léxicos y de las frases válidas que se pueden formar con ellos. En el caso de lenguajes formales, la semántica es simple; ya que no hay duda que "eso" significa exactamente lo que dice, no pasa lo mismo con los lenguajes no formales.
- **Nivel Pragmático**
	Es la dimensión que trata sobre hechos o acciones que evocan las frases, tiene en cuenta el contexto donde se aplica el lenguaje; por lo tanto es dependiente del mismo. Es complicado, por que una misma frase podría significar hechos totalmente distintos.


# Clase 2

## Alfabeto
Es un conjunto finito no vacío de símbolos diferentes, lo denotamos con la letra $\Sigma$, por ejemplo el alfabeto binario es $\Sigma = \{1,2\}$ 
Un conjunto de símbolos es lo que llamamos **datos**
La información son un conjunto de **datos significativos**
Un símbolo se compone de un significante que es la imagen gráfica con la que representamos y de un significado, que es el concepto asociado.
**Palabra:** secuencia finita de símbolos pertenecientes aun alfabeto.
La palabra vacía se representa con lambda $\lambda$, y es aquella secuencia que no tiene símbolos.
$\Sigma*$ representa el conjunto de todas las palabras formadas por los símbolos de dicho alfabeto. (Es el conjunto universal)
$\Sigma+$ representa al Conjunto Universal sin la palabra vacía

## Lenguajes Formales
El lenguaje es cualquier subconjunto L del Conjunto Universal de palabras sobre un alfabeto $\Sigma$
Podemos decir que $L \subseteq \Sigma*$ 
El lenguaje universal entonces será $\Sigma*$
El lenguaje vacío será $\Phi$
El lenguaje $L\lambda = \{\lambda\}$ 

## Operaciones con palabras
### Concatenación
Es una función con dominio $\Sigma* \ x \ \Sigma*$ y rango $\Sigma *$, Tal que dadas las palabras u y v la concatenación de u con v da como resultado la palabra w formada por la secuencia de símbolos de u seguida por la secuencia d esímbolos de v.
### Potenciación
Dada la palabra u y el número natural j, la potencias con base u y exponente j da como resultado la palabra w formada por una sucesión de j veces la palabra u

### Longitud
Tal que dada la palabra u la longitud de u da como resultado la cantidad de símbolos que forman la palabra.

### Inversa
Tal que dada la palabra u la inversa de u da como resultado la imagen especular de u, es decir la imagen reflejada de un objeto, que parece casi idéntica pero está invertida al revés.

## Operaciones con Lenguajes

### Unión
Dados dos lenguajes L1 y L2, la unión enter L1 y L2 será el lenguaje L3 formado por todas las palabras de L1 y todas las palabras de L2 sin repeticiones.

### Diferencia
Tal que dado los lenguajes L1 y L2, la diferencia entre L1 y L2 da como resultado L3 formado por todas las palabras de L1 excepto aquellas que pertenezcan también a L2

### Intersección
Dado los lenguajes L1 y L2, la intersección de L1 y L2 da como resultado otro lenguaje L3 formado por todas las palabras que pertenecen a L1 y que también pertenecen a L2.

### Complemento
Dado el lenguaje L1, el complemento de este lenguaje es L3 formado por toads las palabras que pertenecen al universo ($\Sigma*$) y que no pertenecen a L1.

### Producto o Concatenación
Dado L1 y L2 se obtiene L3 formado por todas las palabras que resultan de concatenar una palabra de L1 con una palabra de L2 y solo en ese oredn.

### Potenciación
Dado L1 y el número natural i mayor igual que 2, da como resultado el lenguaje L3 formado por el producto de L1 consigo mismo (i-1) veces

### Clausura o estrella de Kleene
Tal que dado L1, la operación "L1 estrella" da como resultado L3, formado por todas las potencias de base L1 y exponente i, desde i igual a cero hasta infinito.
Es decir
$L_1* = L_1^0 \cup L_1^1 \cup L_1^2 \cup ... \cup L_1^n$ 
Tiene propiedades interesantes como por ejemplo:
- $(L_1^*)*=L1^*$
- $\Phi^* = L\lambda$ y $L\lambda^* = L\lambda$ 

### Estrella Positiva
Dado L1, "L1 estrella positiva" da L3 formado por todas las potencias de base L1 y de exponente i, desde i igual a uno hasta infinito.
Esto quiere decir que no incluye la vacía.
$L_1* = L_1^1 \cup L_1^2 \cup ... \cup L_1^n$ 
Mismas props.

### Inversa
Tal que dado L1, la inversa de L1 da como resultado otro lenguaje L3 formado por todas las inversas correspondientes a las palabras de L1.



# Clase 3

## Gramáticas estructuradas por frases

Se pueden definir por:
- **Definición por Extensión** Listado de las palabras del lenguaje
- **Definición por comprensión** Especificación de atributos de las palabras
- **Definición por patrones** Expresiones de palabras con parámetros
La gramática es el conjunto de reglas de formación junto con los símbolos utilizados.

## Definición formal de una gramática estructurada por frases

$$ G = < \Sigma_N \\, \Sigma_T \\, P \\, S>$$
- $\Sigma_N$ es el alfabeto de símbolos No-terminales o variables de la gramática
- $\Sigma_T$ es el alfabeto de símbolos terminales o símbolos del lenguaje
- P es el conjunto finito no vacío de Reglas de Producción de la forma:
				$\alpha \rightarrow \beta$   
	donde:
	$\alpha = \alpha_1N\alpha_2 \space con \space \alpha_1 \\, \alpha_2 \in \Sigma* \space N \in \Sigma_N \space \beta \in \Sigma*$    
- S es el símbolo inicial o axioma de la gramática.

Es importante que $\Sigma_N \space y \space \Sigma_T$ sean conjuntos disjuntos.

### Derivación de palabras a partir del axioma (S)
Podemos generar una palabra del lenguaje que describe una gramática comenzando por una regla que tenga el axioma a la izquierda y luego se continúa con el resto de las reglas que sean necesarias para llegar a la palabra.
Podemos decir que:
$S \rightarrow \alpha_1 \rightarrow \alpha_2 \rightarrow \space ... \space \alpha_n \rightarrow w$
Que equivale a decir $S \rightarrow *w$ 
Donde el operador de la flechita es la derivación, y la flechita estrellita es derivación a la larga.

### Forma Sentencial
Cualquier secuencia $\gamma~$ que se obtenga a partir del axioma en un proceso de derivación se denomina forma sentencial.
Una forma sentencial está compuesta por símbolos terminales, se denomina sentencia y constituye el final del proceso de derivación.
De aquí se desprende la idea de que:
- **Derivación más a la izquierda** Cuando se empieza a reemplazar la subsecuencia por la izquierda estamos ante este tipo de derivación.
- **Derivación más a la derecha** Cuando se empieza a reemplazar la subsecuencia por la derecha estamos ante este tipo de derivación

### Lenguaje generado por una gramática
El lenguaje generado por una gramática para estructuras de frases G detonado como L(G), es el conjunto definido como:
$$L(G) = {w / w \in (\Sigma_T^*) \space \\y \space S \rightarrow * w}$$
### Equivalencia entre gramáticas
Dos gramáticas G y G' se dicen equivalentes si y sólo si los lenguajes generados por ambas son iguales es decir.
$$ L(G) = L(G') \Leftrightarrow G \equiv G'$$  
### Jerarquía de Chomsky
Es una clasificación realizada por Chomsky, que implica una jerarquía de los lenguaje generados por las gramáticas de cada tipo, ya que una gramática del tipo X surge de aplicar ciertas restricciones al tipo anterior (X-1)
De este modo, queda organizado así
$$L_0 \supset L_1 \supset L_2 \supset l_3 \supset L_4$$


<table border="1" cellpadding="5" cellspacing="0">
  <thead>
    <tr>
      <th>Tipo</th>
      <th>Gramática</th>
      <th>Lenguaje</th>
      <th>Nivel Lingüístico</th>
      <th>Modelo Matemático</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Irrestricta (GI)</td>
      <td>Recursivamente enumerable (LI)</td>
      <td>Pragmático</td>
      <td>Máquina de Turing (MT)</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Dependiente del Contexto (GDC)</td>
      <td>Lenguaje Dependiente del Contexto (LDC)</td>
      <td>Semántico</td>
      <td>Autómata Linealmente Limitado (ALL)</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Independiente del Contexto (GIC)</td>
      <td>Lenguaje Independiente del Contexto (LIC)</td>
      <td>Sintáctico</td>
      <td>Autómata de Pila (AP)</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Regular (GR)</td>
      <td>Lenguaje Regular (LR)</td>
      <td>Léxico</td>
      <td>Autómata Finito (AF)</td>
    </tr>
  </tbody>
</table>

#### Tipo 0 (Irrestricta o Sin Restricciones -GI)
Está estructurada por frases sin ninguna restricción, es decir que sus reglas de producción tienen en la parte izquierda al menos un símbolo no terminal y en la parte derecha cualquier secuencia de terminales o no-terminales, inclusive vacía.
Todo lenguaje generado por una GI y que no puede ser generado por una gramática de menor jerarquía, se llama "**Lenguaje Irrestricto o Recursivamente Enumerable (LI)**"

#### Tipo 1 (Dependiente del / Sensible del Contexto GDC)
Es la gramática estructurada por frases cuyas reglas de producción se restringen en la longitud de su parte derecha, la cual no puede ser menor que la longitud de la parte izquierda, es decir que no tienen reglas compresoras; exceptuando la regla de borrado $S \rightarrow \lambda$, siempre y cuando S no figure a la derecha de ninguna regla y el objetivo de esto, es generar la palabra vacía.

#### Tipo 2 (Independiente / Libre del Contexto - GIC)
Gramática estructurada por frases cuyas reglas de producción se restringen en la longitud de su parte izquierda, que debe ser igual a 1. Es decir la parte izquierda es un no-terminal y la parte derecha puede ser cualquier secuencia de terminales o no-terminales.
Cualquier lenguaje formal que no puede ser generado por una gramática de menor jerarquía, se llama **Lenguaje Independiente del Contexto (LIC)** 

#### Tipo 3 (Lineal / Regular - GR)
Es una gramática estructurada por las reglas de producción que su parte izquierda debe ser igual a 1, y la parte derecha puede ser una secuencia de terminales con un no-terminal como sufijo (GR por derecha) o con un no-terminal como prefijo (GR por izquierda) o simplemente una secuencia de terminales.
Existe una equivalencia entre ambas formas.
Todo lenguaje formal generado por una GR por derecha se llama **Lenguaje Regular (LR)**


# Clase 5

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