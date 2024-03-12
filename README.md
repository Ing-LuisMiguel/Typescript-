**Características de TypeScript:**

**Static type-checking:**

Definición: Proceso de verificación estática de tipos durante la compilación para detectar posibles errores y mejorar la robustez del código.
Ejemplo:

let nombre: string = "Juan";
// Error en tiempo de compilación al intentar asignar un número a una cadena
// nombre = 123;

**Non-exception Failures:**

Significado: Enfoque para manejar errores sin depender de excepciones tradicionales, común en lenguajes funcionales.
Ejemplo:

function dividir(a: number, b: number): number {
    // No arroja una excepción, pero puede llevar a resultados inesperados
    return a / b;
}


**Types for Tooling:**

Concepto: Uso de anotaciones de tipos para mejorar herramientas de desarrollo como autocompletado y análisis estático.
Ejemplo:

interface Persona {
    nombre: string;
    edad: number;
}

const usuario: Persona = {
    nombre: "Alicia",
    edad: 30,
};

// El editor puede proporcionar autocompletado y sugerencias basadas en tipos
usuario.


**tsc, the TypeScript compiler:**

Explicación: Herramienta de línea de comandos para compilar archivos TypeScript a JavaScript y otras operaciones relacionadas.
Ejemplo:

tsc ejemplo.ts


**Emitting with Errors:**

Descripción: Configuración que permite generar archivos de salida incluso con errores en el código fuente TypeScript.
Ejemplo:

function saludar(nombre: string) {
    // Genera código JavaScript a pesar de un error (falta punto y coma)
    console.log("¡Hola, " + nombre)
}


**Explicit Types:**

Definición: Práctica que implica especificar claramente los tipos de datos en variables, parámetros y valores de retorno.
Ejemplo:

function sumarNumeros(a: number, b: number): number {
    // Tipos de parámetros y valor de retorno especificados explícitamente
    return a + b;
}


**Erased Types:**

Significado: Eliminación de información de tipos durante la compilación para mejorar el rendimiento y la interoperabilidad.
Ejemplo:

interface Producto {
    nombre: string;
    precio: number;
}

const laptop: Producto = {
    nombre: "Laptop",
    precio: 1200,
};

// La información de tipos se elimina durante la compilación


**Downleveling:**

Explicación: Proceso que convierte código TypeScript a versiones más antiguas de ECMAScript para garantizar la compatibilidad.
Ejemplo:

// Código TypeScript dirigido a ECMAScript 2015 (ES6)
const arrowFunction = () => console.log("¡Hola, función de flecha!");
// Comando para compilar con reducción de nivel a ECMAScript 3
// tsc --target es3 nombredelarchivo.ts


**Strictness:**

Concepto: Nivel de rigurosidad en la verificación de tipos para capturar errores comunes durante el desarrollo.
Ejemplo:

// Activar la bandera noImplicitAny evita el uso implícito de 'any'
function multiplicar(a: number, b) {
    // Error: El parámetro 'b' tiene implícitamente un tipo 'any'
    return a * b;
}


**noImplicitAny:**

Explicación: Configuración que genera un error si el compilador no puede inferir el tipo de una variable, evitando el uso implícito de any.
Ejemplo:

// Activar noImplicitAny genera un error si el compilador no puede inferir el tipo
function multiplicar(a: number, b) {
    // Error: El parámetro 'b' tiene implícitamente un tipo 'any'
    return a * b;
}

// Añadiendo la anotación de tipo para evitar el error
function multiplicarConTipos(a: number, b: number): number {
    return a * b;
}


**strictNullChecks:**

Significado: Mejora la seguridad al obligar a considerar explícitamente los valores nulos y undefined en el sistema de tipos.
Ejemplo:

// Al activar strictNullChecks, se requiere manejo explícito de null y undefined
let nombreUsuario: string | null = "Juan";
// Error: El objeto posiblemente es 'null'
console.log(nombreUsuario.length);
