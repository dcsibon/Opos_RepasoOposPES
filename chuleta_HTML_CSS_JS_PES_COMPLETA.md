
# Chuleta HTML + CSS + JavaScript Básico + Nivel Intermedio (PES Informática)

---

## 1. Estructura básica HTML

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Título</title>
  <style>
    body { font-family: Arial; }
    .destacado { color: blue; font-weight: bold; }
  </style>
</head>
<body>

  <h1 class="destacado">Hola!</h1>
  <p id="parrafo">Texto</p>
  <button id="boton">Púlsame</button>

  <script>
    console.log("Página cargada");
  </script>

</body>
</html>
```

---

## 2. Selectores

```js
document.getElementById("id");
document.getElementsByClassName("clase");
document.querySelector("#id");
document.querySelector(".clase");
document.querySelector("elemento");
```

---

## 3. Modificar elementos (DOM)

```js
element.textContent = "Nuevo texto";
element.style.color = "red";
```

---

## 4. Variables

```js
let x = 5; // mutable
const PI = 3.1416; // constante
```

---

## 5. Entrada / Salida

```js
console.log("Texto en consola");
alert("Mensaje emergente");
const nombre = prompt("¿Tu nombre?");
```

---

## 6. Formularios + Validación

### HTML

```html
<form id="form">
  Nombre: <input type="text" id="nombre" required>
  Edad: <input type="number" id="edad" min="0" max="120">
  <button type="submit">Enviar</button>
</form>
<p id="resultado"></p>
```

### JS

```js
const form = document.getElementById("form");

form.addEventListener("submit", function(event) {
  event.preventDefault(); // Evita que se recargue la página

  const nombre = document.getElementById("nombre").value.trim();
  const edad = parseInt(document.getElementById("edad").value);

  if (nombre === "") {
    document.getElementById("resultado").textContent = "Nombre obligatorio";
    return;
  }

  if (isNaN(edad) || edad < 0) {
    document.getElementById("resultado").textContent = "Edad no válida";
    return;
  }

  document.getElementById("resultado").textContent =
    `Nombre: ${nombre}, Edad: ${edad}`;
});
```

---

## 7. Eventos básicos

```js
element.addEventListener("click", function() { ... });
form.addEventListener("submit", function() { ... });
input.addEventListener("input", function() { ... });
```

---

## 8. ¿Dónde se escribe el JS?

- En un bloque `<script> ... </script>` al final de la página
- O en un archivo `.js` externo: `<script src="archivo.js"></script>`

---

## 9. Organización del código

```js
// Instrucción suelta
console.log("Hola");

// Definición de función
function saludar() {
    console.log("Bienvenido");
}

// Llamar a función
saludar();
```

---

## 10. ¿Cómo se llama a las funciones en HTML?

- Si defines una función JS en `<script>`, se ejecuta cuando:

### a) La llamas desde un evento:

**Desde HTML (más antiguo):**

```html
<button onclick="saludar()">Púlsame</button>
```

**Desde JS (recomendado):**

```js
document.getElementById("boton").addEventListener("click", saludar);
```

### b) O la llamas directamente en JS.

---

## 11. ¿Qué hace `event.preventDefault();` ?

Evita el comportamiento por defecto del navegador cuando ocurre un evento.

Ejemplo en formulario:

```js
form.addEventListener("submit", function(event) {
    event.preventDefault(); // Evita que el formulario recargue la página
});
```

Si no se pone, el formulario haría "submit" y recargaría la página.

También sirve en eventos de click sobre enlaces, teclado, ratón, etc.

---

## 12. Arrays (colecciones)

```js
const numeros = [1, 2, 3, 4];
console.log(numeros[0]);
numeros.push(5);
numeros.pop();
numeros.length;
```

---

## 13. Bucles

### For clásico

```js
for (let i = 0; i < numeros.length; i++) {
    console.log(numeros[i]);
}
```

### For-of

```js
for (let num of numeros) {
    console.log(num);
}
```

### ForEach

```js
numeros.forEach(function(num) {
    console.log(num);
});
```

---

## 14. Funciones flecha

```js
const saludar = () => {
    console.log("Hola con flecha!");
};

const cuadrado = x => x * x;
console.log(cuadrado(4)); // 16
```

---

## 15. Map, Filter

```js
const dobles = numeros.map(n => n * 2);
const mayoresQueDos = numeros.filter(n => n > 2);
```

---

## 16. Temporizadores

```js
// Una vez tras x ms
setTimeout(() => {
    console.log("Han pasado 2 segundos");
}, 2000);

// Repetido cada x ms
const timer = setInterval(() => {
    console.log("Cada segundo");
}, 1000);

// clearInterval(timer); // Detener
```

---

## 17. Condicionales

```js
if (x > 10) { ... } else { ... }

switch (opcion) {
    case 1:
        ...
        break;
    default:
        ...
}
```

---

## 18. Operadores comunes

```js
==    // igualdad con conversión
===   // igualdad estricta
!=    // distinto
!==   // distinto estricto
&&    // AND
||    // OR
!     // NOT
```

---

## 19. Eventos avanzados

```js
input.addEventListener("change", function() { ... });
window.addEventListener("load", function() { ... });
document.addEventListener("DOMContentLoaded", function() { ... });
```

---

## 20. Tipos de datos

- String
- Number
- Boolean
- Array
- Object
- null
- undefined

---

## 21. Conversión de tipos

```js
parseInt("123") // -> 123
parseFloat("3.14") // -> 3.14
String(123) // -> "123"
```

---

## 22. Resumen de bucles

```js
for (let i = 0; i < n; i++) { ... }
while (condicion) { ... }
do { ... } while (condicion);
```

---

## 23. Buenas prácticas

- Usa `let` o `const`, no `var`
- Usa `event.preventDefault()` en formularios
- Usa `.textContent` para mostrar mensajes en la página
- Usa `querySelector()` para más flexibilidad
- Valida los datos antes de procesarlos
- Carga eventos con `addEventListener`
- Organiza el código en funciones nombradas si es reutilizable
- Usa funciones flecha en callbacks
- Para arrays: map, filter, forEach
- Usa `DOMContentLoaded` si el script va en <head>

---
