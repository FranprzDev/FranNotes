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