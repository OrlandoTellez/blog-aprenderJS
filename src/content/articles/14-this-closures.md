---
titulo: this en funciones y Closures en JavaScript
descripcionPrevia: son esenciales para escribir código limpio y efectivo.
tag: Principiante
layout: "../../layouts/PlantillaArticulos.astro"
---

# `this` en funciones y Closures en JavaScript

En JavaScript, `this` y los closures son conceptos fundamentales que a menudo confunden a los principiantes, pero son esenciales para escribir código limpio y efectivo. En este artículo, exploraremos qué son, cómo funcionan y cómo puedes utilizarlos.

## El contexto de `this` en funciones

`this` es una palabra clave que hace referencia al contexto en el que se ejecuta una función. Su valor depende de cómo se llame la función y no de dónde está definida.

### `this` en el contexto global
En el contexto global (fuera de cualquier función), `this` hace referencia al objeto global. En navegadores, esto es el objeto `window`:

```javascript
console.log(this); // En el navegador: window
```

### `this` en funciones normales
Cuando `this` es usado dentro de una función, su valor depende de cómo se invoque esa función:

#### 1. Llamada de función normal
En una llamada de función normal, `this` hace referencia al objeto global en modo no estricto, y es `undefined` en modo estricto:

```javascript
function mostrarThis() {
  console.log(this);
}

mostrarThis(); // En el navegador: window (modo no estricto)
'use strict';
mostrarThis(); // undefined (modo estricto)
```

#### 2. Método de un objeto
Cuando una función es llamada como un método de un objeto, `this` se refiere a ese objeto:

```javascript
const persona = {
  nombre: "Juan",
  saludar: function () {
    console.log(`Hola, soy ${this.nombre}`);
  }
};

persona.saludar(); // Hola, soy Juan
```

#### 3. Uso con `call()`, `apply()` y `bind()`
Puedes cambiar explícitamente el valor de `this` con estos métodos:

```javascript
function saludar() {
  console.log(this.nombre);
}

const persona = { nombre: "Ana" };

saludar.call(persona); // Ana
saludar.apply(persona); // Ana

const saludarBind = saludar.bind(persona);
saludarBind(); // Ana
```

### `this` en funciones flecha
Las funciones flecha no tienen su propio `this`. En cambio, heredan el valor de `this` del contexto en el que se definieron:

```javascript
const persona = {
  nombre: "Luis",
  saludar: function () {
    const flecha = () => {
      console.log(`Hola, soy ${this.nombre}`);
    };
    flecha();
  }
};

persona.saludar(); // Hola, soy Luis
```

---

## Closures en JavaScript

Un closure es una función que recuerda el entorno (o alcance) en el que fue creada, incluso después de que dicho entorno haya dejado de existir.

### Cómo funcionan los closures
Cuando una función es definida dentro de otra, la función interna tiene acceso a las variables de la función externa, incluso después de que la función externa haya terminado de ejecutarse:

```javascript
function crearContador() {
  let contador = 0;

  return function () {
    contador++;
    return contador;
  };
}

const contador1 = crearContador();
console.log(contador1()); // 1
console.log(contador1()); // 2

const contador2 = crearContador();
console.log(contador2()); // 1
```

### Ejemplos comunes de closures

#### 1. Uso para ocultar datos (Encapsulación)
Los closures permiten crear datos privados que no pueden ser accedidos directamente desde fuera:

```javascript
function crearPersona(nombre) {
  return {
    saludar: function () {
      console.log(`Hola, soy ${nombre}`);
    }
  };
}

const persona = crearPersona("María");
persona.saludar(); // Hola, soy María
```

#### 2. Funciones que recuerdan configuraciones
Los closures son útiles para funciones con configuraciones iniciales:

```javascript
function multiplicador(factor) {
  return function (numero) {
    return numero * factor;
  };
}

const duplicar = multiplicador(2);
console.log(duplicar(5)); // 10

const triplicar = multiplicador(3);
console.log(triplicar(5)); // 15
```

### Consideraciones sobre closures
- **Consumo de memoria**: Como los closures mantienen referencias al entorno externo, pueden consumir más memoria si no se gestionan adecuadamente.
- **Depuración**: Puede ser más difícil de depurar, ya que las variables no están directamente accesibles.

---

Con una comprensión clara de `this` y los closures, puedes escribir código más poderoso y flexible en JavaScript. Practicar con estos conceptos es clave para dominarlos.

