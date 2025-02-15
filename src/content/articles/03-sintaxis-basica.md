---
titulo: Sintaxis Básica 
descripcionPrevia: En este artículo, exploraremos las bases de su sintaxis, incluyendo comentarios, variables, tipos de datos y operadores.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Sintaxis Básica de JavaScript

JavaScript es el lenguaje que da vida a las páginas web. Su sintaxis es clara y amigable, lo que lo hace perfecto para crear desde pequeñas interacciones hasta aplicaciones completas. En este artículo, aprenderás lo esencial: cómo escribir comentarios, declarar variables, utilizar diferentes tipos de datos y aplicar operadores.

---

## Comentarios

Los comentarios son notas que escribes en el código para recordar o explicar lo que hace cada parte, ¡y el navegador los ignora! Son muy útiles para ti y para otros que lean tu código. Hay dos formas de escribirlos:

### Comentarios de una línea

Usa `//` para comentar una sola línea. Por ejemplo:

```javascript
// Esto es un comentario de una línea
console.log("¡Hola, mundo!"); // También puedes colocar un comentario al lado del código
```

### Comentarios de varias líneas

Para comentarios más largos, utiliza `/*` para iniciar y `*/` para cerrar el comentario:

```javascript
/*
Este es un comentario
que abarca varias líneas.
Se usa para explicar secciones más complejas.
*/
console.log("¡Hola, mundo!");
```

---

## Variables

Las variables son como cajitas donde guardas información (números, textos, etc.). En JavaScript, existen tres maneras principales de declarar variables: `var`, `let` y `const`.

### `var`

Es la forma tradicional de declarar una variable. Tiene un alcance global o dentro de una función, lo que puede llevar a errores si no se usa con cuidado.  
*Ejemplo:*

```javascript
var saludo = "Hola";
console.log(saludo);
```

### `let`

Introducido en ES6, `let` te permite crear variables con un alcance de bloque, lo que significa que solo se usan dentro del bloque donde las defines.  
*Ejemplo:*

```javascript
let nombre = "Juan";
if (true) {
    let nombre = "Ana";
    console.log(nombre); // Imprime "Ana"
}
console.log(nombre); // Imprime "Juan"
```

### `const`

Se usa para declarar constantes, es decir, valores que no cambiarán una vez definidos. También tiene alcance de bloque.  
*Ejemplo:*

```javascript
const pi = 3.1416;
console.log(pi);
// pi = 3.14; // Esto causará un error porque no se puede cambiar una constante
```

---

## Tipos de Datos

JavaScript maneja diferentes tipos de datos que te permiten almacenar información de distintas maneras.

### Tipos Primitivos

- **Números:** Se usan para valores numéricos, ya sean enteros o decimales.
  ```javascript
  let edad = 25;
  let precio = 19.99;
  ```

- **Cadenas (Strings):** Representan textos y se pueden escribir entre comillas simples, dobles o con backticks (para incluir variables).
  ```javascript
  let mensaje = 'Hola';
  let saludo = "Mundo";
  let plantilla = `Hola, ${saludo}`;
  ```

- **Booleanos:** Solo pueden tener dos valores: `true` o `false`.
  ```javascript
  let esVerdadero = true;
  let esFalso = false;
  ```

- **Undefined:** Significa que una variable ha sido declarada pero no se le ha asignado ningún valor.
  ```javascript
  let sinValor;
  console.log(sinValor); // Imprime undefined
  ```

- **Null:** Indica la ausencia intencional de valor.
  ```javascript
  let vacio = null;
  ```

- **Symbol:** Es un tipo especial usado para crear identificadores únicos (se usa en casos más avanzados).
  ```javascript
  let idUnico = Symbol("id");
  ```

### Tipo Complejo

- **Object:** Se utiliza para agrupar datos y funcionalidades en una sola estructura.
  ```javascript
  let persona = {
      nombre: "Carlos",
      edad: 30
  };
  console.log(persona.nombre); // Imprime "Carlos"
  ```

---

## Operadores

Los operadores te permiten realizar acciones con los valores y variables, como hacer cálculos o comparar datos.

### Operadores Aritméticos

Sirven para realizar operaciones matemáticas básicas:
```javascript
let suma = 5 + 3;           // 8
let resta = 5 - 3;          // 2
let multiplicacion = 5 * 3; // 15
let division = 5 / 3;       // 1.666...
let modulo = 5 % 3;         // 2 (resto de la división)
let potencia = 5 ** 3;      // 125
```

### Operadores Lógicos

Se utilizan para combinar condiciones y trabajar con valores booleanos:
```javascript
let ambosVerdaderos = true && true;   // true
let unoFalso = true && false;           // false
let alMenosUno = true || false;         // true
let negacion = !true;                   // false
```

### Operadores de Comparación

Permiten comparar valores y devuelven un resultado booleano:
```javascript
let igual = 5 == "5";               // true (compara solo el valor)
let estrictamenteIgual = 5 === "5"; // false (compara valor y tipo)
let diferente = 5 != "5";           // false
let estrictamenteDiferente = 5 !== "5"; // true
let mayor = 5 > 3;                  // true
let menor = 5 < 3;                  // false
let mayorIgual = 5 >= 3;            // true
let menorIgual = 5 <= 3;            // false
```

---

## Conclusión

Con estos conceptos básicos, ya tienes lo esencial para comenzar a escribir tus primeros programas en JavaScript. Practica cada uno de estos elementos y verás cómo, poco a poco, tu código se vuelve más fluido y poderoso. ¡La práctica es la clave para dominar cualquier lenguaje de programación!


