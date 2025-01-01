---
titulo: Trabajo con el DOM (Document Object Model)
descripcionPrevia: Este modelo permite a JavaScript acceder, modificar y manipular el contenido, la estructura y los estilos de una página web de manera dinámica.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---


### Trabajo con el DOM (Document Object Model) en JavaScript

El **DOM (Document Object Model)** es la representación estructurada de un documento HTML o XML como un árbol de nodos. Este modelo permite a JavaScript acceder, modificar y manipular el contenido, la estructura y los estilos de una página web de manera dinámica.

En este artículo, exploraremos cómo trabajar con el DOM, desde acceder a elementos hasta manipular su contenido, estilos y eventos.

---

## Acceso a Elementos del DOM

Para interactuar con los elementos del DOM, JavaScript proporciona varios métodos de selección:

### 1. `getElementById`
Obtiene un elemento basado en su atributo `id`.

```html
<div id="miDiv">Hola, mundo!</div>
```

```javascript
const elemento = document.getElementById("miDiv");
console.log(elemento.textContent); // Hola, mundo!
```

---

### 2. `querySelector` y `querySelectorAll`
- `querySelector`: Selecciona el **primer elemento** que coincide con un selector CSS.
- `querySelectorAll`: Selecciona **todos los elementos** que coinciden con un selector CSS.

```html
<p class="parrafo">Primer párrafo</p>
<p class="parrafo">Segundo párrafo</p>
```

```javascript
const primerParrafo = document.querySelector(".parrafo");
console.log(primerParrafo.textContent); // Primer párrafo

const todosLosParrafos = document.querySelectorAll(".parrafo");
todosLosParrafos.forEach((p) => console.log(p.textContent));
// Primer párrafo
// Segundo párrafo
```

---

## Manipulación de Contenido y Estilos

Una vez que seleccionamos un elemento, podemos modificar su contenido y estilos utilizando propiedades y métodos.

### Modificar el Contenido
#### 1. `textContent` y `innerHTML`
- **`textContent`**: Cambia el texto del elemento.
- **`innerHTML`**: Cambia el contenido HTML del elemento.

```html
<div id="miDiv">Texto original</div>
```

```javascript
const miDiv = document.getElementById("miDiv");

// Cambiar texto
miDiv.textContent = "Nuevo texto";

// Cambiar contenido HTML
miDiv.innerHTML = "<strong>Texto con formato</strong>";
```

---

### Modificar Atributos
Usa `setAttribute` y `getAttribute` para manejar atributos.

```html
<img id="miImagen" src="imagen1.jpg" alt="Imagen inicial">
```

```javascript
const imagen = document.getElementById("miImagen");

// Cambiar el atributo 'src'
imagen.setAttribute("src", "imagen2.jpg");

// Obtener el atributo 'alt'
console.log(imagen.getAttribute("alt")); // Imagen inicial
```

---

### Modificar Estilos
Puedes usar la propiedad `style` para cambiar estilos directamente o modificar clases con `classList`.

#### Cambiar Estilos Directamente:
```javascript
const elemento = document.querySelector("#miDiv");
elemento.style.color = "blue";
elemento.style.fontSize = "20px";
```

#### Añadir y Quitar Clases:
```html
<div id="miDiv" class="rojo">Texto</div>
```

```javascript
const elemento = document.querySelector("#miDiv");
elemento.classList.add("azul"); // Añadir clase
elemento.classList.remove("rojo"); // Quitar clase
elemento.classList.toggle("oculto"); // Alternar clase
```

---

## Manejo de Eventos

Los eventos permiten responder a interacciones del usuario, como clics, envío de formularios o pulsaciones de teclas.

### 1. Escuchar Eventos con `addEventListener`

#### Ejemplo: Evento `click`
```html
<button id="miBoton">Haz clic aquí</button>
```

```javascript
const boton = document.getElementById("miBoton");
boton.addEventListener("click", () => {
    alert("¡Botón clickeado!");
});
```

---

### 2. Evento `submit`
Captura el envío de formularios para validaciones.

```html
<form id="miFormulario">
    <input type="text" id="nombre" placeholder="Nombre">
    <button type="submit">Enviar</button>
</form>
```

```javascript
const formulario = document.getElementById("miFormulario");

formulario.addEventListener("submit", (evento) => {
    evento.preventDefault(); // Previene el envío por defecto
    const nombre = document.getElementById("nombre").value;
    alert(`Nombre ingresado: ${nombre}`);
});
```

---

### 3. Otros Eventos Comunes
- **`mouseover` y `mouseout`**: Para detectar cuando el cursor pasa sobre un elemento.
- **`keydown` y `keyup`**: Para capturar eventos de teclado.
- **`change`**: Para detectar cambios en campos de formulario.

```javascript
const input = document.querySelector("#nombre");

// Detectar pulsación de teclas
input.addEventListener("keydown", (evento) => {
    console.log(`Tecla presionada: ${evento.key}`);
});
```

---

## Ejemplo Completo: Manipulación Dinámica del DOM

Creamos un ejemplo donde un usuario escribe un texto y cambia dinámicamente el contenido de un párrafo.

```html
<div>
    <input type="text" id="texto" placeholder="Escribe algo">
    <button id="boton">Cambiar texto</button>
    <p id="parrafo">Texto inicial</p>
</div>
```

```javascript
const inputTexto = document.getElementById("texto");
const boton = document.getElementById("boton");
const parrafo = document.getElementById("parrafo");

boton.addEventListener("click", () => {
    const nuevoTexto = inputTexto.value;
    parrafo.textContent = nuevoTexto || "Texto inicial"; // Si no hay texto, mostrar el texto inicial
});
```

---

## Conclusión

El trabajo con el DOM es una de las habilidades esenciales en JavaScript para crear páginas web interactivas. Aprender a acceder, manipular y responder a eventos en elementos del DOM te permitirá construir aplicaciones dinámicas y atractivas. Combina estas técnicas con otras herramientas de JavaScript, como funciones y promesas, para maximizar el potencial de tus proyectos.