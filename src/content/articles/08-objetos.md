---
titulo: Objetos
descripcionPrevia: Crear, acceder, modificar, y trabajar con métodos dentro de los objetos
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# Objetos en JavaScript

Los objetos en JavaScript son una estructura fundamental para modelar datos complejos y representan colecciones de propiedades, donde cada propiedad es una clave asociada a un valor. Este artículo abarca cómo crear, acceder, modificar, y trabajar con métodos dentro de los objetos, además de explorar la desestructuración de objetos.

---

## Creación de Objetos

### Sintaxis Literal
La forma más común y sencilla de crear un objeto es usando la sintaxis literal:

```javascript
const persona = {
    nombre: "Juan",
    edad: 30,
    profesion: "Ingeniero"
};
```

### Con el Constructor `Object`
Otra forma de crear un objeto es usando el constructor integrado `Object`:

```javascript
const persona = new Object();
persona.nombre = "Ana";
persona.edad = 25;
persona.profesion = "Médico";
```

### Usando Clases o Funciones Constructoras
Si necesitas crear múltiples objetos con una estructura similar, puedes usar funciones constructoras o clases:

```javascript
function Persona(nombre, edad, profesion) {
    this.nombre = nombre;
    this.edad = edad;
    this.profesion = profesion;
}

const persona1 = new Persona("Carlos", 40, "Arquitecto");
const persona2 = new Persona("Lucia", 35, "Diseñadora");
```

Con clases:

```javascript
class Persona {
    constructor(nombre, edad, profesion) {
        this.nombre = nombre;
        this.edad = edad;
        this.profesion = profesion;
    }
}

const persona1 = new Persona("Carlos", 40, "Arquitecto");
const persona2 = new Persona("Lucia", 35, "Diseñadora");
```

---

## Acceso y Modificación de Propiedades

### Acceso a Propiedades
Puedes acceder a las propiedades de un objeto utilizando la notación de punto o la notación de corchetes:

```javascript
const persona = {
    nombre: "Sofia",
    edad: 28
};

console.log(persona.nombre); // Sofia
console.log(persona["edad"]); // 28
```

### Modificación de Propiedades
Modificar una propiedad es tan simple como reasignarle un nuevo valor:

```javascript
persona.edad = 29;
persona["nombre"] = "Laura";
console.log(persona); // { nombre: "Laura", edad: 29 }
```

### Agregar Nuevas Propiedades
Puedes agregar nuevas propiedades de manera dinámica:

```javascript
persona.profesion = "Artista";
console.log(persona); // { nombre: "Laura", edad: 29, profesion: "Artista" }
```

### Eliminar Propiedades
El operador `delete` se utiliza para eliminar propiedades:

```javascript
delete persona.edad;
console.log(persona); // { nombre: "Laura", profesion: "Artista" }
```

---

## Métodos dentro de Objetos

Los métodos son funciones asociadas a un objeto. Se definen como propiedades cuyo valor es una función:

```javascript
const calculadora = {
    sumar: function(a, b) {
        return a + b;
    },
    restar(a, b) {
        return a - b; // También se puede usar esta sintaxis más corta
    }
};

console.log(calculadora.sumar(5, 3)); // 8
console.log(calculadora.restar(5, 3)); // 2
```

Con la sintaxis ES6:

```javascript
const persona = {
    nombre: "Carlos",
    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre}`);
    }
};

persona.saludar(); // Hola, mi nombre es Carlos
```

---

## Desestructuración de Objetos

La desestructuración es una forma concisa de extraer valores de un objeto y asignarlos a variables:

```javascript
const persona = {
    nombre: "Maria",
    edad: 32,
    profesion: "Doctora"
};

const { nombre, edad } = persona;
console.log(nombre); // Maria
console.log(edad); // 32
```

### Renombrar Propiedades
Puedes renombrar propiedades al desestructurar:

```javascript
const { nombre: nombreCompleto, edad: años } = persona;
console.log(nombreCompleto); // Maria
console.log(años); // 32
```

### Valores Predeterminados
Es posible asignar valores predeterminados:

```javascript
const { nombre, pais = "No especificado" } = persona;
console.log(pais); // No especificado
```

### Desestructuración Anidada
Si el objeto contiene otros objetos, puedes desestructurar niveles anidados:

```javascript
const empleado = {
    nombre: "Luis",
    direccion: {
        ciudad: "Madrid",
        pais: "España"
    }
};

const { direccion: { ciudad, pais } } = empleado;
console.log(ciudad); // Madrid
console.log(pais); // España
```

---

Los objetos son esenciales en JavaScript y ofrecen una forma flexible de organizar y manejar datos complejos. Con el entendimiento de su creación, acceso, modificación y desestructuración, junto con la implementación de métodos, estarás bien equipado para trabajar con esta poderosa estructura en tus proyectos.

