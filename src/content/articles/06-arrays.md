---
titulo: Arrays 
descripcionPrevia: Estructuras de datos fundamentales que permiten almacenar colecciones de elementos
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Arrays en JavaScript

Los arrays en JavaScript son estructuras de datos fundamentales que permiten almacenar colecciones de elementos, ya sean valores primitivos u objetos. Los arrays son dinámicos, lo que significa que su tamaño puede cambiar durante la ejecución del programa, y permiten realizar operaciones como agregar, eliminar y modificar elementos.

---

## Creación de Arrays

### Declaración de un array vacío
Un array puede ser creado utilizando corchetes (`[]`) o el constructor `Array`.
```javascript
// Usando corchetes
let miArray = [];

// Usando el constructor Array
let otroArray = new Array();
```

### Declaración con elementos iniciales
```javascript
let numeros = [1, 2, 3, 4, 5];
let colores = ["rojo", "azul", "verde"];
```

---

## Acceso a Elementos

Los elementos del array se acceden mediante índices, que comienzan desde 0.
```javascript
let frutas = ["manzana", "banana", "cereza"];

console.log(frutas[0]); // "manzana"
console.log(frutas[2]); // "cereza"

// Modificar un elemento
frutas[1] = "pera";
console.log(frutas); // ["manzana", "pera", "cereza"]
```

---

## Modificación de Arrays

### Agregar Elementos

- **`push()`**: Agrega uno o más elementos al final del array.
```javascript
let numeros = [1, 2, 3];
numeros.push(4);
console.log(numeros); // [1, 2, 3, 4]
```

- **`unshift()`**: Agrega uno o más elementos al inicio del array.
```javascript
numeros.unshift(0);
console.log(numeros); // [0, 1, 2, 3, 4]
```

### Eliminar Elementos

- **`pop()`**: Elimina el último elemento del array y lo devuelve.
```javascript
let ultimo = numeros.pop();
console.log(ultimo); // 4
console.log(numeros); // [0, 1, 2, 3]
```

- **`shift()`**: Elimina el primer elemento del array y lo devuelve.
```javascript
let primero = numeros.shift();
console.log(primero); // 0
console.log(numeros); // [1, 2, 3]
```

---

## Métodos Avanzados de Arrays

### `map()`
Crea un nuevo array aplicando una función a cada elemento del array original.
```javascript
let numeros = [1, 2, 3, 4];
let cuadrados = numeros.map(x => x ** 2);
console.log(cuadrados); // [1, 4, 9, 16]
```

### `filter()`
Crea un nuevo array con los elementos que cumplen una condición.
```javascript
let numeros = [10, 20, 30, 40];
let mayoresDe20 = numeros.filter(x => x > 20);
console.log(mayoresDe20); // [30, 40]
```

### `reduce()`
Reduce los elementos del array a un único valor aplicando una función acumulativa.
```javascript
let numeros = [1, 2, 3, 4];
let suma = numeros.reduce((acumulador, actual) => acumulador + actual, 0);
console.log(suma); // 10
```

---

## Ejemplo Completo

Combina varios métodos para manipular arrays.
```javascript
let estudiantes = ["Ana", "Luis", "María", "Pedro"];

// Agregar un estudiante al final
estudiantes.push("Laura");

// Eliminar el primero
let primerEstudiante = estudiantes.shift();

// Filtrar estudiantes cuyos nombres tienen más de 4 letras
let estudiantesFiltrados = estudiantes.filter(nombre => nombre.length > 4);

// Crear un array de la longitud de los nombres
let longitudes = estudiantes.map(nombre => nombre.length);

// Sumar la longitud total de los nombres
let totalLongitudes = longitudes.reduce((acc, len) => acc + len, 0);

console.log(estudiantes); // ["Luis", "María", "Pedro", "Laura"]
console.log(primerEstudiante); // "Ana"
console.log(estudiantesFiltrados); // ["María", "Pedro"]
console.log(longitudes); // [4, 5, 5, 5]
console.log(totalLongitudes); // 19
```

---

Los arrays son herramientas extremadamente poderosas en JavaScript. Dominar su creación, acceso y los métodos disponibles te permitirá trabajar de manera eficiente con datos en tus aplicaciones.

