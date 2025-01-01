---
titulo: Callbacks y Promesas
descripcionPrevia: ¿Qué son los callbacks y promesas? cómo funcionan y cómo usarlos correctamente es sobre de lo que trata este artículo.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Callbacks y Promesas en JavaScript

En JavaScript, manejar operaciones asíncronas es fundamental para construir aplicaciones modernas y eficientes. Dos de las herramientas más importantes para este propósito son los callbacks y las promesas. Este artículo explora qué son, cómo funcionan, y cómo usarlos correctamente.

---

## Callbacks

Un **callback** es una función que se pasa como argumento a otra función para que sea ejecutada más tarde. Los callbacks son una forma tradicional de manejar código asíncrono en JavaScript.

### Ejemplo de Callback

```javascript
function procesarUsuario(nombre, callback) {
    console.log(`Hola, ${nombre}`);
    callback();
}

function despedida() {
    console.log("Adios!");
}

procesarUsuario("Carlos", despedida);
// Salida:
// Hola, Carlos
// Adios!
```

En este ejemplo, la función `despedida` se pasa como un callback a `procesarUsuario` y se ejecuta después de que `procesarUsuario` muestra el saludo.

### Callbacks en Operaciones Asíncronas

Un uso típico de los callbacks es en operaciones como temporizadores o solicitudes HTTP.

```javascript
setTimeout(() => {
    console.log("Esto se ejecuta después de 2 segundos");
}, 2000);
```

Aunque los callbacks son poderosos, pueden conducir al "Callback Hell" cuando se anidan demasiados, dificultando la lectura y el mantenimiento del código.

---

## Promesas

Las **promesas** son una alternativa moderna para manejar operaciones asíncronas. Representan un valor que puede estar disponible ahora, en el futuro, o nunca. Las promesas tienen tres estados principales:

1. **Pendiente** (*pending*): La operación no se ha completado.
2. **Cumplida** (*fulfilled*): La operación se completó con éxito.
3. **Rechazada** (*rejected*): La operación falló.

### Creación de una Promesa

```javascript
const promesa = new Promise((resolve, reject) => {
    let exito = true;

    if (exito) {
        resolve("Operación exitosa!");
    } else {
        reject("Operación fallida.");
    }
});

promesa
    .then((mensaje) => {
        console.log(mensaje);
    })
    .catch((error) => {
        console.error(error);
    });
```

### Encadenamiento de Promesas

El método `.then()` permite encadenar varias operaciones asíncronas de manera legible.

```javascript
new Promise((resolve) => {
    resolve("Primera promesa cumplida");
})
    .then((resultado) => {
        console.log(resultado);
        return "Segunda promesa cumplida";
    })
    .then((resultado) => {
        console.log(resultado);
    })
    .catch((error) => {
        console.error(error);
    });
```

### Promesas con `fetch`

Un uso común de las promesas es en solicitudes HTTP con `fetch`:

```javascript
fetch("https://api.example.com/datos")
    .then((respuesta) => respuesta.json())
    .then((datos) => {
        console.log(datos);
    })
    .catch((error) => {
        console.error("Hubo un error:", error);
    });
```

---

## Comparación entre Callbacks y Promesas

| Aspecto               | Callbacks                     | Promesas                     |
|-----------------------|-------------------------------|------------------------------|
| Lectura del código    | Puede ser difícil de seguir   | Más limpio y legible        |
| Manejo de errores     | Propenso a errores anidados   | Manejo centralizado con `.catch()` |
| Encadenamiento        | Difícil (Callback Hell)       | Sencillo y organizado        |

---

## Conclusión

Tanto los callbacks como las promesas son herramientas poderosas para manejar la asincronía en JavaScript. Mientras que los callbacks son más simples de implementar, las promesas ofrecen una sintaxis más elegante y robusta, especialmente para operaciones encadenadas o manejo de errores. Dominar ambas técnicas te ayudará a escribir código eficiente y mantenible.

