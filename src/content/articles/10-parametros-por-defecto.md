---
titulo: Parámetros por Defecto
descripcionPrevia: Esta característica fue introducida en ES6 y facilita la escritura de código más claro y robusto.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---


# Parámetros por Defecto en JavaScript

En JavaScript, los parámetros por defecto permiten asignar un valor predeterminado a los parámetros de una función en caso de que no se proporcione uno durante su llamada. Esta característica fue introducida en ES6 y facilita la escritura de código más claro y robusto.

## Sintaxis de los Parámetros por Defecto

Para definir un parámetro por defecto, simplemente se asigna un valor al parámetro en la declaración de la función:

```javascript
function saludar(nombre = "Invitado") {
    console.log(`Hola, ${nombre}!`);
}

saludar(); // Salida: Hola, Invitado!
saludar("Ana"); // Salida: Hola, Ana!
```

En este ejemplo:

- Si no se proporciona un valor para `nombre`, se utiliza el valor por defecto "Invitado".
- Si se pasa un argumento, el valor predeterminado se sobrescribe.

## Ventajas de los Parámetros por Defecto

1. **Evitar Valores ****`undefined`**: Sin parámetros por defecto, un parámetro no proporcionado tendrá el valor `undefined`, lo que puede llevar a errores si no se maneja adecuadamente.
2. **Código Más Limpio**: Reduce la necesidad de comprobaciones manuales para asignar valores predeterminados.
3. **Mayor Legibilidad**: Facilita la comprensión de las intenciones de la función.

## Ejemplo: Funciones con Varios Parámetros

Los valores por defecto también se pueden combinar con otros parámetros:

```javascript
function crearUsuario(nombre = "Anónimo", edad = 18, esAdmin = false) {
    return {
        nombre: nombre,
        edad: edad,
        esAdmin: esAdmin
    };
}

console.log(crearUsuario());
// Salida: { nombre: "Anónimo", edad: 18, esAdmin: false }

console.log(crearUsuario("Carlos", 25));
// Salida: { nombre: "Carlos", edad: 25, esAdmin: false }
```

En este caso, solo se sobrescriben los parámetros que se especifican durante la llamada.

## Orden de los Parámetros por Defecto

Es posible utilizar valores de otros parámetros como valores por defecto, pero el parámetro utilizado debe haber sido declarado antes:

```javascript
function calcularPrecio(precioBase, impuesto = 0.15, descuento = precioBase * 0.1) {
    return precioBase + (precioBase * impuesto) - descuento;
}

console.log(calcularPrecio(100));
// Salida: 105 (100 + 15 - 10)

console.log(calcularPrecio(100, 0.2));
// Salida: 110 (100 + 20 - 10)
```

Si se intenta usar un parámetro declarado después como valor por defecto, se generará un error.

## Uso de Expresiones como Valores por Defecto

Los valores por defecto pueden ser resultados de expresiones o incluso funciones:

```javascript
function generarID() {
    return Math.floor(Math.random() * 10000);
}

function registrarUsuario(nombre = "Usuario", id = generarID()) {
    return { nombre, id };
}

console.log(registrarUsuario());
// Salida: { nombre: "Usuario", id: 1234 }

console.log(registrarUsuario("Ana"));
// Salida: { nombre: "Ana", id: 5678 }
```

Esto permite un alto nivel de personalización y flexibilidad en las funciones.

## Comparación con Comprobación Manual de Valores Predeterminados

Antes de ES6, los desarrolladores solían asignar valores predeterminados de manera manual:

```javascript
function sumar(a, b) {
    a = a || 0;
    b = b || 0;
    return a + b;
}

console.log(sumar()); // Salida: 0
console.log(sumar(5, 7)); // Salida: 12
```

Aunque funcional, este enfoque no permite manejar valores como `false`, `0` o `""` correctamente, ya que el operador `||` considera estos valores como falsos. Con parámetros por defecto:

```javascript
function sumar(a = 0, b = 0) {
    return a + b;
}

console.log(sumar()); // Salida: 0
console.log(sumar(5, 7)); // Salida: 12
```

Este método es más seguro y moderno.

---

Los parámetros por defecto son una herramienta poderosa para escribir funciones más limpias, comprensibles y robustas. Su combinación con otras características modernas de JavaScript hace que sean indispensables para el desarrollo eficiente y profesional.

