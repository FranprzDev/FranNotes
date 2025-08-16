# Clase 39

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


# Clase 41

# Construcción de una MT
## Composición de MT

Sea $MT_1 \space y \space MT_2$ dos MT sobre el mismo alfabeto de entrada $\Sigma_E$ y el mismo alfabeto auxiliar $\Sigma_A$  donde:
$$
 MT_1 = <Q_2, \Sigma_E, \Sigma_A, q_{01}, F_1, f_1>
$$
$$
	MT_2 = <Q_2, \Sigma_E, \Sigma_A, q_{02}, F_1, f_1>
$$
Con $Q_1 \space y \space Q_2$ disjuntos, la composición de estas dos máquinas generará una $MT_3$ tal que:

$$
MT3 = < Q_1 \cup Q_2, \Sigma_E, \Sigma_A, q_{01}, F_2, f_3 >
$$
Donde $f_3(q,e)$ sucederá:
- $f_1(q,e) \space si \space q \in Q_1 \space y \space f_1(q,e) \neq (p, s, m) \space \forall p \in F_1$
- $f_2(q,e) \space si \space q \in Q_2$
- $(q_02, s, m) \space si \space q \in Q_1 \space y \space f_1(q,e)=(p,s,m) \space y  \space p \in F_1$

Osea:
- Si está dentro del espacio de la MT1, con excepción del estado final
- Si está la MT2
- Si es el estado final.

Entonces, aquí es donde podemos usar como plantillas de máquinas de turing simples y las vamos combinando según necesitamos, al estilo de thompson.
![[Pasted image 20250727051229.png]]
![[Pasted image 20250727051234.png]]
Ejemplo:
![[Pasted image 20250727051244.png]]

## Variantes de la MT
Con el objetivo de resolver problemas más complejos se pueden plantear variaciones de la MT. Las mas comunes se encuentran la **MT Multicinta y la MT Multiplista**.

La MT multicinta consta de N cintas infinitas con N cabezales independientes de tal modo que inicalmente se escriben secuencias de entrada en las N cintas y los cabezales comienzan en una posición determinada de las cintas, normalmente en el extremo izquierdo.
El control de cada uno de los cabezales requiere una func de transición independiente, similares a una MT de una sola cinta. 
Esto quiere decir que:
$$
MT_{multicinta} = <Q, \Sigma_E, \Sigma_A, q_0, F, f>$$
Donde $f$ resulta en varias funciones de transiciones dependiendo de a que cinta se apunte.

La MT multipista, la única diferencia es que los cabezales están restringidos a realizar todos juntos el mismo movimiento.

## Aceptores del lenguaje

### Comprobación de pertenencia
La comprobación de pertenencia responde al problema de verificar si una palabra **w** está incluida en un lenguaje que genera una gramática **G**.
Se puede afirmar que este problema tiene solución para los lenguajes de Tipo 1, 2 y 3.
Sin embargo, para los lenguajes de tipo 0 o LI no existe un algoritmo general que permita comprobar la pertenencia de una palabra **w** a un lenguaje generado por una gramática irrestricta.

La dificultad está en las gramáticas irrestrictas en la permisividad de las reglas compresoras; específicamente cuando se desea obtener todas las palabras de longitud menor o igual a **N**. En este caso las secuencias pueden ir disminuyendo de longitud, entonces no se sabe con seguridad cuando terminar el proceso; y de esta forma entrar en un posible lazo infinito.

Esto es justamente lo que se llama **"PROBLEMA DE LA PARADA DE LA MT"** **(The Halting Problem)** que constituye el primer problema sin solución algorítmica demostrable

## Problema de la parada de la MT
### 1. **¿Qué es el problema de la parada?**
El **problema de la parada** (*halting problem*) pregunta si existe un algoritmo que pueda determinar, para cualquier **Máquina de Turing (MT)** \( M \) y entrada \( w \), si \( M \) se detiene (termina su ejecución) o sigue indefinidamente. Su lenguaje asociado es:
$$
L_{\text{parada}} = \{ \langle M, w \rangle \mid M \text{ es una MT y } M \text{ se detiene en } w \}
$$


Es un lenguaje **recursivamente enumerable** (Tipo 0 en la jerarquía de Chomsky), pero **indecidible**.

### 2. **¿Qué quiso demostrar Turing?**
Alan Turing quiso demostrar que **no todos los problemas computacionales son decidibles**, específicamente que no existe una Máquina de Turing que pueda resolver el problema de la parada para cualquier entrada. Esto establece un límite fundamental en la computación, mostrando que hay preguntas sobre programas que no pueden responderse algorítmicamente.

### 3. **¿De qué trataba el problema de Entscheidungsproblem?**
El **Entscheidungsproblem** ("problema de decisión") fue propuesto por David Hilbert y Wilhelm Ackermann en 1928. Se preguntaba si existe un algoritmo general que pueda determinar si una afirmación en lógica de primer orden es universalmente válida (verdadera en todos los modelos). Turing usó el problema de la parada para demostrar que el Entscheidungsproblem es indecidible, ya que resolverlo implicaría resolver problemas indecidibles como el de la parada.

A continuación, reescribo la sección de la **demostración de la indecidibilidad** del problema de la parada, incorporando expresiones matemáticas en formato LaTeX donde corresponda, siguiendo tu instrucción. Cada expresión matemática estará encerrada en símbolos de dólar (\$) para indicar que es una expresión matemática, como es estándar en LaTeX.

### 4. **Demostración de la indecidibilidad (paso a paso)**
Turing demostró que el problema de la parada es indecidible mediante una **prueba por contradicción**:

1. **Suposición**: Supongamos que existe una Máquina de Turing $H$ que decide el problema de la parada. Para cualquier entrada $\langle M, w \rangle$, donde $\langle M, w \rangle$ es la codificación de una Máquina de Turing $M$ y una entrada $w$:
   - $H$ acepta si $M$ se detiene en $w$, es decir, $H(\langle M, w \rangle) = \text{acepta}$.
   - $H$ rechaza si $M$ no se detiene en $w$, es decir, $H(\langle M, w \rangle) = \text{rechaza}$.

2. **Construcción de $D$**: Se crea una nueva Máquina de Turing $D$ que toma como entrada la codificación de una Máquina de Turing $\langle M \rangle$ y opera como sigue:
   - Ejecuta $H(\langle M, \langle M \rangle \rangle)$, es decir, evalúa si $M$ se detiene cuando se le da su propia codificación $\langle M \rangle$ como entrada.
   - Si $H(\langle M, \langle M \rangle \rangle) = \text{acepta}$ (i.e., $M$ se detiene en $\langle M \rangle$), entonces $D$ entra en un bucle infinito.
   - Si $H(\langle M, \langle M \rangle \rangle) = \text{rechaza}$ (i.e., $M$ no se detiene en $\langle M \rangle$), entonces $D$ se detiene.

3. **Paradoja**: Ejecutamos $D$ con su propia codificación $\langle D \rangle$:
   - Si $D$ se detiene en $\langle D \rangle$, entonces $H(\langle D, \langle D \rangle \rangle) = \text{acepta}$, lo que implica que $D$ debería entrar en un bucle infinito (contradicción).
   - Si $D$ no se detiene en $\langle D \rangle$, entonces $H(\langle D, \langle D \rangle \rangle) = \text{rechaza}$, lo que implica que $D$ debería detenerse (contradicción).

4. **Resultado**: La suposición de que existe una Máquina de Turing $H$ que decide el problema de la parada lleva a una contradicción. Por lo tanto, no puede existir tal $H$, y el problema de la parada es indecidible.


### 5. **Ejemplo en código Python**
No podemos implementar un solucionador general del problema de la parada (porque es indecidible), pero podemos ilustrar la idea de la paradoja con un código Python que simula el razonamiento de Turing. Este código muestra cómo la existencia de un supuesto "decisor" lleva a una contradicción:

```python
def halts(program, input):
    # Suponemos que existe una función que decide si 'program' se detiene en 'input'
    # En la realidad, esta función no puede existir
    # Aquí simulamos una lógica simple (esto es solo ilustrativo)
    pass  # No implementable en general

def diagonal(program):
    # Implementa la máquina D: toma la codificación de un programa
    if halts(program, program):  # Si el programa se detiene en sí mismo
        while True:  # Entra en un bucle infinito
            pass
    else:  # Si no se detiene
        return  # Se detiene

# Simulamos la paradoja ejecutando diagonal con sí mismo
def main():
    # No podemos ejecutar diagonal(diagonal) directamente en Python,
    # pero el código ilustra que si 'halts' existiera, llevaría a una contradicción
    print("Si halts(diagonal, diagonal) dice que se detiene, diagonal entra en bucle.")
    print("Si halts(diagonal, diagonal) dice que no se detiene, diagonal termina.")
    print("Esto es una contradicción, por lo que halts no puede existir.")

if __name__ == "__main__":
    main()
```

**Explicación del código**:
- La función `halts(program, input)` representa la hipotética Máquina de Turing \( H \) que decide si un programa se detiene. En la realidad, no puede implementarse.
- La función `diagonal(program)` simula la máquina \( D \), que usa `halts` para crear una contradicción.
- Al intentar ejecutar `diagonal` con su propia codificación, se produce una paradoja lógica, mostrando que `halts` no puede existir.
- En Python, no podemos codificar programas como entradas de manera directa como en una MT, pero el código ilustra la idea de la contradicción.

### 6. **Relación con el Entscheidungsproblem**
Turing relacionó el problema de la parada con el **Entscheidungsproblem** al mostrar que si pudiéramos resolver el problema de la parada, también podríamos resolver el Entscheidungsproblem (codificando afirmaciones lógicas como MTs). Dado que el problema de la parada es indecidible, el Entscheidungsproblem también lo es.

### 7. **Implicaciones prácticas**
- **Verificación de software**: No podemos crear una herramienta que garantice si cualquier programa termina.
- **Límites de la computación**: Hay problemas intrínsecamente irresolubles, incluso para sistemas avanzados como los LLMs.
- **Teoría de lenguajes**: El lenguaje del problema de la parada es de Tipo 0, pero su indecidibilidad lo distingue de lenguajes más simples.

## Aceptor de Lenguajes < 0
Se puede demostrar que siempre es posible resolver el problema de comprobación de pertenencia para GDC, GIC y GR, definiendo el siguiente algoritmo.

Dada una $G = <\Sigma_N, \Sigma_T, P, S> y una palabra $w$ con longitud $N$, ENTONCES:
1) $T_0 = {S}$
2) $T_k = T_{k-1} \cup \{\beta / |\beta| \leq N \space y \space \exists \alpha \in T_{k-1} \space y \space \alpha \Rightarrow \beta \}$
3) Repetir 2 hasta que:
	1) $T_k == {T_{k-1}}$
	2) $w \in T_k$

## Aplicación Resolubilidad y Complejidad
### Función Computable
Una función $f$ se dice Turing Computable, si para la misma existe una MT que es capaz de obtener el valor de $f(w)$ para todo $w \in domf$  
### Problemas de decisión
Son aquellos problemas cuyo resultado se puede representar con una función de rango binario con valores (falso / verdadero, si / no, 0 / 1)

## Resolubilidad o Decidibilidad
Cuando un problema de decisión es computable por una MT se dice que es decidible, de lo contrario se dice que es indecidible.
### Lenguajes Recursivamente Enumerables
Los lenguajes generados por GR de tipo 0, son los que son reconocidos como lenguajes recursivamente enumerables, debido a que sus palabras se pueden generar mediante la aplicación de reglas gramaticales recursivas sobre la cinta de una MT, esto a su vez permite que una MT sea capaz de reconocer las palabras, por lo que se dice que son **"aceptables"**.
Pero, existen secuencias del universo del lenguaje aceptado que pueden producir un bucle infinito, **esto significa que los complementos de algunos LRE no son aceptables por una MT, y por lo tanto no son LRE.**

## Lenguajes Recursivos
Los LRE cuyos complementos también son LRE son conocidos como **LENGUAJES RECURSIVOS**. Estos lenguajes son decidibles por una MT, ya que todas las palabras del universo provocan la detención o parada de la MT.
Osea, que el problema de decisión que plantea la pertenencia, siempre tiene solución algoritmica y por lo tanto es resoluble o decidible.
Por lo tanto, el conjunto de LDC (Tipo 1) es un subconjutno de los **Lenguajes Recursivos**

## Propiedades de los lenguajes aceptables y decidibles por MT

Los LRE son cerrados para las operaciones intersección, unión, concatenación y estrella de Kleene, no así para el complemento.

En el caso de los recursivos se puede demostrar que son cerrados para todas.

### Complejidad algorítmica
La complejidad de un algoritmo se puede medir en lo **temporal** y en lo **espacial**.
Desde un punto de vista teórico, la temporal se mide en la cantidad de pasos que lleva una MT asociada al algoritmo en detenerse.
Osea se cuentan los pasos que realiza la MT en función de la entrada n, identificando la función de crecimiento.

La complejidad espacial se mide en función de la cantidad de casilleros que utilizaria la MT para resolver un problema.