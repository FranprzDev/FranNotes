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
