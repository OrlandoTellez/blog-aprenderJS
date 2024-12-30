---
titulo: Funciones
descripcionPrevia: Aprenderás todo sobre las funciones, desde su declaración básica hasta el uso de parámetros y valores de retorno
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Funciones en JavaScript

Las funciones son bloques de código reutilizables que realizan una tarea específica. En JavaScript, son uno de los conceptos fundamentales, ya que permiten estructurar, modularizar y reutilizar código de manera eficiente. En este artículo aprenderás todo sobre las funciones, desde su declaración básica hasta el uso de parámetros y valores de retorno, acompañado de ejemplos claros.

---

## ¿Qué es una función?

Una función es un conjunto de instrucciones agrupadas para realizar una tarea específica. Puedes llamarla varias veces en tu código, lo que mejora la reutilización y la legibilidad.

```javascript
function saludar() {
    console.log("Hola, mundo!");
}

// Llamar a la función
saludar(); // Salida: Hola, mundo!
```

En este ejemplo, la función `saludar` imprime un mensaje en la consola cada vez que se llama.

---

## Declaración de funciones

Hay varias formas de declarar funciones en JavaScript. A continuación, exploraremos las más comunes.

### 1. Declaración de función (Function Declaration)

Esta es la forma clásica de declarar una función. La sintaxis comienza con la palabra clave `function`, seguida del nombre de la función, paréntesis y un bloque de código.

```javascript
function sumar(a, b) {
    return a + b;
}

console.log(sumar(5, 3)); // Salida: 8
```

### 2. Expresión de función (Function Expression)

Las funciones también se pueden asignar a variables. Estas son funciones anónimas (sin nombre) almacenadas en una variable.

```javascript
const restar = function(a, b) {
    return a - b;
};

console.log(restar(10, 4)); // Salida: 6
```

### 3. Funciones flecha (Arrow Functions)

Introducidas en ES6, las funciones flecha son una forma concisa de escribir funciones. No tienen su propio `this`, lo que las hace ideales para callbacks.

```javascript
const multiplicar = (a, b) => a * b;

console.log(multiplicar(4, 5)); // Salida: 20
```

Si la función tiene solo un parámetro o una sola línea de código, los paréntesis y las llaves son opcionales.

---

## Parámetros y Argumentos

### Parámetros

Los parámetros son variables que se definen entre los paréntesis de una función. Puedes especificar tantos parámetros como necesites.

```javascript
function saludar(nombre) {
    console.log(`Hola, ${nombre}!`);
}

saludar("Carlos"); // Salida: Hola, Carlos!
saludar("Ana");    // Salida: Hola, Ana!
```

### Argumentos

Cuando llamas a una función, los valores que pasas a los parámetros se llaman argumentos.

```javascript
function sumar(a, b) {
    console.log(`Argumento 1: ${a}`);
    console.log(`Argumento 2: ${b}`);
    return a + b;
}

sumar(3, 7); // Salida: Argumento 1: 3; Argumento 2: 7
```

### Parámetros por defecto

Puedes asignar valores predeterminados a los parámetros en caso de que no se proporcionen argumentos al llamar a la función.

```javascript
function saludar(nombre = "invitado") {
    console.log(`Hola, ${nombre}!`);
}

saludar(); // Salida: Hola, invitado!
saludar("Luis"); // Salida: Hola, Luis!
```

---

## Valores de Retorno

Una función puede devolver un valor utilizando la palabra clave `return`. Cuando se alcanza un `return`, la ejecución de la función se detiene.

```javascript
function areaRectangulo(base, altura) {
    return base * altura;
}

let resultado = areaRectangulo(5, 10);
console.log(resultado); // Salida: 50
```

Si una función no tiene un `return`, devuelve `undefined` por defecto.

```javascript
function sinRetorno() {
    console.log("Esta función no devuelve nada.");
}

let valor = sinRetorno();
console.log(valor); // Salida: undefined
```

---

## Ejemplos Completos

### Función para calcular el factorial de un número

El factorial de un número \(n!\) se calcula como el producto de todos los números enteros positivos hasta \(n\).

```javascript
function factorial(n) {
    if (n === 0 || n === 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

console.log(factorial(5)); // Salida: 120
```

### Función para verificar si un número es par o impar

```javascript
function esPar(numero) {
    return numero % 2 === 0;
}

console.log(esPar(4)); // Salida: true
console.log(esPar(7)); // Salida: false
```

### Función con parámetros y valores predeterminados

```javascript
function crearSaludo(nombre = "Visitante", hora = "día") {
    return `Buen ${hora}, ${nombre}!`;
}

console.log(crearSaludo()); // Salida: Buen día, Visitante!
console.log(crearSaludo("Laura", "tarde")); // Salida: Buen tarde, Laura!
```

---

Con esta guía, tienes un conocimiento detallado de las funciones en JavaScript, desde cómo declararlas hasta cómo trabajar con parámetros y valores de retorno. Practica implementando tus propias funciones para resolver problemas y automatizar tareas en tu código.

