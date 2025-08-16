# 2° Parcial Diseño 3K2

## **Explique en qué debe enfocarse un Diseñador Centrado en el Usuario.** 
Cuando diseñamos interfases tenemos que enfocarnos en la imagen viendo que opciones tiene disponibles el usuario. Así mismo, el diseño visual solo es una parte (UI) necesitamos también concentrarnos en la experiencia del usuario (UX).
Para esto es que como ingenieros debemos proporcionar una solución al tipo de usuario que usará el sistema; eso es el diseño centrado en el usuario, básicamente identificar los usuarios del sistema y lo que ellos quieren hacer con él.
Para esto hay distintos procesos pero se puede.
- Observar como las personas trabajan actualmente en su oficina.
- Entrevistar a esas personas
- Escuchar el problema de los clientes
- Identificar todos los usuarios pertinentes.
- Hay que saber para que quién estamos diseñando y lo que la gente quiere hacer con el producto

Aquí viene todo el cuentito del diseñador centrado en el usuario y de la fábula del **"pequeño saltamontes"**.

Quien diseñe centrándose en el usuario debe basarse en los secretos y ellos son:
1) **Primer secreto del diseño centrado en el usuario**
	1) Foco temprano y continuo en el usuario y sus tareas
		1)  Los diseños planteados deben funcionar como la gente espera que lo hagan; y la mejor forma de corroborarlo es haciendo que ellos lo usen; si el cliente reporta que hay un problema, es que él es un inútil, pero es un problema para nosotros por que no lo está usando correctamente; por eso utilizamos pruebas de usabilidad.
2) **Segundo secreto del diseño centrado en el usuario**
	1) La medición empírica del comportamiento del usuario
		1) Medir la efectividad: cuanta gente logra completar la ruta crítica de forma correcta.
		2) Medir la eficiencia: cuanto tiempo le toma a la gente completar esa tarea
		3) Realizar pruebas de usabilidad.
3) **Tercer secreto del diseño centrado en el usuario**
	1) Crear muchos prototipos en papel y electrónicos probarlos y luego cambiar los diseños dependiendo de la retroalimentación, y antes de mandarnos a codear como loco tenemos que definir todo y la decisión final será tomada por quien cobre más plata, o quien tenga los pantalones en ese proyecto

##  **Explique en qué consiste el patrón GRASP Bajo Acoplamiento (Problema - Solución).**

## Bajo Acoplamiento

|                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------- |
| Acoplamiento: medida de la fuerza con que un elemento está conectado a, tiene conocimiento de, o confía en otros elementos. |
|                                                                                                                             |

- **Problema:** ¿Cómo soportar bajas dependencias, en miras a la reutilización?
- **Solución:** Asignar una responsabilidad de manera que el acoplamiento permanezca bajo.

<p style="color: red; font-size: 20px;">
	Es importante chamuyar un poquito más.
</p>

## **Explique claramente y en detalle en qué consiste la Visibilidad.**
Es la capacidad de un objeto de "ver" o tener referencia a otro, es decir es la capacidad de "conocer" sobre algo en específico. Si tenemos un objeto que emite hacia un receptor; el primero debe tener visibilidad del segundo para saber a donde le emitirá.
Responde a la pregunta, **¿Se encuentra un recurso o instancia al alcance de otro?**

Existen 4 formas de alcanzar visibilidad de un objeto A a un objeto B.
1) **Visibilidad de atributo**: B es un atributo de A
2) **Visibilidad de parámetro**: B es un parámetro de un método de A
3) **Visibilidad local**: B es un objeto local (no un parámetro) en un método de A
4) **Visibilidad global:** B es de algún modo visible globalmente.


## Visibilidad de atributo.
Sucede cuando "B" es un atributo de "A".
Este tipo de visibilidad es permanente, ya que existirá siempre que existan A y B.
Ejemplo:

```
class ClaseA {
  constructor() {
    this.atributoB = "Soy visible desde los métodos de A"; // B es un atributo de A
  }

  metodoDeA() {
    console.log(this.atributoB); // Acceso a B desde un método de A
  }
}

let objetoA = new ClaseA();
objetoA.metodoDeA(); // Salida: "Soy visible desde los métodos de A"
```
## Visibilidad de parámetro
Sucede cuando B se transmite como un parámetro a un método de A.
Este tipo de visibilidad es relativamente **TEMPORAL**, es decir existirá en el ámbito del método.
Ejemplo;

```
class ClaseA {
  metodoDeA(parametroB) { // B es un parámetro del método
    console.log(parametroB); // Acceso a B dentro del método
  }
}

let objetoA = new ClaseA();
objetoA.metodoDeA("Soy visible solo dentro del método"); 
```
## Visibilidad Local
Es cuando se declara que B es un objeto local, dentro de un método de A.
Este tipo de visibilidad es relativamente **TEMPORAL**, es decir existirá en el ámbito del método.
Ejemplo:

```
class ClaseA {
  metodoDeA() {
    let variableLocalB = "Soy visible solo dentro de este método"; // B es una variable local
    console.log(variableLocalB);
  }
}

let objetoA = new ClaseA();
objetoA.metodoDeA(); // Salida: "Soy visible solo dentro de este método"
```
## Visibilidad Global
Sucede cuando B es global para A.
Es una visibilidad **permanente** ya que persiste mientras existan A y B.
Ejemplo:

```
let variableGlobalB = "Soy visible globalmente"; // B es una variable global

class ClaseA {
  metodoDeA() {
    console.log(variableGlobalB); // Acceso a B desde dentro de la clase
  }
}

let objetoA = new ClaseA();
objetoA.metodoDeA(); // Salida: "Soy visible globalmente"

console.log(variableGlobalB); // Acceso a B desde cualquier lugar
```

## **Explique qué entiende por Prueba de Escenario. Ejemplifique.**

Las **pruebas de versión** es el proceso de poner a prueba una versión de un sistema fuera del equipo de desarrollo.
Está enfocada en las pruebas de versión; creando escenarios típicos de uso y con ellos desarrollando casos de prueba. Un escenario no es más que una historia que describe una forma en que puede usarse el sistema, pero deben ser realistas estos escenarios. Una prueba de escenario incluye una historia narrativa creíble y compleja.

<p style="color: red; font-size: 20px;">
	Es importante chamuyar un poquito más.
</p>
## **Explique por qué debe planificarse la prueba.**

Es necesaria una planificación cuidadosa para sacar el máximo provecho de inspecciones y pruebas así controlamos sus costos, ya que son procesos caros. El esfuerzo que dedicaremos a las pruebas; siempre dependerá del tipo de sistema que desarrollaremos. Los planes de prueba incluyen contingencias, para que los desajustes puedan solucionarse y el personal pueda ser reasignado a otras actividades.

<p style="color: red; font-size: 20px;">
	Es importante chamuyar un poquito más.
</p>