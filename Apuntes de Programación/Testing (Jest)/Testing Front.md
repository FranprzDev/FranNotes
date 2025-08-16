### Jr
1) ¿Qué es Jest y para qué se utiliza en el testing de aplicaciones frontend?  
    Jest es un framework de testing para JavaScript que se utiliza para realizar pruebas unitarias, de integración y de extremo a extremo en aplicaciones frontend. Permite escribir pruebas para verificar que el código se comporta como se espera.
2) ¿Cómo se configura Jest en un proyecto de React?  
    Se configura instalando Jest y sus dependencias mediante npm o yarn, y creando un archivo de configuración `jest.config.js` si es necesario. También se puede configurar Jest en el archivo `package.json`.
3) ¿Qué son los snapshots en Jest y cómo se utilizan en el testing de componentes de React?  
    Los snapshots en Jest son una forma de guardar una representación del componente en un momento dado. Se utilizan para realizar pruebas de regresión, comparando el componente actual con el snapshot guardado anteriormente para detectar cambios inesperados.
4) ¿Cómo se realiza una prueba unitaria básica con Jest en un componente React?  
    Se realiza importando el componente y renderizándolo con herramientas como `@testing-library/react`, luego se utilizan métodos de aserción para verificar que el componente se comporta como se espera.
5) ¿Qué es `@testing-library/react` y cómo se utiliza en conjunto con Jest para probar componentes React?  
    `@testing-library/react` es una biblioteca que proporciona utilidades para renderizar componentes React y realizar aserciones sobre su comportamiento. Se utiliza con Jest para escribir pruebas más centradas en el comportamiento del usuario.
6) ¿Cómo se escribe una prueba que verifica si un componente React renderiza correctamente un texto?  
    Se escribe renderizando el componente con `@testing-library/react` y utilizando el método `getByText` para verificar que el texto esperado está presente en el documento.
7) ¿Cómo se simulan eventos como clics en pruebas con Jest y `@testing-library/react`?  
    Se simulan eventos utilizando el método `fireEvent` de `@testing-library/react`, que permite disparar eventos como clics, cambios de texto y otros eventos del DOM.
8) ¿Cómo se utiliza Jest para probar funciones o métodos en un archivo de utilidad?  
    Se importan las funciones o métodos en el archivo de prueba y se escriben pruebas unitarias que verifican su comportamiento esperado utilizando métodos de aserción de Jest.
9) ¿Qué es el archivo de configuración `jest.config.js` y qué opciones comunes se configuran en él?  
    `jest.config.js` es el archivo de configuración para Jest donde se pueden especificar opciones como el entorno de prueba, los directorios a ignorar y las transformaciones de archivos. Opciones comunes incluyen `testEnvironment`, `transform` y `moduleNameMapper`.
10) ¿Cómo se utilizan los mocks en Jest para simular dependencias en una prueba?  
    Se utilizan funciones de mock como `jest.mock()` para reemplazar módulos o dependencias con implementaciones simuladas durante la prueba, permitiendo controlar y verificar su comportamiento.
11) ¿Qué es `jest.fn()` y cómo se utiliza para crear funciones simuladas?  
    `jest.fn()` es una función que se utiliza para crear funciones simuladas o mock functions. Permite espiar llamadas a funciones, proporcionar implementaciones simuladas y verificar llamadas.
12) ¿Cómo se realiza una prueba que verifica si un componente React se renderiza correctamente con propiedades?  
    Se realiza pasando las propiedades al componente al renderizarlo con `@testing-library/react` y utilizando métodos de aserción para verificar que el componente muestra el contenido esperado basado en esas propiedades.
13) ¿Qué es un "spy" en Jest y cómo se utiliza para espiar llamadas a funciones?  
    Un "spy" en Jest es una función mock que permite interceptar y registrar llamadas a una función. Se utiliza para verificar que una función ha sido llamada con ciertos argumentos o un número específico de veces.
14) ¿Cómo se realiza una prueba que verifica si un componente maneja correctamente el estado interno?  
    Se realiza renderizando el componente, interactuando con él para cambiar el estado (por ejemplo, haciendo clic en un botón), y luego verificando que el estado interno se actualiza como se espera.
15) ¿Cómo se utiliza `beforeEach` y `afterEach` en Jest para preparar y limpiar el entorno de prueba?  
    `beforeEach` se utiliza para ejecutar código antes de cada prueba, como configurar el estado inicial, mientras que `afterEach` se utiliza para limpiar o restablecer el estado después de cada prueba.
16) ¿Qué es `describe` en Jest y cómo se utiliza para agrupar pruebas relacionadas?  
    `describe` es una función que se utiliza para agrupar pruebas relacionadas en bloques. Permite organizar las pruebas en suites y aplicar configuraciones específicas a un grupo de pruebas.
17) ¿Cómo se escriben pruebas asíncronas en Jest para componentes que realizan operaciones asíncronas?  
    Se escriben utilizando `async/await` para manejar operaciones asíncronas en las pruebas, y se asegura que las promesas se resuelvan antes de que las pruebas terminen utilizando `await` en la llamada a funciones asíncronas.
18) ¿Cómo se realiza una prueba que verifica si un componente React maneja correctamente errores?  
    Se realiza simulando una condición de error (por ejemplo, pasando un error al componente) y verificando que el componente muestra la información de error adecuada o realiza la acción esperada.
19) ¿Cómo se utilizan los "mock modules" en Jest para simular módulos completos?  
    Se utilizan `jest.mock()` para reemplazar un módulo completo con una implementación simulada, permitiendo controlar el comportamiento del módulo y verificar interacciones durante las pruebas.
20) ¿Qué son los "test doubles" y cómo se utilizan en Jest?  
    Los "test doubles" son objetos utilizados en pruebas para reemplazar dependencias reales. En Jest, se utilizan mocks, stubs y spies como test doubles para simular comportamientos y verificar interacciones.
### Ssr
1) ¿Cómo se integra Jest con herramientas de pruebas end-to-end como Cypress?  
    Se integra utilizando Jest para pruebas unitarias y de integración, mientras que Cypress se utiliza para pruebas end-to-end. Ambos pueden coexistir en el mismo proyecto, con Jest manejando las pruebas de unidades y Cypress las pruebas de flujos completos.
2) ¿Qué es `jest.mock()` y cómo se usa para simular módulos específicos en pruebas?  
    `jest.mock()` se utiliza para reemplazar un módulo completo con una versión simulada. Permite definir cómo debería comportarse el módulo simulado, proporcionando un control total sobre las dependencias.
3) ¿Cómo se realizan pruebas de rendimiento en componentes React utilizando Jest?  
    Se realizan utilizando herramientas y técnicas adicionales como `react-performance-testing` junto con Jest para medir y analizar el rendimiento de los componentes, identificando posibles cuellos de botella.
4) ¿Qué son los "test coverage reports" en Jest y cómo se generan?  
    Los "test coverage reports" proporcionan información sobre qué partes del código están cubiertas por pruebas. Se generan ejecutando Jest con la opción `--coverage`, que crea informes detallados de cobertura de código.
5) ¿Cómo se realiza la simulación de módulos de terceros en Jest cuando se prueba un componente React?  
    Se realiza utilizando `jest.mock()` para simular módulos de terceros, como bibliotecas o servicios, permitiendo controlar sus comportamientos y verificar cómo el componente React interactúa con ellos.
6) ¿Qué es `jest.spyOn()` y cómo se utiliza para espiar métodos de objetos en pruebas?  
    `jest.spyOn()` se utiliza para espiar métodos de objetos, permitiendo interceptar y registrar llamadas a métodos. Se utiliza para verificar que los métodos se llaman con los argumentos correctos y en el momento adecuado.
7) ¿Cómo se realizan pruebas de integración de componentes React utilizando Jest y `@testing-library/react`?  
    Se realizan renderizando varios componentes juntos, interactuando con ellos y verificando que se comportan como se espera en conjunto. Se prueban interacciones y la integración entre componentes.
8) ¿Cómo se implementan pruebas de regresión con Jest en una aplicación React?  
    Se implementan utilizando snapshots para guardar la representación de los componentes en un momento dado. Las pruebas de regresión comparan el snapshot actual con el guardado previamente para detectar cambios inesperados.
9) ¿Qué es el "test environment" en Jest y cómo se configura para pruebas frontend?  
    El "test environment" define el entorno en el que se ejecutan las pruebas. En Jest, se configura con la opción `testEnvironment` en `jest.config.js`, configurando el entorno como `jsdom` para pruebas frontend en un entorno simulado de navegador.
10) ¿Cómo se realizan pruebas de accesibilidad en componentes React utilizando Jest?  
    Se realizan utilizando bibliotecas de pruebas de accesibilidad como `jest-axe` junto con Jest para verificar que los componentes cumplen con las normas de accesibilidad y no presentan problemas como contrastes insuficientes.
11) ¿Cómo se utiliza Jest para realizar pruebas de componentes que dependen de un contexto de React?  
    Se utiliza envolviendo el componente en un proveedor de contexto durante la renderización de las pruebas, permitiendo que el componente acceda y utilice el contexto necesario para su funcionamiento.
12) ¿Qué técnicas se pueden usar para mejorar la velocidad de las pruebas en Jest?  
    Técnicas incluyen la ejecución paralela de pruebas utilizando `--runInBand` para reducir la sobrecarga de I/O, la optimización de pruebas individuales para que sean menos costosas en términos de tiempo, y el uso de `jest --watch` para ejecutar solo pruebas relacionadas con los archivos modificados.
13) ¿Cómo se simulan respuestas de APIs en las pruebas con Jest?  
    Se simulan respuestas de APIs utilizando `jest.mock()` para reemplazar módulos que hacen llamadas a APIs con versiones simuladas que devuelven respuestas predefinidas.
14) ¿Cómo se escribe una prueba de integración que verifica la comunicación entre varios componentes en React?  
    Se escribe renderizando los componentes juntos en un entorno de prueba y verificando que interactúan correctamente entre sí, como pasar datos de un componente a otro o verificar la actualización del estado.
15) ¿Cómo se utilizan los mocks para pruebas en Jest para verificar el comportamiento de llamadas a APIs?  
    Se utilizan `jest.mock()` para crear versiones simuladas de funciones que realizan llamadas a APIs, permitiendo verificar que se llaman con los argumentos correctos y manejar respuestas simuladas para las pruebas.
16) ¿Qué es `jest.clearAllMocks()` y cuándo se debe utilizar en pruebas?  
    `jest.clearAllMocks()` se utiliza para restablecer todos los mocks en Jest, limpiando el historial de llamadas y restaurando las implementaciones originales. Se debe utilizar en `beforeEach` o `afterEach` para evitar efectos secundarios entre pruebas.
17) ¿Cómo se configuran pruebas para componentes React que usan Hooks personalizados?  
    Se configuran renderizando el componente que utiliza el Hook personalizado y verificando su comportamiento a través de la interfaz pública del componente, como los efectos secundarios y las actualizaciones del estado.
18) ¿Cómo se implementa el testing de componentes con React Router utilizando Jest?  
    Se implementa envolviendo los componentes en un proveedor de `Router` durante la renderización de las pruebas, permitiendo simular la navegación y verificar que los componentes se comportan correctamente en diferentes rutas.
19) ¿Cómo se realizan pruebas de rendimiento en componentes React con Jest?  
    Se realizan midiendo el tiempo que tarda en ejecutarse un componente o función utilizando herramientas como `performance.now()` y analizando los resultados para identificar posibles problemas de rendimiento.
20) ¿Qué son los "mock implementations" en Jest y cómo se utilizan para pruebas más avanzadas?  
    Los "mock implementations" son implementaciones simuladas de funciones o módulos que se utilizan para controlar el comportamiento de las dependencias durante las pruebas. Se definen utilizando `jest.fn()` o `jest.mock()` con una implementación personalizada.
### Sr
1) ¿Cómo se integra Jest con un pipeline de CI/CD para garantizar la ejecución automática de pruebas?  
    Se integra configurando el pipeline para ejecutar Jest en cada commit o solicitud de extracción, utilizando herramientas de CI/CD como GitHub Actions, Jenkins o GitLab CI, y configurando pasos para ejecutar pruebas y generar informes de cobertura.
2) ¿Qué estrategias se pueden emplear para manejar el estado global en pruebas con Jest para una aplicación grande?  
    Se pueden emplear estrategias como el uso de mocks y spies para simular el estado global, el uso de contextos y proveedores de estado para configurar el estado necesario en cada prueba, y la limpieza del estado global entre pruebas para evitar interferencias.
3) ¿Cómo se implementan pruebas de carga para una aplicación frontend utilizando Jest?  
    Se implementan utilizando herramientas complementarias como `artillery` o `k6` para simular carga en la aplicación y verificar el rendimiento bajo condiciones de alta demanda, mientras Jest se encarga de las pruebas unitarias y de integración.
4) ¿Qué es el "test isolation" y cómo se asegura en Jest para pruebas de componentes complejos?  
    El "test isolation" asegura que las pruebas sean independientes entre sí, evitando que una prueba afecte a otra. Se asegura en Jest utilizando mocks para controlar dependencias, configurando el entorno de prueba adecuadamente y limpiando el estado global entre pruebas.
5) ¿Cómo se utilizan los "test doubles" avanzados como stubs y mocks en Jest para pruebas de integración complejas?  
    Se utilizan para reemplazar componentes o módulos con versiones simuladas que controlan el comportamiento durante las pruebas, permitiendo verificar la interacción entre partes del sistema sin depender de implementaciones reales.
6) ¿Cómo se realizan pruebas de seguridad en una aplicación frontend utilizando Jest?  
    Se realizan utilizando herramientas de análisis de seguridad estática y dinámica junto con Jest, para identificar vulnerabilidades y asegurar que el código cumple con las mejores prácticas de seguridad.
7) ¿Qué técnicas se utilizan para escribir pruebas que sean resistentes a cambios en el código base?  
    Se utilizan técnicas como pruebas basadas en el comportamiento del usuario en lugar de la implementación, el uso de mocks y spies para controlar el entorno de prueba, y la escritura de pruebas de integración que verifican la funcionalidad general en lugar de detalles específicos.
8) ¿Cómo se integra Jest con herramientas de análisis estático de código para mejorar la calidad de las pruebas?  
    Se integra utilizando herramientas como ESLint y Prettier en el pipeline de CI/CD junto con Jest para asegurar que el código está bien formateado y sigue las mejores prácticas, y para detectar errores potenciales antes de ejecutar las pruebas.
9) ¿Cómo se manejan las pruebas de componentes React que interactúan con APIs externas en Jest?  
    Se manejan utilizando mocks para simular las respuestas de las APIs externas, permitiendo que las pruebas verifiquen cómo los componentes manejan las respuestas y los errores sin hacer llamadas reales a las APIs.
10) ¿Qué son los "fixtures" en el contexto de pruebas y cómo se utilizan en Jest?  
    Los "fixtures" son datos de prueba predefinidos que se utilizan para configurar el entorno de prueba. Se utilizan en Jest para proporcionar datos consistentes y controlados para las pruebas, asegurando que los resultados sean reproducibles.
11) ¿Cómo se implementa el testing de rendimiento para aplicaciones frontend utilizando Jest?  
    Se implementa midiendo el tiempo de ejecución de funciones y componentes, y utilizando herramientas como `benchmark.js` para realizar pruebas de rendimiento y analizar el impacto de cambios en el código en el tiempo de ejecución.
12) ¿Qué es el "test data management" y cómo se gestiona en Jest para aplicaciones grandes?  
    El "test data management" se refiere a la creación, gestión y limpieza de datos de prueba. Se gestiona en Jest utilizando fixtures, creando datos de prueba en `beforeEach` y limpiando los datos en `afterEach` para asegurar un entorno de prueba limpio.
13) ¿Cómo se maneja el testing de componentes que utilizan Web APIs como `fetch` en Jest?  
    Se maneja utilizando `jest.mock()` para simular el comportamiento de `fetch`, proporcionando respuestas predefinidas para las pruebas y verificando cómo los componentes manejan las respuestas y errores de las Web APIs.
14) ¿Cómo se realizan pruebas de compatibilidad entre navegadores utilizando Jest?  
    Se realizan configurando Jest para ejecutarse en diferentes entornos de prueba o utilizando herramientas de pruebas específicas para compatibilidad entre navegadores, como `browserstack`, junto con Jest para validar el comportamiento en múltiples navegadores.
15) ¿Cómo se realizan pruebas de usabilidad en una aplicación frontend utilizando Jest?  
    Se realizan utilizando herramientas de pruebas de interfaz de usuario que se integran con Jest para verificar que la interfaz es intuitiva y fácil de usar, y para identificar problemas de usabilidad en el diseño de la aplicación.
16) ¿Cómo se configuran pruebas para aplicaciones frontend con SSR (Server-Side Rendering) en Jest?  
    Se configuran renderizando componentes en el entorno del servidor y verificando que se comportan correctamente durante el renderizado del lado del servidor, utilizando herramientas como `react-dom/server` junto con Jest.
17) ¿Cómo se gestionan las pruebas de componentes React que dependen de servicios externos en Jest?  
    Se gestionan utilizando mocks para simular los servicios externos y proporcionar respuestas controladas durante las pruebas, permitiendo verificar el comportamiento de los componentes sin depender de servicios reales.
18) ¿Qué es el "test flakiness" y cómo se evita en Jest?  
    El "test flakiness" se refiere a pruebas que fallan de forma intermitente. Se evita en Jest asegurando que las pruebas sean independientes, utilizando datos consistentes y limpiando el estado entre pruebas para evitar efectos secundarios.
19) ¿Cómo se utilizan los "test reports" para analizar y mejorar la calidad del testing en Jest?  
    Se utilizan para revisar los resultados de las pruebas y los informes de cobertura, identificando áreas problemáticas y oportunidades de mejora. Los informes ayudan a analizar la eficacia de las pruebas y a priorizar áreas de refactorización.
20) ¿Cómo se manejan las pruebas de componentes que interactúan con la base de datos en Jest?  
    Se manejan utilizando mocks para simular la interacción con la base de datos, proporcionando respuestas predefinidas y verificando cómo los componentes manejan los datos, sin realizar operaciones reales en la base de datos.
