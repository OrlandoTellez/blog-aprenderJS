---
titulo: Funciones Asíncronas y "async/await"
descripcionPrevia: Las funciones asíncronas son una característica clave de JavaScript que permite manejar operaciones asíncronas de forma más clara y sencilla.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---


### Funciones Asíncronas y `async/await` en JavaScript

Las funciones asíncronas son una característica clave de JavaScript que permite manejar operaciones asíncronas de forma más clara y sencilla, reemplazando el uso de callbacks anidados y mejorando la legibilidad del código. En este artículo, aprenderás qué son las funciones asíncronas, cómo utilizar `async/await`, y cómo manejar errores en este contexto.

---

## ¿Qué es una Función Asíncrona?

Una función asíncrona es aquella que devuelve una **promesa** de forma implícita. Estas funciones permiten escribir código asíncrono que parece sincrónico, facilitando la lectura y el mantenimiento.

### Declaración de una Función Asíncrona

Se utiliza la palabra clave `async` antes de la declaración de la función:
```javascript
async function obtenerDatos() {
    return "Datos obtenidos";
}

// Equivalente a:
function obtenerDatos() {
    return Promise.resolve("Datos obtenidos");
}

obtenerDatos().then((resultado) => console.log(resultado)); // Datos obtenidos
```

---

## Uso de `await` 

El operador `await` solo puede ser utilizado dentro de una función declarada como `async`. Pausa la ejecución de la función hasta que una **promesa** se resuelve o se rechaza.

### Ejemplo Básico de `await`
```javascript
async function ejemploAwait() {
    const promesa = new Promise((resolve) => {
        setTimeout(() => resolve("¡Resuelto!"), 2000);
    });

    const resultado = await promesa; // Pausa hasta que la promesa se resuelve
    console.log(resultado); // ¡Resuelto!
}

ejemploAwait();
```

---

## Caso de Uso: Llamadas a una API

Veamos cómo las funciones asíncronas y `await` simplifican las operaciones de red.

### Sin `async/await`:
```javascript
function obtenerUsuarios() {
    fetch("https://jsonplaceholder.typicode.com/users")
        .then((respuesta) => respuesta.json())
        .then((usuarios) => console.log(usuarios))
        .catch((error) => console.error(error));
}
obtenerUsuarios();
```

### Con `async/await`:
```javascript
async function obtenerUsuarios() {
    try {
        const respuesta = await fetch("https://jsonplaceholder.typicode.com/users");
        const usuarios = await respuesta.json();
        console.log(usuarios);
    } catch (error) {
        console.error("Error al obtener los usuarios:", error);
    }
}
obtenerUsuarios();
```

Como puedes ver, el uso de `async/await` hace que el flujo del código sea más claro y lineal.

---

## Manejo de Errores en Funciones Asíncronas

Para manejar errores en funciones asíncronas, utilizamos bloques `try...catch`.

### Ejemplo:
```javascript
async function obtenerDatosConError() {
    try {
        const respuesta = await fetch("https://url-invalida.com");
        const datos = await respuesta.json();
        console.log(datos);
    } catch (error) {
        console.error("Ocurrió un error:", error);
    }
}
obtenerDatosConError();
```

Si la promesa rechaza (por ejemplo, debido a un error de red), el flujo se transfiere al bloque `catch`.

---

## Funciones Asíncronas en Funciones Flecha

Las funciones flecha también pueden ser declaradas como asíncronas añadiendo `async` al inicio:
```javascript
const obtenerMensaje = async () => {
    const promesa = new Promise((resolve) => setTimeout(() => resolve("Hola Async!"), 1000));
    const mensaje = await promesa;
    console.log(mensaje); // Hola Async!
};

obtenerMensaje();
```

---

## Combinando Múltiples `await`

Cuando tienes varias operaciones asíncronas que dependen unas de otras, puedes usar múltiples `await` en una sola función.

### Ejemplo:
```javascript
async function flujoAsincrono() {
    const primero = await new Promise((resolve) => setTimeout(() => resolve("Primero"), 1000));
    console.log(primero);

    const segundo = await new Promise((resolve) => setTimeout(() => resolve("Segundo"), 1000));
    console.log(segundo);

    const tercero = await new Promise((resolve) => setTimeout(() => resolve("Tercero"), 1000));
    console.log(tercero);
}

flujoAsincrono();
// Salida:
// Primero (después de 1 segundo)
// Segundo (después de 2 segundos en total)
// Tercero (después de 3 segundos en total)
```

---

## Ejecutando Tareas en Paralelo con `Promise.all`

Si las operaciones asíncronas no dependen unas de otras, puedes ejecutarlas en paralelo con `Promise.all`, lo que reduce el tiempo total.

### Ejemplo:
```javascript
async function enParalelo() {
    const [primero, segundo, tercero] = await Promise.all([
        new Promise((resolve) => setTimeout(() => resolve("Primero"), 1000)),
        new Promise((resolve) => setTimeout(() => resolve("Segundo"), 1000)),
        new Promise((resolve) => setTimeout(() => resolve("Tercero"), 1000))
    ]);

    console.log(primero, segundo, tercero); // Primero Segundo Tercero (todos después de 1 segundo)
}

enParalelo();
```

---

## Ventajas de `async/await`

1. **Legibilidad mejorada**: Código más lineal y fácil de entender.
2. **Reducción de anidaciones**: Elimina el "infierno de callbacks".
3. **Manejo claro de errores**: La combinación con `try...catch` hace que sea fácil de manejar errores.

---

## Conclusión

Las funciones asíncronas y `async/await` son herramientas esenciales para manejar operaciones asíncronas en JavaScript. Con su capacidad para simplificar el código y mejorar la legibilidad, se han convertido en un estándar en el desarrollo moderno. Dominar estas características te permitirá escribir código más limpio, eficiente y mantenible.