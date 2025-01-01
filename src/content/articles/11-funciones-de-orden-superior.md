---
titulo: Funciones de Orden Superior
descripcionPrevia: Las funciones de orden superior son un concepto fundamental en JavaScript, especialmente en la programación funcional.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Funciones de Orden Superior en JavaScript

Las **funciones de orden superior** son un concepto fundamental en JavaScript, especialmente en la programación funcional. Una función se considera de orden superior si cumple con al menos una de estas condiciones:

1. Recibe otra función como argumento.
2. Devuelve una función como resultado.

Estas funciones son ampliamente utilizadas para manejar datos y procesos de manera eficiente y expresiva.

## Concepto Básico

En JavaScript, las funciones son ciudadanos de primera clase (*first-class citizens*), lo que significa que pueden ser tratadas como cualquier otro valor: asignadas a variables, pasadas como argumentos, o devueltas por otras funciones. Esto permite la creación de funciones de orden superior.

### Ejemplo Simple
```javascript
function operar(num1, num2, operacion) {
    return operacion(num1, num2);
}

const suma = (a, b) => a + b;
const resta = (a, b) => a - b;

console.log(operar(5, 3, suma)); // 8
console.log(operar(5, 3, resta)); // 2
```
En este ejemplo, la función `operar` es de orden superior porque recibe una función (`suma` o `resta`) como argumento.

---

## Ejemplos Comunes de Funciones de Orden Superior

### Métodos de Arrays
Muchos métodos de los arrays son funciones de orden superior porque aceptan funciones como argumentos.

#### `map()`
Crea un nuevo array aplicando una función a cada elemento del array original.
```javascript
const numeros = [1, 2, 3, 4];
const cuadrados = numeros.map(num => num ** 2);
console.log(cuadrados); // [1, 4, 9, 16]
```

#### `filter()`
Crea un nuevo array con todos los elementos que cumplen una condición.
```javascript
const edades = [18, 21, 16, 40];
const mayores = edades.filter(edad => edad >= 18);
console.log(mayores); // [18, 21, 40]
```

#### `reduce()`
Reduce el array a un único valor acumulando los resultados de una función.
```javascript
const numeros = [1, 2, 3, 4];
const sumaTotal = numeros.reduce((acumulador, valorActual) => acumulador + valorActual, 0);
console.log(sumaTotal); // 10
```

---

## Retornar Funciones
Otra capacidad de las funciones de orden superior es devolver nuevas funciones.

### Ejemplo: Generador de saludos
```javascript
function crearSaludo(saludoInicial) {
    return function(nombre) {
        return `${saludoInicial}, ${nombre}!`;
    };
}

const saludoEnEspanol = crearSaludo("Hola");
const saludoEnIngles = crearSaludo("Hello");

console.log(saludoEnEspanol("Juan")); // Hola, Juan!
console.log(saludoEnIngles("John")); // Hello, John!
```
En este caso, `crearSaludo` devuelve una nueva función personalizada para un saludo específico.

---

## Composición de Funciones
La composición de funciones es una técnica que combina funciones pequeñas para construir funciones más complejas.

### Ejemplo
```javascript
const agregar = x => x + 1;
const multiplicar = x => x * 2;

const combinarFunciones = (x) => multiplicar(agregar(x));
console.log(combinarFunciones(5)); // 12
```
Aquí, la salida de `agregar` se utiliza como entrada para `multiplicar`.

---

## Uso en Programación Asíncrona
Las funciones de orden superior son comunes en el manejo de promesas y operaciones asíncronas.

### Ejemplo con `then`
```javascript
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```
En este caso, las funciones pasadas a `then` y `catch` son funciones de orden superior que procesan el resultado de las promesas.

---

## Ventajas de las Funciones de Orden Superior
- **Reutilización de código:** Permiten encapsular lógica común en funciones reutilizables.
- **Legibilidad:** Hacen que el código sea más declarativo y fácil de entender.
- **Modularidad:** Dividen las tareas complejas en funciones más pequeñas y manejables.

---

Las funciones de orden superior son una herramienta poderosa que todo desarrollador de JavaScript debe dominar. Desde manipular datos en arrays hasta manejar procesos asíncronos, su utilidad es clave para escribir código limpio, eficiente y expresivo.

