---
titulo: Metodos de cadena
descripcionPrevia: JavaScript proporciona una amplia variedad de métodos que permiten trabajar y manipular Strings
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Cadenas de Texto en JavaScript

Las cadenas de texto (o strings) son un tipo de dato primitivo en JavaScript que se utilizan para representar texto. JavaScript proporciona una amplia variedad de métodos que permiten trabajar y manipular cadenas de forma fácil y eficiente.

## Creación de cadenas

En JavaScript, las cadenas pueden definirse utilizando comillas simples, dobles o backticks (para cadenas de plantillas):

```javascript
let simple = 'Hola';
let doble = "Mundo";
let plantilla = `Hola, ${doble}`;
console.log(plantilla); // Hola, Mundo
```

## Propiedad `length`

La propiedad `length` devuelve la longitud de la cadena, es decir, el número de caracteres que contiene:

```javascript
let saludo = "Hola, mundo!";
console.log(saludo.length); // 12
```

## Métodos comunes de cadenas

### `slice()`
Extrae una porción de una cadena y devuelve una nueva. Recibe dos parámetros: el índice de inicio (incluido) y el índice de fin (excluido).

```javascript
let texto = "JavaScript es genial";
let parte = texto.slice(0, 10);
console.log(parte); // JavaScript
```

### `substring()`
Es similar a `slice()`, pero no acepta índices negativos.

```javascript
let texto = "JavaScript es genial";
let parte = texto.substring(0, 10);
console.log(parte); // JavaScript
```

### `toUpperCase()` y `toLowerCase()`
Estos métodos convierten una cadena a mayúsculas o minúsculas, respectivamente.

```javascript
let texto = "JavaScript";
console.log(texto.toUpperCase()); // JAVASCRIPT
console.log(texto.toLowerCase()); // javascript
```

### `trim()`
Elimina los espacios en blanco al inicio y al final de la cadena.

```javascript
let texto = "   Hola, mundo!   ";
console.log(texto.trim()); // "Hola, mundo!"
```

### `includes()`
Verifica si una cadena contiene un texto específico. Devuelve `true` o `false`.

```javascript
let texto = "Aprender JavaScript es divertido";
console.log(texto.includes("JavaScript")); // true
console.log(texto.includes("Python")); // false
```

### `indexOf()` y `lastIndexOf()`
`indexOf()` devuelve el índice de la primera aparición de un texto; `lastIndexOf()` busca desde el final.

```javascript
let texto = "JavaScript es genial. Aprender JavaScript es útil.";
console.log(texto.indexOf("JavaScript")); // 0
console.log(texto.lastIndexOf("JavaScript")); // 31
```

### `replace()` y `replaceAll()`
Reemplaza una subcadena por otra. `replace()` solo afecta la primera coincidencia, mientras que `replaceAll()` afecta a todas.

```javascript
let texto = "JavaScript es genial, y JavaScript es versátil.";
console.log(texto.replace("JavaScript", "JS")); // "JS es genial, y JavaScript es versátil."
console.log(texto.replaceAll("JavaScript", "JS")); // "JS es genial, y JS es versátil."
```

### `split()`
Divide una cadena en un array según un delimitador especificado.

```javascript
let texto = "rojo,verde,azul";
let colores = texto.split(",");
console.log(colores); // ["rojo", "verde", "azul"]
```

### `concat()`
Une dos o más cadenas en una sola.

```javascript
let saludo = "Hola";
let mundo = "mundo";
console.log(saludo.concat(", ", mundo, "!")); // "Hola, mundo!"
```

### `charAt()` y `charCodeAt()`
`charAt()` devuelve el caracter en un índice específico, mientras que `charCodeAt()` devuelve el código Unicode del caracter.

```javascript
let texto = "JavaScript";
console.log(texto.charAt(0)); // J
console.log(texto.charCodeAt(0)); // 74
```

### `startsWith()` y `endsWith()`
Verifican si una cadena comienza o termina con un texto específico.

```javascript
let texto = "JavaScript es genial";
console.log(texto.startsWith("Java")); // true
console.log(texto.endsWith("genial")); // true
```

---

Con estos métodos y propiedades, puedes manipular cadenas de texto de forma eficiente y flexible en tus proyectos JavaScript. Practica combinando varios de estos métodos para resolver problemas complejos con cadenas.

