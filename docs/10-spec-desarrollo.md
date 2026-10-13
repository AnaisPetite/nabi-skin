# Spec de desarrollo — Nabi Skin

> Guía: [Spec de desarrollo](../evaluacion/guias/fase-2-specs/07-spec-de-desarrollo.md)

## 0. Insumos y prompt para el asistente

```text
Lee DESIGN.md, docs/05-arquitectura.md, docs/09-spec-diseno.md y docs/10-spec-desarrollo.md.
En la carpeta stitch/ está el código exportado de Stitch de cada pantalla (usado exclusivamente como referencia visual de maquetación).
Construye el sitio de Nabi Skin siguiendo exactamente docs/10-spec-desarrollo.md:
- Desarrolla únicamente con HTML5 semántico y Vanilla CSS (sin frameworks, sin Tailwind, sin librerías externas).
- Respeta la estructura de archivos y carpetas, y la navegación entre páginas definida.
- Implementa en css/styles.css todas las variables en :root con los valores y tokens de DESIGN.md.
- Sigue la convención de clases y la estructura semántica de cada una de las páginas.
- Asegura que el sitio sea totalmente responsive bajo el enfoque mobile-first con los breakpoints de la spec (375px, 768px y 1024px).
Al terminar, evalúa uno a uno los criterios de aceptación y confirma cuáles se cumplen (con Sí o No).
```

---

## 1. Estructura de archivos y carpetas

El proyecto se estructura con archivos en minúsculas, sin espacios ni caracteres especiales, centralizando estilos y recursos estáticos:

```text
nabi-skin/
├── index.html                   ← Landing principal
├── tienda.html                  ← Catálogo de productos y filtros
├── producto.html                ← Ficha individual de producto
├── carrito.html                 ← Resumen de compra y cálculo de despacho
├── blog.html                    ← Listado de artículos y categorías del blog
├── articulo.html                ← Lectura de artículo con producto recomendado
├── nosotros.html                ← Historia de la marca y filosofía consciente
├── contacto.html                ← Formulario de consultas y asesoría
├── preguntas-frecuentes.html    ← FAQ sobre envíos, pagos y K-Beauty
├── terminos.html                ← Términos y condiciones del servicio
├── privacidad.html              ← Política de privacidad y tratamiento de datos
├── 404.html                     ← Página de error 404 con retorno a tienda
├── DESIGN.md                    ← Design system oficial con tokens de diseño
├── css/
│   └── styles.css               ← Hoja de estilos global con variables :root y componentes
├── img/
│   ├── productos/               ← Fotografías de cosméticos y texturas
│   ├── blog/                    ← Imágenes editoriales de artículos
│   └── icons/                   ← Íconos SVG (carrito, lupa, WhatsApp, camión)
├── stitch/                      ← Archivos HTML/CSS exportados de Google Stitch (solo referencia)
└── docs/                        ← Documentación de requerimientos y especificaciones
```

---

## 2. Páginas y navegación

### Elementos transversales

* **Navbar (presente en las 12 páginas):**
  * Logo de Nabi Skin (enlace a `index.html`).
  * Enlaces principales: "Tienda" (`tienda.html`), "Blog" (`blog.html`), "Nosotros" (`nosotros.html`), "Contacto" (`contacto.html`).
  * Buscador rápido con campo de texto.
  * Acceso directo al carrito con contador dinámico/estático (`carrito.html`).
* **Footer (presente en las 12 páginas):**
  * Enlaces institucionales: "Nosotros" (`nosotros.html`), "Preguntas frecuentes" (`preguntas-frecuentes.html`), "Contacto" (`contacto.html`).
  * Enlaces legales: "Términos y condiciones" (`terminos.html`), "Política de privacidad" (`privacidad.html`).
  * Redes sociales y contacto: Enlace externo a WhatsApp (`https://wa.me/56912345678`) e Instagram.

### Matriz de navegación y user flows

La navegación implementa de forma continua los dos flujos definidos en [docs/05-arquitectura.md](05-arquitectura.md):

| Desde | Elemento interactivo | Lleva a | Propósito / Flujo |
|---|---|---|---|
| `index.html` | Botón "Ver productos" del Hero | `tienda.html` | Inicio Flujo 1 (Compra) |
| `index.html` | Botón "Test de rutina" del Hero | `tienda.html#test` | Asesoría rápida |
| `index.html` | Botón "Ver detalle" en cards destacadas | `producto.html` | Acceso directo a ficha |
| `index.html` | Formulario "Quiero la guía" | `index.html#gracias` | Lead magnet 10% OFF |
| `tienda.html` | Chips de categoría ("Limpiadores", etc.) | `tienda.html` (filtro visual) | Filtrado por paso |
| `tienda.html` | Checkbox "Piel sensible" | `tienda.html` (filtro visual) | Selección por necesidad |
| `tienda.html` | Botón "Ver detalle" en cada `card-product` | `producto.html` | Paso 2 Flujo 1 |
| `tienda.html` | Banner "Consultar por WhatsApp" | `https://wa.me/56912345678` | Asesoría directa |
| `producto.html` | Botón "Agregar al carrito" | `carrito.html` | Paso 3 Flujo 1 |
| `producto.html` | Botón "Consultar por WhatsApp" | `https://wa.me/56912345678` | Resolución de dudas |
| `producto.html` | Miga de pan "Tienda" | `tienda.html` | Retorno al catálogo |
| `carrito.html` | Botón "Calcular" comuna | `carrito.html` (cálculo visual) | Evitar costo sorpresivo |
| `carrito.html` | Enlace "← Continuar comprando" | `tienda.html` | Retorno a compras |
| `carrito.html` | Botón "Ir a pagar" | Pasarela simulada / checkout | Fin Flujo 1 |
| `blog.html` | Botón "Leer artículo" de Hero post | `articulo.html` | Inicio Flujo 2 (Contenido) |
| `blog.html` | Clic en cualquier `card-article` | `articulo.html` | Lectura educativa |
| `articulo.html` | Card de producto recomendado ("Ver producto") | `producto.html` | Conexión Flujo 2 con producto |
| `articulo.html` | Botón "Compartir en WhatsApp" | `https://api.whatsapp.com/send...` | Recomendar a una amiga |
| `articulo.html` | Enlace a Contacto para asesoría | `contacto.html` | Alternativa sin compra inmediata |
| `contacto.html` | Botón "Enviar consulta" | `contacto.html#enviado` | Fin alternativo Flujo 2 |
| `404.html` | Botón "Volver a la tienda" | `tienda.html` | Recuperación de error |

---

## 3. Estructura semántica de cada página

Cada archivo HTML utiliza elementos semánticos de HTML5 para optimizar accesibilidad, estructura y SEO:

### 1. `index.html` (Landing)
```html
<header> → <nav class="navbar"> (logo, enlaces, buscador, carrito)
<main>
  <section class="hero"> → h1, bajada, botones de acción, imagen
  <section class="value-prop"> → h2, 3 artículos de propuesta de valor
  <section class="featured-products"> → h2, grilla con 3 <article class="card-product">
  <section class="lead-magnet"> → h2, formulario con input de email y botón
  <section class="testimonials"> → h2, 3 testimonios de clientas
</main>
<footer class="footer"> → enlaces secundarios, redes y copyright
```

### 2. `tienda.html` (Catálogo)
```html
<header> → <nav class="navbar">
<main>
  <header class="catalog-header"> → h1, bajada, buscador expandido
  <nav class="category-chips"> → lista de botones <button class="chip-filter">
  <div class="catalog-layout">
    <aside class="catalog-filters"> → filtros de tipo de piel, síntoma y precio
    <section class="catalog-grid"> → h2 accesible, grilla con 6 <article class="card-product">
  </div>
  <aside class="whatsapp-banner"> → banner de ayuda personalizada
</main>
<footer class="footer">
```

### 3. `producto.html` (Ficha de producto)
```html
<header> → <nav class="navbar">
<main>
  <nav class="breadcrumbs" aria-label="Miga de pan">
  <article class="product-detail">
    <div class="product-gallery"> → imagen principal + miniaturas
    <div class="product-info"> → tags, h1, valoración, precio, selector, botón agregar al carrito, botón WhatsApp
  </article>
  <section class="guide-usage"> → h2, 3 columnas (para qué sirve, cómo usarlo, paso en rutina)
  <section class="product-tabs"> → pestañas de ingredientes, FAQ y reseñas
  <section class="related-products"> → h2, grilla con 3 <article class="card-product">
</main>
<footer class="footer">
```

### 4. `carrito.html` (Carrito)
```html
<header> → <nav class="navbar">
<main>
  <header class="cart-header"> → h1, indicador de pasos
  <div class="cart-layout">
    <section class="cart-items"> → tabla semántica de productos (table, thead, tbody, tr, td)
    <aside class="cart-summary"> → h2, desglose, calculadora de comuna, cupón, total y botón pagar
  </div>
</main>
<footer class="footer">
```

### 5. `blog.html` (Listado del blog)
```html
<header> → <nav class="navbar">
<main>
  <header class="blog-header"> → h1, bajada explicativa
  <nav class="blog-categories"> → chips de categoría del blog
  <article class="featured-post"> → post destacado en formato horizontal
  <section class="blog-grid"> → h2 accesible, grilla de 6 <article class="card-article">
  <section class="lead-magnet"> → módulo de captación de newsletter
</main>
<footer class="footer">
```

### 6. `articulo.html` (Detalle de artículo)
```html
<header> → <nav class="navbar">
<main>
  <nav class="breadcrumbs" aria-label="Miga de pan">
  <article class="post-content">
    <header class="post-header"> → tag de categoría, h1, fecha, tiempo de lectura, imagen principal
    <div class="post-body"> → párrafos de contenido, subtítulos h2
      <aside class="recommended-product"> → tarjeta integrada con producto recomendado y botón de compra
      <div class="post-share"> → botones para compartir en WhatsApp e Instagram
    </div>
    <section class="comments-section"> → h3, listado de comentarios y formulario de consulta
  </article>
  <section class="related-posts"> → h2, 2 <article class="card-article">
</main>
<footer class="footer">
```

### 7. Páginas secundarias (`nosotros.html`, `contacto.html`, `preguntas-frecuentes.html`, `terminos.html`, `privacidad.html`, `404.html`)
* Todas estructuradas con `<header>`, `<main>` con un único `<h1>` por página y secciones de contenido `<section>`, y `<footer>`.
* `contacto.html` incluye formulario accesible con etiquetas `<label>` vinculadas a sus `<input>` y `<textarea>`.
* `404.html` incluye mensaje empático de error y enlace visible de retorno al catálogo en `tienda.html`.

---

## 4. Organización del CSS

### Variables globales en `:root` (extraídas directamente de `DESIGN.md`)

```css
:root {
  /* Colores principales y de marca */
  --color-primary: #2D5A43;
  --color-primary-hover: #1E3F30;
  --color-primary-active: #152E23;
  --color-on-primary: #FFFFFF;

  /* Colores secundarios y acentos */
  --color-secondary: #F4EAE2;
  --color-on-secondary: #222421;
  --color-tertiary: #B8533B;
  --color-on-tertiary: #FFFFFF;

  /* Superficies y fondos */
  --color-neutral: #FAF8F5;
  --color-surface: #FFFFFF;
  --color-border: #E2DFD6;

  /* Tipografía y textos */
  --color-on-surface: #222421;
  --color-on-surface-variant: #5E605B;

  /* Estados y retroalimentación */
  --color-disabled: #E5E3DD;
  --color-on-disabled: #7E7D76;
  --color-error: #BA2D2D;
  --color-success: #25663F;

  /* Fuentes (Google Fonts) */
  --font-title: 'Playfair Display', Georgia, serif;
  --font-body: 'Plus Jakarta Sans', system-ui, -apple-system, sans-serif;

  /* Escala tipográfica */
  --text-display: 3rem;       /* 48px */
  --text-headline-lg: 2rem;   /* 32px */
  --text-headline-md: 1.5rem; /* 24px */
  --text-title-md: 1.125rem;  /* 18px */
  --text-body-lg: 1.125rem;   /* 18px */
  --text-body-md: 1rem;       /* 16px */
  --text-body-sm: 0.875rem;   /* 14px */
  --text-label-sm: 0.8125rem; /* 13px */

  /* Radios de curvatura */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 14px;
  --radius-full: 9999px;

  /* Escala de espaciados */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;

  /* Sombras y elevaciones */
  --shadow-sm: 0 2px 8px rgba(34, 36, 33, 0.04);
  --shadow-md: 0 8px 24px rgba(45, 90, 67, 0.08);
  --shadow-lg: 0 16px 40px rgba(34, 36, 33, 0.14);

  /* Layout */
  --container-max-width: 1200px;
}
```

### Convención de clases CSS

Se utiliza una nomenclatura semántica con guiones (kebab-case) coherente con los nombres de tokens de `DESIGN.md`:
* **Componentes base:** `.navbar`, `.footer`, `.hero`, `.cart-layout`.
* **Botones:** `.button-primary`, `.button-secondary`, `.button-primary[disabled]`.
* **Tarjetas:** `.card-product`, `.card-article`, `.card-value`.
* **Etiquetas y filtros:** `.tag-routine`, `.tag-offer`, `.chip-filter`, `.chip-filter.active`.
* **Formularios:** `.input-field`, `.form-group`, `.message-error`, `.message-success`.
* **Bloques didácticos:** `.guide-usage`, `.cart-summary`.

### Breakpoints responsivos (Mobile-First)

El desarrollo adopta el enfoque **mobile-first**, aplicando estilos para móviles por defecto y enriqueciendo el diseño mediante `@media (min-width: ...)`:

1. **Mobile base (hasta 767px):**
   * Viewport de 375px a 767px con padding lateral de 16px (`--space-md`).
   * Grillas a 1 columna (o 2 columnas compactas de 160px para catálogo).
   * Navbar con menú hamburguesa colapsable.
   * Filtros de tienda en botón modal deslizante inferior.
2. **Tablet (`@media (min-width: 768px)`):**
   * Padding lateral de 32px (`--space-xl`).
   * Grillas de catálogo y blog a 2 columnas.
   * Menú de navegación visible en cabecera.
3. **Desktop (`@media (min-width: 1024px)`):**
   * Contenedor centrado con ancho máximo de 1200px y padding lateral de 48px (`--space-2xl`).
   * Grilla de catálogo a 3 o 4 columnas con barra lateral fija de filtros.
   * Grilla de blog a 3 columnas.

---

## 5. Criterios de aceptación verificables

Todos los criterios están formulados como afirmaciones estrictamente evaluables con **Sí** o **No**:

### Navegación y flujos de usuario
- [ ] ¿La navbar y el footer están presentes y son consistentes en todas las páginas del sitio?
- [ ] ¿Es posible completar el Flujo 1 (Landing → Tienda → Ficha de producto → Carrito) sin enlaces rotos?
- [ ] ¿Es posible completar el Flujo 2 (Blog → Artículo → Ficha de producto recomendado)?
- [ ] ¿El enlace de consulta rápida por WhatsApp redirige a una URL válida de `wa.me`?
- [ ] ¿Existe una página `404.html` que ofrece un enlace funcional para retornar a la tienda?

### Funcionalidades
- [ ] ¿La landing incluye el formulario de captación para la guía gratuita de K-Beauty con la promesa del 10% de descuento?
- [ ] ¿La tienda dispone de buscador visible, chips de categoría y opciones de filtro por tipo de piel (sensible, grasa, mixta, seca)?
- [ ] ¿La ficha de producto contiene la guía de uso (`guide-usage`) estructurada con "Para qué sirve", "Cómo usarlo" y "Paso de la rutina"?
- [ ] ¿El carrito de compras permite simular el cálculo de costo de despacho al ingresar la comuna?
- [ ] ¿El artículo del blog incluye botones específicos para compartir en WhatsApp e Instagram?
- [ ] ¿El artículo del blog dispone de una sección de comentarios y dudas?

### Diseño y Design System
- [ ] ¿Todos los colores utilizados en `css/styles.css` provienen de las variables de `:root` declaradas en `DESIGN.md`?
- [ ] ¿El sitio utiliza exclusivamente HTML y CSS propios, sin incluir frameworks como Tailwind ni código sin depurar exportado de Stitch?
- [ ] ¿Las tarjetas de producto muestran siempre el precio visible sin requerir acción del cursor?
- [ ] ¿Los botones primarios, secundarios y chips cuentan con estados interactivos visibles en hover y active?
- [ ] ¿Las etiquetas de tipo de piel (`tag-routine`) y de oferta (`tag-offer`) utilizan los colores y radios definidos en `DESIGN.md`?

### Responsive y adaptación móvil
- [ ] ¿En un ancho de pantalla de 375px la página no genera ningún tipo de scroll horizontal?
- [ ] ¿El menú de navegación se colapsa adecuadamente en pantallas menores a 768px?
- [ ] ¿El catálogo de productos adapta su grilla a 1 columna en mobile, 2 en tablet y al menos 3 en desktop?
- [ ] ¿Los elementos interactivos principales (botones y campos de texto) cuentan con una altura mínima de 44px en móviles para ser touch-friendly?

### Accesibilidad, semántica y publicación
- [ ] ¿Cada página HTML cuenta con un único elemento `<h1>` principal?
- [ ] ¿Todas las imágenes del sitio cuentan con el atributo `alt` descriptivo?
- [ ] ¿Todas las combinaciones de texto y fondo cumplen con el ratio mínimo de contraste WCAG AA (4.5:1)?
- [ ] ¿Los campos de formulario cuentan con sus respectivas etiquetas `<label>` asociadas?
- [ ] ¿El repositorio está publicado y accesible en GitHub Pages en la URL del proyecto?
