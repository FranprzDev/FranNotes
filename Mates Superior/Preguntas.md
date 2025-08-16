# Unidad 2: Transformada de Laplace
### ¿Que es la Transformada de Laplace? Exprese su formula
Definiremos una función real, f(t) que este definida para t > 0, llamaremos **Transformada de Laplace de f(t) a:**
![[Pasted image 20241001204331.png]]
Donde s es una variable compleja, y t es la variable que representa el tiempo.
### Propiedades de la Transformada de Laplace
**Propiedad de la suma algebraica** La suma algebraica de las transformadas o de la inversa de las transformadas es la suma algebraica de dichas transformadas.
- **Propiedad de Linealidad:** Al ser una integral, la constantes pueden salir afuera de la transformada.
- **Propiedad de Traslación:** Si tenemos f(t) una función temporal y a una constante, entonces;
	- ![[Pasted image 20241001204824.png]]
- **Transformada de Laplace de las derivadas:** 
	- ![[Pasted image 20241001204901.png]]
	- Generalización
		- ![[Pasted image 20241001204918.png]]
### ¿Qué ecuaciones resuelven las transformadas de Laplace?
Resuelven ecuaciones diferenciales de cualquier orden pero **solo lineales**

# Unidad 3: Ecuaciones diferenciales
### ¿Que es una ecuación diferencial?
Es cualquier igualdad algebraica o trascendental que involucra diferenciales o derivadas. Por ejemplo la segunda Ley de Newton.
### ¿Cómo se clasifican las ecuaciones diferenciales?
Las podemos clasificar según:
- Tipo
	- Ordinarias: La variable dependiente es función de una sola variable independiente. Hablamos de derivadas totales.
	- Parciales: Si la variable dependiente es una función de dos o más variables independientes.
- Orden: Esta dado por la derivada de mayor orden que aparece en la ecuación.
- Grado: Es el grado algebraico (numerito) de la derivada de mayor orden que aparece en la ecuación diferencial.
### ¿Cuando una ecuación diferencial es lineal?
Una ecuación diferencial es **lineal** si en ella no aparecen potencias de la variable dependiente y sus derivadas. Es decir si algún término de la ecuación diferencial contiene potencias superiores, producto o funciones trascendentales **(exponenciales, logaritmicas, trigonometricas, hiperbolicas e inversas)** de las variables dependientes, será una ecuación no lineal.
# Unidad 4: Función de Transferencia
### ¿Por qué es importante la función de transferencia?
Por que cualquier tipo de sistema informático puede ser representado por la función de transferencia, y permite estudiar las salidas Y(s) según las entradas dadas U(s).
Permite lograr una comprensión de la naturaleza del sistema.
### ¿Cómo se obtiene? 
La función de transferencia se define como la transformada de Laplace de la salida sobre la transformada de Laplace de la entrada, es decir.
P(s) = Y(s) / R(s)
Las condiciones iniciales en una función de transferencia siempre serán 0 y sean invariantes en el tiempo.

### ¿Qué significan las condiciones iniciales? ¿Que Implica que sean cero?
Para una ecuación diferencial, son el estado del sistema al momento de arrancar el estudio.
Que sean 0 significa que empezamos a estudiar nuestro sistema cuando este comienza y que el modelo matemático de la función de transferencia existe.

# Unidad 5: Resolución por Métodos de un Paso
### ¿Qué tipo de ecuaciones resuelven?
Resuelven ecuaciones diferenciales **lineales** de **primer orden**
### ¿Cómo se obtiene la pendiente en cada uno?
- Método de Euler O(h^2)
	![[Pasted image 20241002005212.png]]
- Método de Euler Mejorado o Hwei O(h^3)
	![[Pasted image 20241002005431.png]]
- Método del Polígono Mejorado O(h^3)
	![[Pasted image 20241002005612.png]]
### ¿Qué significa el error en cada uno? Marcar los mejores métodos.
Como se puede observar en la gráfica, se comete un error al calcularlo. 
La solución de una EDO incluye dos tipos de errores. 
1) Error de redondeo producido por el número finito de cifras que se usan. 
2) El error de truncamiento producido por la naturaleza del método, este error se lo obtiene al desarrollar la Serie de Taylor,
- Método de Euler - Error O(h^2) 
	- El método de Euler corresponde a la Serie de Taylor truncada en el segundo término,
- Método de Hwei - Error O(h^3) **THE BEST**
	- El método de Hwei es mejor debido a que es un método predictor - corrector que implica el cálculo de dos derivadas, en un punto inicial y en un punto final. Se promedia las 2 derivadas y se obtiene una aproximación mejorada de la pendiente que el método de Euler.
	- El error esta dado de esa forma porque la ecuación correctora es una expresión directa de la regla del trapecio obtenido al  integrar el polinomio de interpolación de Newton Gregory. 
- Método del Polígono Mejorado - Error O(h^3) **THE BEST**
	- Es mejor que el de Euler, por que utiliza una aproximación de la pendiente en el punto medio del intervalo.

 