La mejora de procesos significa comprender los proceos existentes y cambiarlos para incrementar la calidad del producto o reducir los costos y el tiempo de desarrollo.
Existen 2 enfoques.
- El de madurez de procesos
	- Consta de mejorar la calidad del producto y la previsibilidad del proceso.
- Ágil
	- Entrega rápida de funcionalidad y mejorar la capacidad de respuesta
## Ciclo de Mejoras de Proceso
Existe un ciclo de mejora de procesos, definido
![[Pasted image 20251125222925.png]]
_Durante las clases las Ref. a la gestión de la calidad le gustaron bastante, flasheen como puedan y lo que se les ocurra que toda falopa aporta_
Para la Ing. de Software consta de lo siguiente: 
- **Medición**
	Medimos los atributos del proyecto actual o el producto; la meta es mejorar las medidas de acuerdo con los objetivos de la organización. Esto ayuda a determinar una línea de referencia que para ver si son efectivas las mejoras del proceso.
	_Ref. a Gestion de la Calidad_ **Si el proceso no se mide, no se puede mejorar**

	**¿Qué medimos?** (Algunas ideas)
	- **Tiempo para completar un proceso**
		- Desarrollo de casos de prueba
		- Desarrollo de casos de uso
		- Implementación de la Funcionalidad
	- **Recursos requeridos para un proceso**
		- Días persona
		- Costo de relevamiento
	- **Número de ocurrencias de un evento**
		- Defectos encontrados al inspeccionar el código (Pull Requests)
		- Número de cambios de rqeuisitos
		- Número promedio de líneas de código modificadas ante un cambio
- **Análisis**
	Se valora el proceso actual y se identifican las debilidades y los cuellos de botella del proceso; aquí desarrollamos los modelos de procesos descriptos; este análisis se puede enfocar en las características del proceso como la rapidez y la robustez.
	_Ref. a Gestion de la Calidad_ **Una vez que lo medimos, podemos tomar decisiones exactas hacia donde ir.**
- **Cambio**
	Los cambios al proceso son propuestos para atacar alguna de las debilidades identificadas; estos cambios se introducen y el ciclo vuelve a recopilar datos sobre la efectividad del cambio
	_Ref. a Gestion de la Calidad_ **Cuando mejoramos algo, lo volvemos a medir para seguir mejorando y alcanzar la _mejora continua_.**
	
## Modelos de Madurez 
### CMM - CMMI 
Propuesto por el SEI (Software Engineering Institute)
CMM - Software Capability Maturity Model
Modelo de madurez de Capacidades de Software
Evoluciona especificamente en el CMMI
Que es el Modelo de Madurez de Capacidades de Software Integrado

Destaca las áreas clave de proceso (KPA) y va por niveles según dependa.
![[Pasted image 20251125223733.png]]

### ISO/IEC
Del otro lado tenemos la mejora de procesos por medio de la norma ISO/IEC (International Organization for Standarization) (Comisión Electrotécnica Internacional)

Especificamente tenemos la norma 15504 - SPICE (Software Process Improvement Capability Determination); Determinación de la Capacidad de la Mejora del Proceso de Software.

Tiene 6 niveles, que son:
1) Incompleto
2) Realizado
3) Gestionado
4) Establecido
5) Predecible
6) En optimización
_Vicent había dicho que no le demos bola a este pero qsy_

## Mejora de Procesos en contexto ágil
En un modelo tradicional, la mejora del proceso se concibe como una actividad **formal, planificada y documentada** que busca aumentar la **capacidad organizacional y la madurez del proceso**.
Pero no obstante, si lo tenemos que poner en un marco ágil; la mejora del proceso en cambio es **continua, empírica y emergente** integrada durante el ciclo iterativo del desarrollo; y esta surge de la **retroalimentación del equipo y del cliente**

Revisar la respuesta del parcial (me contó bastante)
![[Pasted image 20251125224126.png]]


### Ciclo empírico de mejora continua
![[Pasted image 20251125224231.png]]

_Ref. a Calidad_ al igual que en calidad los procesos estandarizados aplican el Ciclo de mejora continua que es Plan-Do-Check-Act y se relacionan con lo equivalente en el ágil.

- La fase de **plan** la podemos relacionar con la planificación del sprint o la iteración que se realizará; donde definimos que es lo que se hará durante el sprint y la velocity que tendremos.
- La fase de **do** es justamente la ejecución del sprint; que es simplemente laburar.
- La fase de **check** son ceremonias definidas en el scrum como la **Sprint Review** (ver con el cliente si le gusta) y la **Sprint Retrospective** (una retro donde sabemos q hicimos mal). Bajo esta idea; entonces tenemos en cuenta lo que nos dice el cliente, lo que nos dice el equipo y lo tenemos en cuenta para ajustarlo.
- La fase de **act** se corresponde con justamente; la puesta en ejecución de estos ajustes y acuerdos que realizamos entre el equipo, para mejorar el desarrollo.

Esto puede afectar sobre algunas prácticas específicas como:
- **La Sprint Review**
	- Una buena puteada y alineación en la review, puede mejorar como se trabaja.
	- La idea es generar acciones concretas de mejora; y no solo observaciones.
- **Definition of Done**
	- Evolucionará a lo largo del proyecto; ampliándose o refinándose para incorporar lecciones aprendidas sobre la calidad, revisión del código, pruebas automáticas, etc.
- **Scrum Master**
	- Actuando como facilitador de la mejora continua, no como "auditor"
	- Su función es remover impedimentos y promover la autorreflexión del grupo.

### Herramientas
Básicamente se definen las siguientes herramientas:
- **Métricas ligeras** como velocidad, densidad de defectos (es decir hay muchos bugs), lead time (anda a saber q es), satisfacción del equipo
- **Tableros de mejora** Visibilizan problemas de procesos y sus soluciones, básicamente es parsear data de métricas para que tenga sentido.
- **Root cause analysis** / 5 Whys
	  _Ref. a Calidad_ básicamente es saber por q algo no funciono como debería funcionar y decir cual es la causa **MÁS PROBABLE** del por que no funciono. Es importante al hacerlo que si o si nos quedemos con SOLA UNA CAUSA RAÍZ; podemos diagnosticar varias, pero quedarnos con la más probable.
	  _Ref a Administración de Recursos_ Cordero habló algo de los 5 Wh, la verdad que no tengo ni idea que es pero flashen algo con Who, Where, When, What and How
- **Acciones de mejora en el backlog priorizadas por el equipo**

### Cultura organizacional
- Obtenemos transparencia total, sin miedo a visibilizar fallos.
- Autoorganización y empoderamiento del equipo.
- Valoración del insight sobre la documentación
- Aprendizaje colectivo, no señalar simplemente aprender.


### Beneficios y resultados esperados
- Adaptación rápida a cambios del entorno o del cliente.
- Disminución del retrabajo gracias a feedback temprano.
- Incremento sostenido en calidad del producto y satisfacción del equipo.
- Evolución de prácticas, lo que comienza como empírico, se consolida con estándares internos. (Aquí le va a encatar que le hablemos sobre el caso de su empresa, los planes de deploy y blablablbalallablal)


## Etapas en el proceso de pruebas 
1) Análisis y estimación
2) Plan de pruebas
3) Diseño de casos
4) Ejecución y Bug Fixing
5) Documentación

Cualquier estrategia de prueba debe incorporar **la planificación de la prueba**, **el diseño de casos de prueba**, **la ejecución de la prueba** y **la recolección y evaluación de los resultados**.

## Casos de prueba
Un **caso de prueba** es un conjunto de **precondiciones**, **datos de entrada**, **resultados esperados** y **función a probar**; desarrollados para un **objetivo particular**, como por ejemplo, ejercitar un camino concreto de escenario de caso de uso, verificar el cumplimiento de un requisito o comprobar la ejecución de un conjunto de líneas de código.
A veces se puede agregar las condiciones de ejecución y los resultados obtenidos luego de la ejecución de la prueba.

### Diferencia entre casos de prueba y datos de prueba.
Los datos de prueba **son aquellos que se utilizan como entrada** para probar los casos de prueba.
Un caso de prueba **puede estar compuesto por un número finito** **o infinito** de datos de prueba
Debido a que puede haber infinitos datos de prueba es necesario buscar una manera **de testear un caso de prueba de la manera más completa con un conjunto finito** de datos prueba
Este conjunto finito se obtiene por medio de **estrategias** donde buscamos **"datos testigos"**, que identifican situaciones límites o representan un conjunto de datos de prueba.

### Selección de casos de prueba efectivos.
La efectividad de los casos significa:
1) Mostrar que cuando se usa como se esperaba, el componente que se somete a prueba, hace lo que se supone que tiene que hacer.
2) Si hay defectos en el componente, estos deberían relevarse mediante los casos de pruebas.
   
## Pruebas de Caja negra
Son básicamente pruebas donde no se tiene el conocimiento sobre como funciona el sistema propiamente. Es decir; por ejemplo el trabajo de un QA Manual está haciendo pruebas de caja negra; si algo falla; se notifica y ya. Pero no sabe de la implementación.
- Pruebas de validación
- Pruebas del sistema
- Pruebas de usuario
- Pruebas de versión

## Ideal software Testing Pyramid
![[Pasted image 20251125231004.png]]

## Software Testing Ice-cream Cone Anti-Pattern
![[Pasted image 20251125231021.png]]


![[Pasted image 20251125231122.png]]

## Herramientas para la automatización

**Frontend**
- Playwright --> Con esto testeamos nuestro TFI POR SI PREGUNTAAAAAAAN ||  ES UNA HERRAMIENTA QUE SIRVE PARA LEVANTAR UN BROWSER (NAVEGADOR) Y PUEDA REALIZAR TEST INTERNOS. Nosotros los testeamos mediante el "MCP DE PLAYWRIGHT" (Basicamente lo testeó una IA xd)
- Cypress | Selenium / Serenity -> Otras cosas , jamas las use
**Backend**
- AXIOS -> (USAMOS AXIOS PARA USAR EN EL FRONTEND)
- Mocha -> Escenarios en gherkin **(LO UTILIZAMOS EN NUESTRO TFI)**
- Chai -> Para hacer las assertions y validar datos de prueba  **(LO UTILIZAMOS EN NUESTRO TFI)**
- Cypress / RestAssured con Java -> Ni diea no le den bola
**Mobile**
- Appium | Playwright --> no led en bola calculo
- 
