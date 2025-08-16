1) ¿Qué es la notación Big O y por qué es importante en el análisis de algoritmos?  
Big O describe el comportamiento del tiempo o el espacio de un algoritmo en función de la entrada, ayudando a medir su eficiencia.

2) ¿Qué significa O(1) en Big O Notation?  
O(1) indica que el tiempo o espacio requerido por el algoritmo es constante, independientemente del tamaño de la entrada.

3) ¿Qué significa O(n) en Big O Notation?  
O(n) significa que el tiempo o espacio requerido por el algoritmo crece linealmente en proporción al tamaño de la entrada.

4) ¿Qué significa O(n²) y cuándo suele encontrarse este tipo de complejidad?  
O(n²) indica que el tiempo o espacio crece cuadráticamente en relación con el tamaño de la entrada, común en algoritmos de fuerza bruta o de ordenación ineficientes como el bubble sort.

5) ¿Qué es O(log n) y en qué tipo de algoritmos suele aparecer?  
O(log n) representa una complejidad logarítmica, común en algoritmos que dividen la entrada en cada iteración, como la búsqueda binaria.

6) ¿Cuál es la diferencia entre O(n) y O(log n)?  
O(n) crece linealmente con el tamaño de la entrada, mientras que O(log n) crece mucho más lentamente, dividiendo la entrada en cada paso.

7) ¿Qué es O(n log n) y en qué contextos suele aparecer?  
O(n log n) es una combinación de crecimiento lineal y logarítmico, común en algoritmos de ordenación eficientes como merge sort y quicksort.

8) ¿Cómo se compara O(n²) con O(n log n) en términos de eficiencia?  
O(n²) crece más rápido que O(n log n), lo que lo hace menos eficiente para grandes entradas.

9) ¿Qué es el peor caso en el análisis de complejidad y cómo se representa en Big O?  
El peor caso describe el escenario en el que un algoritmo tiene el peor rendimiento posible, y se representa usando la notación Big O para mostrar la mayor cantidad de recursos necesarios.

10) ¿Qué significa O(2^n) y qué tipo de algoritmos suelen tener esta complejidad?  
O(2^n) describe un crecimiento exponencial, típico en algoritmos que exploran todas las combinaciones posibles, como los algoritmos de backtracking.

11) ¿Qué diferencia hay entre el mejor caso y el peor caso en Big O Notation?  
El mejor caso describe el rendimiento óptimo de un algoritmo, mientras que el peor caso indica el escenario donde el algoritmo usa más recursos.

12) ¿Qué es la complejidad de espacio en Big O y cómo difiere de la complejidad temporal?  
La complejidad de espacio mide cuánta memoria utiliza un algoritmo, mientras que la complejidad temporal mide cuánto tiempo toma ejecutarse.

13) ¿Qué significa O(n!) y en qué situaciones se puede encontrar esta complejidad?  
O(n!) describe un crecimiento factorial, característico de algoritmos que generan todas las permutaciones posibles, como el algoritmo de resolución de problemas combinatorios.

14) ¿Qué es la notación Ω (Omega) y cómo se relaciona con Big O?  
Ω (Omega) describe el límite inferior de la complejidad de un algoritmo, representando el mejor caso posible, mientras que Big O describe el límite superior.

15) ¿Qué es la notación Θ (Theta) y cómo se diferencia de Big O y Ω?  
Θ (Theta) describe una cota ajustada, indicando que el tiempo de ejecución de un algoritmo está acotado tanto por arriba como por abajo por una función específica.

16) ¿Cómo afecta el tamaño de la entrada a la complejidad de un algoritmo descrito por O(1)?  
El tamaño de la entrada no afecta a un algoritmo O(1), ya que su tiempo o espacio permanece constante.

17) ¿Cómo afecta la recursividad a la complejidad de un algoritmo en Big O?  
La recursividad puede incrementar la complejidad de un algoritmo, especialmente si cada llamada recursiva genera nuevas operaciones o llamadas adicionales.

18) ¿Qué significa amortized time complexity en Big O Notation?  
La complejidad amortizada mide el costo promedio de una operación en una secuencia de operaciones, distribuyendo el costo de operaciones costosas a lo largo de varias más baratas.

19) ¿Cómo se representa la complejidad de un algoritmo que tiene múltiples entradas con diferentes tamaños?  
Cuando un algoritmo tiene varias entradas, su complejidad se representa con más de una variable, por ejemplo, O(m * n) si hay dos entradas de tamaños diferentes.

20) ¿Qué es el teorema maestro y cómo se utiliza para analizar la complejidad de algoritmos recursivos?  
El teorema maestro proporciona una fórmula para calcular la complejidad de algoritmos recursivos que siguen una forma particular de división y conquista.

21) ¿Qué significa O(√n) y cuándo se suele encontrar esta complejidad?  
O(√n) indica que el algoritmo tiene un crecimiento proporcional a la raíz cuadrada del tamaño de la entrada, común en ciertos algoritmos de búsqueda y factorización.

22) ¿Cómo afecta el uso de estructuras de datos a la complejidad en Big O?  
Las diferentes estructuras de datos pueden cambiar la complejidad de las operaciones básicas (inserción, eliminación, búsqueda), afectando el rendimiento general del algoritmo.

23) ¿Qué es la complejidad polinómica y cómo se compara con la complejidad exponencial en Big O?  
La complejidad polinómica (O(n^k)) crece más lentamente que la exponencial (O(2^n)), lo que hace que los algoritmos polinómicos sean más eficientes para entradas grandes.

24) ¿Qué impacto tiene la constante oculta en Big O Notation?  
Aunque Big O ignora las constantes, en la práctica pueden tener un impacto significativo en el rendimiento de un algoritmo, especialmente para entradas pequeñas.

25) ¿Qué es la complejidad sublineal y en qué contextos se puede encontrar?  
La complejidad sublineal (por ejemplo, O(log n)) indica que el tiempo de ejecución crece más lentamente que el tamaño de la entrada, lo que es típico en algoritmos de búsqueda eficientes.

26) ¿Qué significa decir que un algoritmo es escalable en términos de Big O?  
Un algoritmo escalable mantiene un crecimiento razonable en su tiempo o espacio conforme aumenta el tamaño de la entrada, siendo capaz de manejar grandes conjuntos de datos.

27) ¿Cómo se puede mejorar la complejidad temporal de un algoritmo de O(n²) a O(n log n)?  
Optimizando el algoritmo, por ejemplo, utilizando una técnica de divide y vencerás, como en el caso de mejorar bubble sort a merge sort.

28) ¿Cómo afecta el uso de hash tables a la complejidad en Big O?  
Las tablas hash pueden ofrecer una complejidad promedio de O(1) para operaciones de búsqueda, inserción y eliminación, mejorando significativamente el rendimiento.

29) ¿Cómo se analiza la complejidad de un algoritmo que incluye varias operaciones con diferentes complejidades?  
Se considera la complejidad de la operación más costosa, ya que dominará el comportamiento global del algoritmo.

30) ¿Cuál es la diferencia entre la complejidad asintótica y la complejidad práctica de un algoritmo?  
La complejidad asintótica describe el comportamiento del algoritmo en entradas extremadamente grandes, mientras que la complejidad práctica toma en cuenta factores como las constantes y la arquitectura del sistema en entradas reales.
