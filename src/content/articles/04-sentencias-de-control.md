---
titulo: Sentencias de control 
descripcionPrevia: Exploraremos las principales estructuras de control, incluidas las condicionales y los bucles.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---
# Sentencias de Control en JavaScript

Las sentencias de control en JavaScript permiten alterar el flujo de ejecución del programa dependiendo de ciertas condiciones o repetir bloques de código mientras se cumplan criterios específicos. En este artículo, exploraremos las principales estructuras de control, incluidas las condicionales y los bucles.

---

## Condicionales
Las estructuras condicionales permiten que el código se ejecute solo si se cumple una condición específica.

### `if`
La sentencia `if` evalúa una condición y ejecuta un bloque de código si la condición es verdadera.

```javascript
let edad = 18;
if (edad >= 18) {
    console.log("Eres mayor de edad.");
}
```

### `if...else`
La sentencia `if...else` permite manejar un caso adicional para cuando la condición no se cumple.

```javascript
let hora = 15;
if (hora < 12) {
    console.log("Buenos días.");
} else {
    console.log("Buenas tardes.");
}
```

### `if...else if...else`
Esta estructura permite evaluar múltiples condiciones en cascada.

```javascript
let nota = 85;
if (nota >= 90) {
    console.log("Excelente");
} else if (nota >= 70) {
    console.log("Aprobado");
} else {
    console.log("Reprobado");
}
```

### `switch`
El `switch` evalúa una expresión y ejecuta el bloque de código que coincide con el valor de la expresión. Se usa `break` para detener la ejecución y evitar pasar a otros casos.

```javascript
let dia = "lunes";
switch (dia) {
    case "lunes":
        console.log("Inicio de semana.");
        break;
    case "viernes":
        console.log("Casi fin de semana.");
        break;
    default:
        console.log("Es un día normal.");
}
```

---

## Bucles
Los bucles permiten ejecutar un bloque de código repetidamente mientras se cumpla una condición.

### `for`
El bucle `for` es ideal cuando se conoce de antemano el número de iteraciones.

```javascript
for (let i = 0; i < 5; i++) {
    console.log(`Iteración: ${i}`);
}
```

### `while`
El bucle `while` ejecuta el bloque de código mientras la condición sea verdadera.

```javascript
let contador = 0;
while (contador < 5) {
    console.log(`Contador: ${contador}`);
    contador++;
}
```

### `do...while`
El bucle `do...while` asegura que el bloque de código se ejecute al menos una vez antes de evaluar la condición.

```javascript
let numero = 0;
do {
    console.log(`Número: ${numero}`);
    numero++;
} while (numero < 5);
```

---

## Diferencias clave entre bucles

1. **`for` vs. `while`**:
   - Usa `for` cuando sabes exactamente cuántas veces iterarás.
   - Usa `while` cuando no estás seguro de cuántas veces se ejecutará el bucle, pero depende de una condición.

2. **`while` vs. `do...while`**:
   - Usa `while` cuando quieras evaluar la condición antes de ejecutar el código.
   - Usa `do...while` cuando necesites que el bloque de código se ejecute al menos una vez.

---

## Ejemplo combinado
A continuación, se muestra un ejemplo que combina condicionales y bucles:

```javascript
let numeros = [1, 2, 3, 4, 5];
for (let i = 0; i < numeros.length; i++) {
    if (numeros[i] % 2 === 0) {
        console.log(`${numeros[i]} es par.`);
    } else {
        console.log(`${numeros[i]} es impar.`);
    }
}
```

Con estas estructuras de control, puedes crear programas más dinámicos y flexibles en JavaScript, controlando el flujo de ejecución y optimizando tus soluciones a problemas específicos.

