1) ¿Qué es el hook `useContext` en React?  
    El hook `useContext` permite a los componentes de React acceder al valor del contexto creado con `React.createContext` sin tener que utilizar el componente `<Context.Consumer>`
2) ¿Cómo se crea un contexto en React para usar con `useContext`?  
    Utiliza `React.createContext(defaultValue)` para crear un contexto, donde `defaultValue` es el valor predeterminado del contexto si no hay un proveedor.
3) ¿Cómo se utiliza `useContext` para acceder al valor del contexto en un componente funcional? 
    Importa `useContext` y pasa el contexto creado a `useContext(Context)` para obtener el valor del contexto en el componente.
4) ¿Cuál es la diferencia entre `useContext` y el componente `<Context.Consumer>`?  
    `useContext` simplifica el acceso al contexto en componentes funcionales, mientras que `<Context.Consumer>` se usa en componentes de clase y proporciona un patrón basado en render props.
5) ¿Cómo puedes actualizar el valor del contexto desde un componente que usa `useContext`?  
    Actualiza el valor del contexto en el componente que usa el proveedor `<Context.Provider>`, y los componentes que usan `useContext` reflejarán el nuevo valor.
6) ¿Qué pasa si `useContext` se utiliza fuera de un proveedor de contexto?  
    `useContext` devolverá el valor predeterminado del contexto especificado al crear el contexto con `React.createContext(defaultValue)`.
7) ¿Cómo puedes proporcionar un valor dinámico a un contexto utilizando `useContext`?  
    Usa el estado o las props del componente proveedor para establecer el valor del contexto y proporciona ese valor a través de `<Context.Provider>`.
8) ¿Qué tipo de valores se pueden almacenar en un contexto cuando se utiliza `useContext`?  
    Puedes almacenar cualquier tipo de valor en el contexto, como objetos, funciones, arrays o valores primitivos.
9) ¿Cómo puedes manejar el rendimiento en componentes que utilizan `useContext`?  
    Usa el contexto de manera eficiente y evita que el componente se renderice innecesariamente al memoizar el valor del contexto o usando `React.memo` en componentes hijos.
10) ¿Cómo se puede crear un contexto para manejar temas (tema claro/oscuro) en una aplicación?  
    Crea un contexto con `React.createContext` para el tema y proporciona un valor que incluya la información del tema actual y una función para cambiarlo.
11) ¿Cómo puedes evitar que todos los componentes que usan `useContext` se vuelvan a renderizar cuando cambia el valor del contexto?  
    Asegúrate de que el valor del contexto sea estable y no cambie innecesariamente, utilizando técnicas como la memoización del valor.
12) ¿Qué papel juega el `Provider` en el contexto cuando se utiliza con `useContext`?  
    El `Provider` proporciona el valor del contexto a los componentes descendientes que usan `useContext`, permitiendo que accedan a ese valor.
13) ¿Cómo puedes usar múltiples contextos en un solo componente?  
    Puedes usar múltiples contextos importando y utilizando `useContext` para cada contexto dentro del mismo componente funcional.
14) ¿Cómo puedes combinar `useContext` con otros hooks de React, como `useReducer` o `useState`?  
    Puedes usar `useContext` junto con `useReducer` o `useState` en un componente para manejar el estado local y el estado global proporcionado por el contexto.
15) ¿Cómo se puede evitar el problema de "prop drilling" utilizando `useContext`?  
    Utiliza `useContext` para proporcionar y consumir valores en el árbol de componentes, evitando la necesidad de pasar props a través de múltiples niveles de componentes.
