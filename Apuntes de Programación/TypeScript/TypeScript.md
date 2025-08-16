### Nivel Junior 
1) ¿Qué es TypeScript? 
	TypeScript es un superset de JavaScript que añade tipado estático opcional, lo que permite a los desarrolladores escribir código más robusto y detectar errores antes de la ejecución. 
2) ¿Cuál es la diferencia entre `let`, `const` y `var` en TypeScript?
	`let` y `const` son formas de declarar variables con un ámbito de bloque, mientras que `var` tiene un ámbito de función. `const` crea una referencia inmutable.
3) ¿Qué es la inferencia de tipos en TypeScript? 
	La inferencia de tipos es una característica de TypeScript que permite determinar automáticamente el tipo de una variable según su valor inicial sin necesidad de declarar explícitamente su tipo.
4) ¿Cómo defines un tipo personalizado en TypeScript? 
	Se puede definir un tipo personalizado utilizando `type` o `interface`. Ejemplo: `type Persona = { nombre: string, edad: number };` 
5) ¿Qué es una interfaz en TypeScript y para qué se usa? 
	Una interfaz en TypeScript define la forma de un objeto y se utiliza para describir la estructura de datos, permitiendo que diferentes objetos sigan el mismo contrato. 
6) ¿Qué es el archivo `tsconfig.json` y para qué sirve?
	El archivo `tsconfig.json` es el archivo de configuración de un proyecto TypeScript. Define las opciones del compilador y los archivos que deben incluirse o excluirse en el proceso de compilación. 
7) ¿Qué es el tipo `any` y cuándo debería evitarse su uso?
	El tipo `any` permite asignar cualquier tipo de valor a una variable, anulando las verificaciones de tipos. Debe evitarse porque elimina las ventajas del tipado estático. 
8) ¿Qué es el tipo `unknown` en TypeScript y en qué se diferencia de `any`? 
	`unknown` es un tipo más seguro que `any`. No permite acceder a las propiedades o métodos del valor sin realizar una verificación previa de tipo, lo que lo hace más seguro que `any`. 
9) ¿Qué son los tipos literales en TypeScript?
	Los tipos literales permiten definir un valor exacto que una variable puede tomar. Ejemplo: `let dirección: "norte" | "sur" | "este" | "oeste";` 
10) ¿Qué son los `tuples` en TypeScript?
	Una tupla es un tipo de array con un número fijo de elementos y tipos específicos para cada posición. Ejemplo: `let persona: [string, number] = ["Juan", 25];`
### Nivel Semi-Senior (SSR) 
1) ¿Qué son los tipos genéricos en TypeScript y cómo se usan? 
	Los tipos genéricos permiten crear componentes reutilizables que funcionan con varios tipos. Se definen utilizando una variable de tipo entre los símbolos `<>`. Ejemplo: `function identidad<T>(arg: T): T { return arg; }`. 
2) ¿Cómo se manejan los tipos opcionales en TypeScript? 
	Los tipos opcionales se indican con un `?` después del nombre del parámetro. Ejemplo: `function saludar(nombre?: string) {}`. Esto indica que el parámetro puede ser omitido.
3) ¿Qué son los `union types` y cómo funcionan en TypeScript?
	Los `union types` permiten que una variable pueda tener más de un tipo. Se usan con el símbolo `|`. Ejemplo: `let id: number | string;` que permite que `id` sea tanto un número como un string. 
4) ¿Cómo se define un tipo personalizado en TypeScript? 
	Puedes definir un tipo personalizado usando `type`. Ejemplo: `type ID = string | number;` crea un tipo `ID` que puede ser un `string` o un `number`.
5) ¿Cómo funciona la herencia en TypeScript? 
	La herencia en TypeScript se implementa con la palabra clave `extends`, lo que permite que una clase herede de otra. Ejemplo: `class Estudiante extends Persona {}`. 
6) ¿Qué son los `mapped types` en TypeScript? 
	Los `mapped types` permiten crear nuevos tipos a partir de las propiedades de un tipo existente. Ejemplo: `type SoloLectura<T> = { readonly [K in keyof T]: T[K] };` crea un tipo donde todas las propiedades son de solo lectura.
7) ¿Qué es el `strictNullChecks` en TypeScript y cómo ayuda a prevenir errores? 
	Cuando `strictNullChecks` está habilitado en TypeScript, las variables no pueden ser `null` o `undefined` a menos que estén explícitamente tipadas para permitir estos valores, lo que ayuda a evitar errores en tiempo de ejecución. 
8) ¿Qué son los `decorators` en TypeScript y para qué se utilizan? 
	Los decoradores son funciones que se aplican a clases, métodos, propiedades o parámetros para modificar su comportamiento. Se implementan utilizando `@` antes del nombre de la función decoradora.
9) ¿Cómo se manejan las sobrecargas de funciones en TypeScript? 
	La sobrecarga de funciones permite definir varias firmas para una función con diferentes tipos de parámetros. La implementación final debe manejar todos los tipos permitidos. Ejemplo: 
	```typescript 
	function combinar(a: number, b: number): number; function combinar(a: string, b: string): string; function combinar(a: any, b: any): any { return a + b; }```
10) ¿Qué es el narrowing de tipos en TypeScript? 
	El narrowing de tipos es la técnica que permite refinar el tipo de una variable dentro de un bloque de código mediante condicionales o verificaciones de tipo. Ejemplo: `if (typeof valor === "string") { /* valor es un string aquí */ }`.
### Nivel Senior (SR)

1) ¿Qué son los condicionales de tipos en TypeScript?  
	Los condicionales de tipos permiten aplicar lógica condicional a los tipos en función de otros tipos. Esto se hace utilizando la sintaxis `T extends U ? X : Y`.
1) ¿Cómo funcionan los `mapped types` avanzados en TypeScript?  
	Los `mapped types` avanzados permiten transformar las propiedades de un tipo de manera dinámica, aplicando operaciones a cada una de las propiedades de un tipo existente para crear un nuevo tipo.
1) ¿Qué es el operador `keyof` en TypeScript y cómo se usa?  
	`keyof` es un operador que permite obtener un tipo compuesto por las claves de un objeto. Es útil para garantizar que solo se usen propiedades válidas de un objeto en tiempo de compilación.
1) ¿Qué es un tipo condicional distribuido y cómo se utiliza?  
	Un tipo condicional distribuido se aplica cuando un tipo es una unión. Los tipos condicionales se distribuyen a cada miembro de la unión, permitiendo aplicar lógica condicional a cada tipo en la unión.
5) ¿Cómo se usan los tipos inferidos dentro de condicionales en TypeScript?  
	Se utiliza el operador `infer` para extraer tipos dentro de los condicionales, permitiendo manipular tipos de forma dinámica según los tipos inferidos en tiempo de compilación.
6) ¿Qué es un `lookup type` en TypeScript y cómo funciona?  
	Un `lookup type` permite acceder al tipo de una propiedad específica de un objeto. Se usa la sintaxis `T[K]`, donde `T` es el objeto y `K` es una clave dentro de ese objeto.
7) ¿Qué es el `utility type` `Partial` en TypeScript y cómo se utiliza?  
	`Partial<T>` es un tipo utilitario que convierte todas las propiedades de un tipo `T` en opcionales. Esto permite crear versiones incompletas de un objeto sin necesidad de definir todas sus propiedades.

8) ¿Qué son los tipos `readonly` en TypeScript y cuándo deberían usarse?  
	Los tipos `readonly` permiten definir propiedades que no pueden ser modificadas después de su inicialización. Esto es útil para asegurar la inmutabilidad de los objetos.
1) ¿Cómo se puede optimizar el uso de tipos avanzados para mejorar el rendimiento del código en tiempo de compilación?  
	El uso de tipos más simples, evitando condicionales complejos innecesarios o inferencias de tipos excesivas, puede mejorar significativamente el tiempo de compilación en proyectos grandes.
10) ¿Qué son los archivos de declaración (`.d.ts`) en TypeScript y cuál es su importancia en proyectos grandes?  
	Los archivos de declaración (`.d.ts`) proporcionan definiciones de tipos para bibliotecas o módulos que no están escritos en TypeScript. Son importantes para garantizar que se respeten los contratos de tipos en proyectos que mezclan JavaScript y TypeScript.

