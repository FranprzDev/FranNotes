# Máquina de Turing (MT)
La MT fue concebida por Turing en el 36, como un modelo matemático abstracto que representa la solución de cualquiera problema algorítmico y en particular el reconocimiento de lenguajes de Tipo 0 o Irrestrictos.

El modelo dispone de una **cinta infinita** dividida en casilleros que pueden contener un símbolo cada uno. Un **cabezal de lectura y escritura** sobre la cinta. Un **control** que puede responder de distintas formas según el **estado** en el que se encuentre.

Al comienzo la cinta está llena de espacios en blancos $\Delta$ y se escribe la palabra que se desea analizar $e_i$, el cabezal estará en la posición del primer símbolo de la palabra, en este caso se dice que el control se encuentra en el **ESTADO INICIAL**

A partir del estado inicial el modelo comienza a funcionar realizando las siguientes acciones

1) **Lee** un símbolo
2) De acuerdo al **estado actual** y al símbolo leído
	1) **ESCRIBE** otro símbolo (que puede ser el mismo)
	2) **MUEVE** el cabezal un lugar hacia la derecha o izquierda, eventualmente puede no moverse.
	3) **TRANSICIONA** a un **NUEVO ESTADO** (que puede ser el mismo)
3) Repite 1 y 2 hasta que llega a alguno de los llamados **ESTADOS FINALES** en este caso, se dice que la palabra escrita inicialmente es **ACEPTADA**, o hasta que se llega a un estado en el que no está definida una transición para el símbolo leído, en este caso se produce un **BLOQUEO** y la secuencia de entrada es **RECHAZADA** 

## Definición formal de la MT

$$
MT = <Q, \Sigma_E, \Sigma_A, q_0, F, f>
$$
Donde:
- $Q$ Conjunto finito y no vacío de estados
- $\Sigma_E$ Alfabeto de símbolos de entrada
- $\Sigma_A$ Alfabeto de símbolos auxiliares (incluye a "$\Delta$")
- $q_0$ Estado inicial perteneciente a Q
- $F$ Conjunto de estados finales, incluido en Q
- $f$ Función de transición
Donde $f$ se define como:

$$
f: (Q-F) \times (\Sigma_E \cup \Sigma_A) \Rightarrow Q \times (\Sigma_E \cup \Sigma_A) \times {I,N,D}
$$
Donde los simbolos I, N y D representan los movimientos del cabezal de lectura escritura sobre la cinta, hacia la izquierda, nulo y hacia la derecha respectivamente.
El domino no incluye a $F$, es decir que los estados finales son de parada; todos los símbolos se pueden leer y escribir, pero inicialmente solo hay espacios en blanco y una secuencia de símbolos de entrada.

Según Turing $\Sigma_E^*$ queda divido en tres subconjuntos
- Todas las palabras aceptadas por la MT
- Todas las palabras rechazadas por la MT
- Aquellas palabras que hacen que la MT no se detenga, es decir que ni se acepta ni se rechaza.

Esto implica que todo LI tiene asociado una MT que es capaz de reconocerlo, pero qeu su completo **NO SIEMPRE**

La representación formal se hace por medio del par **(estado actual, símbolo de entrada)** y la terna **(estado nuevo, símbolo de salida, movimiento)** 

En el caso de la MT se puede afirmar que se trata de un modelo DETERMINISTA por naturaleza, es decir que para toda MT ND existe una MT determinista equivalente.

## Configuración de una MT
Es una descripción instantánea de una MT requiere las siguientes especificaciones
- Estado actual del a MT
- Contenido de la cinta
- Posición del Cabezal
Esta terna es la **configuración** de la MT y vamos a representar con la secuencia de símbolos que hay en la cinta antes de la posición del cabezal 
$$
\Delta c_1 \dots c_{i-1} q_kc_i \dots c_n \Delta 
$$

Se define el operador $⊢$ como el operador de transformación directa de una configuración a otra, que implica el paso de un paso de $C_1$ a $C_2$, mediante la aplicación de la función de transición $f$ una sola vez; y en el caso de que se realicen varios se define como:
$$C_1 ⊢^* C_2
$$
Una secuencia de varias configuraciones consecutivas se llama **SECUENCIA DE CONFIGURACIÓN DE LA MT**

## Lenguaje aceptado por una MT
Se define el lenguaje aceptado como el conjunto de palabras que partiendo de una configuración inicial llegan a una configuración que contiene un estado final de la MT.

$$
L(MT) = \{w / w \in \Sigma_E^* \space y \space \Delta q_0w \Delta ⊢^* \Delta \beta_1 q_F \beta_2 \Delta \space y \space q_F \in F \}
$$
Todas aquellas donde se bloquea, entonces esas palabras son rechazadas.

## Autómata Linealmente Limitado (ALL)
Es una MT que tiene restringida la longitud de su cinta, limitandose a la longitud de la secuencia de entrada inicial. Este modelo matemático abstracto representa la solución del problema de aceptación de lenguajes de Tipo 1 o LDC.

El modelo es igual a la MT pero dispone de una **cinta finita**, al comienzo se escribe la palabra $e_i$ el cabezal de lectura-escritura se encuentra en la primera posición, donde está el símbolo inicial de la palabra; se dice que el **control** está en el **estado inicial**. Automáticamente se coloca en los extremos los parentesis angulares $< \space y \space >$ a la izq y derecha respectivamente, actuando como límites para el desplazamiento del cabezal, de tal modo que no se pueden desplazar más a la izquierda o derecha que ellos, es el tope.

### Definición formal
$$
ALL = < Q, \Sigma_E, \Sigma_A, q_0, F, f >
$$
Donde:
- $Q$ Conjunto finito y no vacío de estados
- $\Sigma_E$ Alfabeto de símbolos de entrada
- $\Sigma_A$ Alfabeto de símbolos auxiliares, incluyendo a $< \space y \space >$ 
- $q_0$ Estado inicial, perteneciente a $Q$
- $F$ Conjunto de estados finales, incluido en $Q$
- $f$ Función de control
La función se define como:
$$
f : (Q-F) \times (\Sigma_E \cup \Sigma_A) \Rightarrow Q \times (\Sigma_E \cup \Sigma_A) \times \{I,N,D\}
$$
Donde:
$$
\forall q \in (Q-F) \space y \space q' \in Q:
$$
- $f(q,<) = (q', <, D)$
- $f(q, >) = (q',>,I)$
El dominio no incluye a F, es decir que los estados finales son de parada; todos los simbolos se pueden leer y escribir; pero inicialmente solo se encuentra la secuencia de entrada delimitada por los parentesis angulares.

En este caso, el lenguaje de entrada $\Sigma_E^*$, quedará dividido en:
- Todas las palabras aceptadas por el ALL
- Todas las palabras rechazadas por el ALL

Es decir, para todo LDC existe un ALL que es capaz de aceptarlo y a la vez rechazar su complemento, esto quiere decir que el problema de reconocimiento de LDC siempre tiene solución.

La representación es la siguiente:
- **El par** $(estado \space actual, \space símbolo \space de \space entrada)$
- **La terna** $(estado \space nuevo, \space símbolo \space de \space salida, \space movimiento)$

La relación de transición puede ser **determinista o no-determinista**, pero naturalmente el **ALL** es **determinista por naturaleza**
Aún no se demuestra que para todo ALL ND existe un ALL Determinista equivalente, pero es la creencia más común.

Tienen los mismos conceptos de **configuración, secuencia de configuración y lenguaje aceptado** de una MT.

## MT Transformadora de secuencias

Se puede ver a la MT como un **modelo general de procesamiento de datos** capaz de realizar cualquier transformación sobre una secuencia inicial y obtener una secuencia final que cumpla ciertas condiciones.

La secuencia inicial son los **datos de entrada** y la secuencia final los **datos de salida o resultado de un problema algorítimico**

En estos casos la **aceptación de la secuencia inicial** se puede interpretar como la **validación de los datos de entrada**, ya que si no son validos se rechazan.