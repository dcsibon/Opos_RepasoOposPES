
# Chuleta HTML5 + CSS3 Básico (PES Informática)

---

## 1. Estructura básica HTML5

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi página</title>
</head>
<body>

  <header>
    <h1>Mi sitio web</h1>
    <nav>
      <ul>
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Contacto</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section>
      <h2>Sección principal</h2>
      <p>Contenido...</p>
    </section>

    <article>
      <h2>Artículo</h2>
      <p>Texto del artículo...</p>
    </article>
  </main>

  <footer>
    <p>© 2025 Mi página web</p>
  </footer>

</body>
</html>
```

---

## 2. Etiquetas semánticas HTML5

- `<header>` : cabecera de la página o sección
- `<nav>` : menú de navegación
- `<main>` : contenido principal
- `<section>` : sección de contenido
- `<article>` : contenido independiente (artículos, entradas)
- `<aside>` : contenido relacionado (barra lateral)
- `<footer>` : pie de página

---

## 3. Principales etiquetas de texto

```html
<h1> a <h6>    <!-- Títulos -->
<p>            <!-- Párrafo -->
<strong>       <!-- Negrita semántica -->
<em>           <!-- Cursiva semántica -->
<br>           <!-- Salto de línea -->
<hr>           <!-- Línea horizontal -->
<ul>, <ol>, <li> <!-- Listas -->
```

---

## 4. Imágenes y enlaces

```html
<img src="imagen.jpg" alt="Descripción">
<a href="https://google.com">Ir a Google</a>
```

---

## 5. Formulario básico

```html
<form action="#" method="post">
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <label for="mensaje">Mensaje:</label>
  <textarea id="mensaje" name="mensaje"></textarea>

  <button type="submit">Enviar</button>
</form>
```

---

## 6. CSS3: sintaxis básica

```css
selector {
  propiedad: valor;
}
```

---

## 7. Selectores básicos

```css
p {
  color: blue;
}

#id {
  font-weight: bold;
}

.clase {
  font-style: italic;
}

h1, h2 {
  text-align: center;
}
```

---

## 8. Modelo de caja (Box model)

```css
elemento {
  width: 200px;
  height: 100px;
  padding: 10px;
  border: 1px solid black;
  margin: 20px;
}
```

- `width` / `height`: tamaño del contenido
- `padding`: espacio interno
- `border`: borde
- `margin`: espacio externo

---

## 9. Posicionamiento

```css
position: static;    /* por defecto */
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

```css
top: 10px;
left: 20px;
```

---

## 10. Flexbox (distribución flexible)

```css
.container {
  display: flex;
  justify-content: center;  /* alineación horizontal */
  align-items: center;      /* alineación vertical */
}
```

```css
justify-content:
  flex-start | flex-end | center | space-between | space-around;
align-items:
  flex-start | flex-end | center | stretch;
```

---

## 11. Grid (maquetación en rejilla)

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-gap: 10px;
}
```

```css
grid-template-rows: 100px auto;
```

---

## 12. Unidades comunes

```css
px    /* píxeles */
em    /* relativo al tamaño de fuente padre */
rem   /* relativo al tamaño de fuente raíz */
%     /* porcentaje */
vh, vw /* % de alto/anchura de la ventana */
```

---

## 13. Media Queries (responsive)

```css
@media (max-width: 600px) {
  body {
    background-color: lightgray;
  }
}
```

---

## 14. Buenas prácticas

- Usar etiquetas semánticas (`header`, `nav`, `main`, `section`, etc.)
- Separar HTML (estructura), CSS (presentación), JS (comportamiento)
- Mantener estilos en archivos `.css` externos
- Usar clases para aplicar estilos, no IDs
- Responsive: usar media queries
- Aprovechar Flexbox y Grid para maquetación flexible

---
