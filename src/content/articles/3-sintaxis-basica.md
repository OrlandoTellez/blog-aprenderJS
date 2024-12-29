---
titulo: Sintaxis Básica de JavaScript
descripcionPrevia: En este artículo, exploraremos las bases de su sintaxis, incluyendo comentarios, variables, tipos de datos y operadores.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---
# Sintaxis Básica de JavaScript

JavaScript es un lenguaje de programación con una sintaxis clara y sencilla que permite a los desarrolladores crear desde interacciones simples en páginas web hasta aplicaciones completas. En este artículo, exploraremos las bases de su sintaxis, incluyendo comentarios, variables, tipos de datos y operadores.

## Comentarios
Los comentarios son textos que el navegador ignora al ejecutar el código. Se utilizan para explicar el código o deshabilitar temporalmente ciertas partes. JavaScript admite dos tipos de comentarios:

### Comentarios de una línea
Para escribir comentarios en una sola línea, se utiliza `//`:
```javascript
// Esto es un comentario de una línea
console.log("Hola, mundo!"); // Este comentario está al lado del código
```

### Comentarios de varias líneas
Para comentarios más largos, se usa `/* */`:
```javascript
/*
Este es un comentario
que ocupa varias líneas.
*/
console.log("Hola, mundo!");
```

## Variables
Las variables son contenedores para almacenar datos. En JavaScript, hay tres formas principales de declararlas: `var`, `let` y `const`.

### `var`
Fue la forma original de declarar variables. Su ámbito es global o de función, y puede ser redeclarada. Sin embargo, su uso se desaconseja en favor de `let` y `const`.
```javascript
var saludo = "Hola";
console.log(saludo);
```

### `let`
Introducida en ES6, permite declarar variables con ámbito de bloque, lo que significa que solo están disponibles dentro del bloque donde se definen.
```javascript
let nombre = "Juan";
if (true) {
    let nombre = "Ana";
    console.log(nombre); // Ana
}
console.log(nombre); // Juan
```

### `const`
Se utiliza para declarar constantes, es decir, valores que no cambian una vez asignados. También tiene ámbito de bloque.
```javascript
const pi = 3.1416;
console.log(pi);
// pi = 3.14; // Esto arrojará un error
```

## Tipos de datos
JavaScript tiene varios tipos de datos primitivos y uno complejo principal.

### Tipos primitivos

- **Números**: Representan valores numéricos, tanto enteros como de punto flotante.
  ```javascript
  let edad = 25;
  let precio = 19.99;
  ```

- **Cadenas**: Representan texto. Se pueden usar comillas simples, dobles o backticks.
  ```javascript
  let mensaje = 'Hola';
  let saludo = "Mundo";
  let plantilla = `Hola, ${saludo}`;
  ```

- **Booleanos**: Solo tienen dos valores posibles: `true` o `false`.
  ```javascript
  let esVerdadero = true;
  let esFalso = false;
  ```

- **Undefined**: Indica que una variable está declarada pero no tiene un valor asignado.
  ```javascript
  let indefinido;
  console.log(indefinido); // undefined
  ```

- **Null**: Representa la ausencia intencional de un valor.
  ```javascript
  let vacio = null;
  ```

- **Symbol**: Un tipo especial introducido en ES6, utilizado para identificadores únicos.
  ```javascript
  let simbolo = Symbol("identificador");
  ```

### Tipo complejo
- **Object**: Se utiliza para colecciones de datos y entidades más complejas.
  ```javascript
  let persona = {
      nombre: "Carlos",
      edad: 30
  };
  console.log(persona.nombre); // Carlos
  ```

## Operadores
Los operadores permiten realizar diferentes operaciones con valores y variables.

### Operadores aritméticos
Realizan operaciones matemáticas básicas:
```javascript
let suma = 5 + 3; // 8
let resta = 5 - 3; // 2
let multiplicacion = 5 * 3; // 15
let division = 5 / 3; // 1.666...
let modulo = 5 % 3; // 2
let potencia = 5 ** 3; // 125
```

### Operadores lógicos
Trabajan con valores booleanos:
```javascript
let verdadero = true && true; // true
let falso = true && false; // false
let o = true || false; // true
let negacion = !true; // false
```

### Operadores de comparación
Comparan dos valores y devuelven un booleano:
```javascript
let igual = 5 == "5"; // true (comparación débil)
let estrictamenteIgual = 5 === "5"; // false (comparación estricta)
let diferente = 5 != "5"; // false
let estrictamenteDiferente = 5 !== "5"; // true
let mayor = 5 > 3; // true
let menor = 5 < 3; // false
let mayorIgual = 5 >= 3; // true
let menorIgual = 5 <= 3; // false
```

---

Con este conocimiento básico, ya tienes las bases para comenzar a escribir código en JavaScript. A medida que avances, explorarás temas más avanzados, pero dominar la sintaxis básica es fundamental para cualquier desarrollador.

