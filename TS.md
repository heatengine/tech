# Typescript

- By definition, “TypeScript is JavaScript for application-scale development.”
- TypeScript is a strongly typed, object oriented, compiled language. TypeScript is both a language and a set of tools. TypeScript is a typed superset of JavaScript compiled to JavaScript.

### Interfaces
- An interface is a syntactical contract that an entity should conform to. In other words, an interface defines the syntax that any entity must adhere to.
- Interfaces define properties, methods, and events, which are the members of the interface. Interfaces contain only the declaration of the members. It is the responsibility of the deriving class to define the members. It often helps in providing a standard structure that the deriving classes would follow.

### Unions
- TypeScript 1.4 gives programs the ability to combine one or two types. Union types are a powerful way to express a value that can be one of the several types. Two or more data types are combined using the pipe symbol (|) to denote a Union Type. In other words, a union type is written as a sequence of types separated by vertical bars.

### Namespace
- A namespace is a way to logically group related code. This is inbuilt into TypeScript unlike in JavaScript where variables declarations go into a global scope and if multiple JavaScript files are used within same project there will be possibility of overwriting or misconstruing the same variables, which will lead to the “global namespace pollution problem” in JavaScript.

### Modules
- A module is designed with the idea to organize code written in TypeScript. Modules are broadly divided into −
  1. Internal Modules
    - Internal modules came in earlier version of Typescript. This was used to logically group classes, interfaces, functions into one unit and can be exported in another module. This logical grouping is named namespace in latest version of TypeScript.
  2. External Modules
    - External modules in TypeScript exists to specify and load dependencies between multiple external js files. If there is only one js file used, then external modules are not relevant. Traditionally dependency management between JavaScript files was done using browser script tags (<script></script>). But that’s not extendable, as its very linear while loading modules. That means instead of loading files one after other there is no asynchronous option to load modules. When you are programming js for the server for example NodeJs you don’t even have script tags.

### Ambient
- Ambient declarations are a way of telling the TypeScript compiler that the actual source code exists elsewhere. When you are consuming a bunch of third party js libraries like jquery/angularjs/nodejs you can’t rewrite it in TypeScript. Ensuring typesafety and intellisense while using these libraries will be challenging for a TypeScript programmer. Ambient declarations help to seamlessly integrate other js libraries into TypeScript.