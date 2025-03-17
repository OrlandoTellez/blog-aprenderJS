---
titulo: Principios SOLID
descripcionPrevia: Los principios SOLID son un conjunto de buenas prácticas para el diseño de software orientado a objetos.
tag: Fundamentos
layout: "../../layouts/PlantillaArticulos.astro"
---
# Principios SOLID en JavaScript: Ejemplos prácticos con código

Los principios SOLID son clave para escribir código JavaScript limpio y mantenible, incluso en proyectos complejos. Aquí te mostramos cómo aplicarlos con ejemplos reales en JS.

---

## 1. **Single Responsibility Principle (SRP)**  
**Cada función/clase debe tener una sola responsabilidad**.

### Ejemplo Antes (Violando SRP):
```javascript
class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }

  saveToDatabase() {
    // Lógica para guardar en BD
  }

  sendWelcomeEmail() {
    // Lógica para enviar email
  }
}
```
**Problema**: La clase maneja persistencia de datos **y** comunicación.

### Solución (Cumpliendo SRP):
```javascript
class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }
}

class UserRepository {
  static save(user) {
    // Guardar en BD
  }
}

class EmailService {
  static sendWelcome(user) {
    // Enviar email
  }
}
```

---

## 2. **Open/Closed Principle (OCP)**  
**Extiende funcionalidades sin modificar código existente**.

### Ejemplo Antes (Violando OCP):
```javascript
class Logger {
  log(message, type) {
    switch(type) {
      case 'console':
        console.log(message);
        break;
      case 'file':
        // Lógica para archivo
        break;
    }
  }
}
```
**Problema**: Para añadir un nuevo tipo (ej: SMS), hay que modificar la clase.

### Solución (Cumpliendo OCP):
```javascript
class Logger {
  constructor(strategy = new ConsoleStrategy()) {
    this.strategy = strategy;
  }

  log(message) {
    this.strategy.execute(message);
  }
}

class ConsoleStrategy {
  execute(message) {
    console.log(message);
  }
}

class FileStrategy {
  execute(message) {
    // Escribir en archivo
  }
}

// Uso:
const smsLogger = new Logger(new SMSStrategy()); // Nueva estrategia sin modificar Logger
```

---

## 3. **Liskov Substitution Principle (LSP)**  
**Las clases hijas deben poder usarse como las padres**.

### Ejemplo Válido:
```javascript
class Bird {
  fly() {
    return "Volando";
  }
}

class Eagle extends Bird {
  fly() {
    return "Águila volando alto";
  }
}

function makeBirdFly(bird) {
  return bird.fly();
}

makeBirdFly(new Bird()); // "Volando"
makeBirdFly(new Eagle()); // "Águila volando alto" ✅
```

### Ejemplo que Violaría LSP:
```javascript
class Penguin extends Bird {
  fly() {
    throw new Error("Los pingüinos no vuelan");
  }
}

makeBirdFly(new Penguin()); // Error ❌
```

---

## 4. **Interface Segregation Principle (ISP)**  
**Evita dependencias innecesarias**.

### Ejemplo Antes (Violando ISP):
```javascript
class Printer {
  print() {}
  scan() {}
  fax() {}
}

class BasicPrinter extends Printer {
  print() {
    // Implementación
  }
  
  scan() {
    throw new Error("No soportado"); // ❌
  }
}
```

### Solución (Cumpliendo ISP):
```javascript
class Printer {
  print() {}
}

class Scanner {
  scan() {}
}

class MultiFunctionPrinter {
  print() {}
  scan() {}
  fax() {}
}
```

---

## 5. **Dependency Inversion Principle (DIP)**  
**Depende de abstracciones, no de implementaciones**.

### Ejemplo Antes (Violando DIP):
```javascript
class AuthService {
  constructor() {
    this.database = new MySQLDatabase(); // Dependencia directa
  }
}
```

### Solución (Cumpliendo DIP):
```javascript
class AuthService {
  constructor(database) {
    this.database = database; // Inyección de dependencia
  }
}

// Implementaciones concretas
class MySQLDatabase {
  query() { /*...*/ }
}

class MongoDB {
  find() { /*...*/ }
}

// Uso:
const authWithMongo = new AuthService(new MongoDB());
```

---

## 🔑 **Beneficios Clave en JavaScript**
- **Testeo más fácil**: Funciones con una sola responsabilidad son más simples de mockear.
- **Menos efectos secundarios**: Cambiar una parte no rompe otras.
- **Mejor uso de NPM**: Paquetes pequeños y enfocados cumplen mejor con SRP/ISP.
- **Escalabilidad**: Patrones como estrategia o inyección de dependencia son naturales en JS.

---

## 🛠️ **Conclusión para Desarrolladores JS**
1. **SRP**: Divide funciones grandes en módulos/paquetes de NPM.
2. **OCP**: Usa composición (Object.assign, mixins) en lugar de herencia profunda.
3. **LSP**: Mantén contratos consistentes en métodos (mismos parámetros/salidas).
4. **ISP**: Crea módulos pequeños (ej: `loggers/` con `consoleLogger.js`, `fileLogger.js`).
5. **DIP**: Usa inyección de dependencias en frameworks como Express o NestJS.

**Ejemplo de arquitectura SOLID en Node.js**:
```javascript
// server.js
const UserService = require('./services/user');
const MongoUserRepository = require('./repositories/mongo/user');

const userService = new UserService(new MongoUserRepository());

// repositories/mongo/user.js
class MongoUserRepository {
  save(user) {
    // Implementación específica de MongoDB
  }
}