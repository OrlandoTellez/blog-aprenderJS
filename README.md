# Documentación del Proyecto: Blog para Aprender JavaScript

Este repositorio contiene un blog educativo diseñado para enseñar JavaScript desde cero. El proyecto está construido con **Astro**, un framework moderno para construir sitios web rápidos y optimizados. A continuación, se detalla la estructura del proyecto, los archivos clave y cómo funciona cada parte.

---

## Estructura del Proyecto

El proyecto sigue la siguiente estructura de directorios:

```
orlandotellez-blog-aprenderjs/
├── README.md
├── astro.config.mjs
├── package.json
├── tsconfig.json
├── public/
│   └── imagenes/
│       └── perfil/
└── src/
    ├── env.d.ts
    ├── assets/
    │   └── iconos/
    ├── components/
    │   ├── Boton.astro
    │   ├── BotonTarjetaArticulos.astro
    │   ├── Header.astro
    │   ├── TarjetaArticulosRecientes.astro
    │   ├── TarjetaRecursos.astro
    │   └── TarjetaTutoriales.astro
    ├── content/
    │   └── articles/
    │       ├── 01-que-es-javascript.md
    │       ├── 02-como-se-integra-en-html.md
    │       ├── 03-sintaxis-basica.md
    │       ├── 04-sentencias-de-control.md
    │       ├── 05-funciones-javascript.md
    │       ├── 06-arrays.md
    │       ├── 07-strings.md
    │       ├── 08-objetos.md
    │       ├── 09-funciones-anonimas-y-arrow-functions.md
    │       ├── 10-parametros-por-defecto.md
    │       ├── 11-trabajo-con-el-DOM.md
    │       ├── 12-funciones-de-orden-superior.md
    │       ├── 13-callbacks-promesas.md
    │       ├── 14-this-closures.md
    │       └── 24-async-await.md
    ├── layouts/
    │   ├── Layout.astro
    │   └── PlantillaArticulos.astro
    ├── pages/
    │   ├── index.astro
    │   ├── recursos.astro
    │   ├── sobreMi.astro
    │   └── tutoriales/
    │       ├── [...slug].astro
    │       └── index.astro
    └── secciones/
        ├── ArticulosRecientes.astro
        ├── Footer.astro
        ├── Hero.astro
        └── VerTutorialesSeccion.astro
```

## Cómo Ejecutar el Proyecto

1. **Clonar el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/orlandotellez-blog-aprenderjs.git
   cd orlandotellez-blog-aprenderjs
   ```

2. **Instalar dependencias**:
   ```bash
   npm install
   ```

3. **Ejecutar el servidor de desarrollo**:
   ```bash
   npm run dev
   ```
   El sitio estará disponible en `http://localhost:4321`.

4. **Construir el proyecto para producción**:
   ```bash
   npm run build
   ```

5. **Previsualizar la versión de producción**:
   ```bash
   npm run preview
   ```

---

## Comandos Disponibles

| Comando                   | Acción                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Instala las dependencias del proyecto.           |
| `npm run dev`             | Inicia el servidor de desarrollo.                |
| `npm run build`           | Construye el sitio para producción.              |
| `npm run preview`         | Previsualiza la versión de producción.           |
| `npm run astro ...`       | Ejecuta comandos de la CLI de Astro.             |
| `npm run astro -- --help` | Muestra la ayuda de la CLI de Astro.             |

---
