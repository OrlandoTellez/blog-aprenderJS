---
titulo: ¿Cómo se integra JavaScript en HTML?
descripcionPrevia: Hay varias formas de hacerlo, y cada una tiene sus ventajas según el contexto.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

## ¿Cómo se integra JavaScript en HTML?

Integrar JavaScript en una página HTML es fundamental para aprovechar al máximo sus capacidades. Hay varias formas de hacerlo, y cada una tiene sus ventajas según el contexto.

### Métodos de integración

1. **Incrustado en línea (inline)** Puedes agregar JavaScript directamente en los atributos de eventos de los elementos HTML. Por ejemplo:

   ```html
   <button onclick="alert('Hola Mundo!')">Haz clic aquí</button>
   ```

   - Ventaja: Fácil de usar en ejemplos simples o para prototipos rápidos.
   - Desventaja: Difícil de mantener en proyectos grandes.

2. **Bloques de script dentro del HTML** Colocar el código JavaScript dentro de etiquetas `<script>` en el mismo archivo HTML:

   ```html
   <html>
   <head>
       <title>Ejemplo de JavaScript</title>
   </head>
   <body>
       <h1>Hola Mundo</h1>
       <script>
           alert('Bienvenido a mi sitio web');
       </script>
   </body>
   </html>
   ```

   - Ventaja: Conveniente para scripts que afectan únicamente a esa página.
   - Desventaja: Puede dificultar la organización si el código crece demasiado.

3. **Archivo externo** Guardar el código JavaScript en un archivo separado con extensión `.js` y enlazarlo al HTML usando la etiqueta `<script>`.

   Ejemplo:

   ```html
   <html>
   <head>
       <title>Ejemplo con archivo externo</title>
       <script src="scripts/main.js"></script>
   </head>
   <body>
       <h1>Bienvenido a mi sitio</h1>
   </body>
   </html>
   ```

   Contenido del archivo `main.js`:

   ```javascript
   alert('Este mensaje viene de un archivo externo.');
   ```

   - Ventaja: Mejora la organización y permite la reutilización del código.
   - Desventaja: Requiere una estructura de archivos más compleja.

### Buenas prácticas para la integración

1. **Colocar los scripts al final del cuerpo:** Para evitar bloqueos en la carga de la página, se recomienda colocar las etiquetas `<script>` antes del cierre de la etiqueta `</body>`.

   ```html
   <body>
       <!-- Contenido -->
       <script src="scripts/main.js"></script>
   </body>
   ```

2. **Usar el atributo **``**:** Permite que el navegador descargue el script en paralelo y lo ejecute después de que se haya cargado completamente el HTML.

   ```html
   <script src="scripts/main.js" defer></script>
   ```

3. **Evitar código inline:** A menos que sea estrictamente necesario, es preferible mantener el código JavaScript en archivos externos para facilitar el mantenimiento.

4. **Comentar el código:** Agregar comentarios explicativos para ayudar a otros desarrolladores (o a ti mismo en el futuro) a entender el propósito de cada fragmento de código.

   ```javascript
   // Este código muestra un mensaje de bienvenida
   alert('Hola, bienvenido a mi sitio');
   ```

En conclusión, integrar JavaScript en HTML es sencillo y esencial para cualquier proyecto web. Elegir el método adecuado depende de la escala del proyecto y las necesidades de mantenimiento.

