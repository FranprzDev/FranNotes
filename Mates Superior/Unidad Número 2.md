## Transformada de Laplace (TL)
Definiremos una función real, f(t) que este definida para t > 0, llamaremos **Transformada de Laplace de f(t) a:**
![[Pasted image 20241001204331.png]]
Donde s es una variable compleja, y t es la variable que representa el tiempo.
## Inversa de la Transformada de Laplace (ITL)
La transformada de Laplace convierte un problema del dominio de la variable real tiempo en el dominio de una variable compleja "s", si necesitamos volver al dominio real, para esto utilizaremos la inversión de dicha transformada así obtengamos la solución en el dominio del tiempo.
### Propiedades de la Transformada de Laplace y su Inversa

- **Propiedad de la suma algebraica** La suma algebraica de las transformadas o de la inversa de las transformadas es la suma algebraica de dichas transformadas.
- **Propiedad de Linealidad:** Al ser una integral, la constantes pueden salir afuera de la transformada.
- **Propiedad de Traslación:** Si tenemos f(t) una función temporal y a una constante, entonces;
	- ![[Pasted image 20241001204824.png]]
- **Transformada de Laplace de las derivadas:** 
	- ![[Pasted image 20241001204901.png]]
	- Generalización
		- ![[Pasted image 20241001204918.png]]

### Tabla resumida de las Transformadas de Laplace:
![[Pasted image 20241001204955.png]]

### Expansión en Fracciones Parciales

La E.F.P es una forma de representar funciones racionales, que utilizamos para simplificar el cálculo de la inversa de la T.L de una función racional.
Existen varios métodos que dependerán de las raíces, que en matemática superior se llaman **polos**.
Los métodos son tres: 
- Simples
- Múltiples
- Complejas

Cuando se nos presenta una TL en forma de cociente de poloniomios; F(s) = p(s)/q(s)
Donde tanto p y q son polinomios, donde el grado p(s) >= q(s),
Entonces podemos reescribir  F(s) de la siguiente forma:
![[Pasted image 20241001205312.png]]
En otras palabras, lo que debemos hacer en líneas generales será siempre intentar transformar el denominador q(s) a una forma expresada donde estén los polos, para llegar a expresar la función F(s) de forma tal que sea una suma de los polos con sus "Residuos".

Los **Residuos** son los valores de las constantes que debemos encontrar.
La formula para calcular los residuos dependerá de la clasificación de los polos.
- Polos simples:
	- La formula que utilizaremos es:
		![[Pasted image 20241001205528.png]]
- Polos múltiples:
	- La formula que utilizaremos incluye derivada, así que hay que estar atento a como derivar, y saber las reglas de la derivación.
	- La generalización de esta expresión es la que utilizaremos para el calculo de polos. Siendo la primera "r" el orden de la derivada en la que estamos, y la segunda **r** el grado mayor de la derivada.
	- ![[Pasted image 20241001205625.png]]
	