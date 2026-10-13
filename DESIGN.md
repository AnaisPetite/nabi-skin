---
version: alpha
name: "Nabi Skin"
description: "Design system de cosmética y skincare coreano consciente y luminoso"
colors:
  primary: "#2D5A43"
  primary-hover: "#1E3F30"
  primary-active: "#152E23"
  on-primary: "#FFFFFF"
  secondary: "#F4EAE2"
  on-secondary: "#222421"
  tertiary: "#B8533B"
  on-tertiary: "#FFFFFF"
  neutral: "#FAF8F5"
  surface: "#FFFFFF"
  on-surface: "#222421"
  on-surface-variant: "#5E605B"
  disabled: "#E5E3DD"
  on-disabled: "#7E7D76"
  error: "#BA2D2D"
  success: "#25663F"
typography:
  headline-display:
    fontFamily: "Playfair Display"
    fontSize: 48px
    fontWeight: 600
    lineHeight: 1.1
  headline-lg:
    fontFamily: "Playfair Display"
    fontSize: 32px
    fontWeight: 600
    lineHeight: 1.2
  headline-md:
    fontFamily: "Playfair Display"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 1.25
  title-md:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 18px
    fontWeight: 600
    lineHeight: 1.3
  body-lg:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
  label-md:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 1
  label-sm:
    fontFamily: "Plus Jakarta Sans"
    fontSize: 13px
    fontWeight: 600
    lineHeight: 1
rounded:
  sm: 4px
  md: 8px
  lg: 14px
  full: 9999px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  2xl: 48px
  3xl: 64px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.full}"
    padding: 12px 24px
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
  button-primary-active:
    backgroundColor: "{colors.primary-active}"
    textColor: "{colors.on-primary}"
  button-primary-disabled:
    backgroundColor: "{colors.disabled}"
    textColor: "{colors.on-disabled}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.full}"
    padding: 12px 24px
  button-secondary-hover:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.primary-hover}"
  card-product:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.title-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.md}"
  card-product-hover:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
  tag-routine:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-secondary}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.full}"
    padding: 4px 10px
  tag-offer:
    backgroundColor: "{colors.tertiary}"
    textColor: "{colors.on-tertiary}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.full}"
    padding: 4px 10px
  chip-filter:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.full}"
    padding: 8px 16px
  chip-filter-active:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.full}"
    padding: 8px 16px
  input-field:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.full}"
    padding: 12px 18px
  input-field-focus:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
  card-article:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.title-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.md}"
  guide-usage:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.md}"
    padding: "{spacing.md}"
  cart-summary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.lg}"
  message-error:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.error}"
    typography: "{typography.body-sm}"
  message-success:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.success}"
    typography: "{typography.body-sm}"
  page:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
  text-secondary:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.on-surface-variant}"
    typography: "{typography.body-sm}"
---

# Nabi Skin — Design system

## Overview

Nabi Skin es una tienda online de cosmética y skincare coreano (K-Beauty) enfocada en el autocuidado consciente y el respeto por la barrera cutánea. Su usuaria principal es Sofía (24 años), estudiante universitaria con piel sensible y reactiva que busca luminosidad natural (*glass skin*) sin irritaciones, y a quien le frustran los catálogos confusos, las rutinas de pasos interminables y los precios opacos.

La interfaz debe sentirse como un ritual de bienestar fresco, limpio, reconfortante y accesible. Basada en las palabras clave del moodboard (**Luminosidad · Glass Skin · Natural · Fluidez · Calma**), la experiencia visual equilibra la elegancia editorial coreana con la practicidad de compra móvil.

## Colors

- **Primary (`#2D5A43`):** Verde salvia botánico profundo. Utilizado en botones primarios (`button-primary`), enlaces activos, botones de filtro seleccionados (`chip-filter-active`) y detalles de marca. No se utiliza como fondo de página completa ni en bloques de texto continuo.
- **Primary-hover (`#1E3F30`):** Verde bosque oscuro. Aplicado en la interacción hover y focus de botones y enlaces primarios.
- **Primary-active (`#152E23`):** Verde profundo prensado. Aplicado al hacer clic (active) en botones primarios.
- **On-primary (`#FFFFFF`):** Blanco puro. Color de texto e íconos sobre fondos primarios (ratio 8.0:1, cumple WCAG AAA).
- **Secondary (`#F4EAE2`):** Durazno piel suave. Utilizado como fondo de badges de tipo de piel (`tag-routine`), fondos de bloques secundarios y estado hover de botones secundarios. Nunca se utiliza como color de texto.
- **On-secondary (`#222421`):** Carbón botánico suave. Color de texto legible sobre superficies secundarias (ratio 12.3:1, cumple WCAG AAA).
- **Tertiary (`#B8533B`):** Terracota luminoso cálido. Reservado exclusivamente para badges de ahorro o descuentos (`tag-offer`) y alertas de stock limitado. No se usa en navegación general.
- **On-tertiary (`#FFFFFF`):** Blanco puro. Color de texto sobre badges terciarios (ratio 4.88:1, cumple WCAG AA).
- **Neutral (`#FAF8F5`):** Crema seda luminoso. Fondo base global de todo el sitio. Evita la frialdad del blanco puro y aporta calidez de luz natural.
- **Surface (`#FFFFFF`):** Blanco puro. Fondo de tarjetas (`card-product`, `card-article`), campos de formulario (`input-field`), modales y cajón del carrito.
- **On-surface (`#222421`):** Carbón suave. Color principal de texto para títulos, párrafos y precios (ratio 14.1:1 sobre `neutral` y 14.9:1 sobre `surface`, cumple WCAG AAA).
- **On-surface-variant (`#5E605B`):** Gris cálido neutro. Empleado en bajadas, metadatos, tiempo de lectura y placeholders (ratio 5.1:1 sobre `neutral` y 5.4:1 sobre `surface`, cumple WCAG AA).
- **Disabled (`#E5E3DD`):** Gris arena claro. Fondo de botones o campos inhabilitados.
- **On-disabled (`#7E7D76`):** Gris neutro atenuado. Texto de elementos deshabilitados.
- **Error (`#BA2D2D`):** Rojo pétalo. Mensajes de error en formularios y avisos de validación.
- **Success (`#25663F`):** Verde hoja. Confirmaciones de suscripción, cupón aplicado y compras exitosas.

## Typography

- **Títulos:** Playfair Display (Google Fonts). Tipografía serif con elegancia editorial, delicadeza en curvas y alta presencia estética, evocando revistas de belleza y bienestar consciente.
- **Textos:** Plus Jakarta Sans (Google Fonts). Tipografía sans-serif contemporánea, limpia y geométrica, seleccionada para garantizar lectura ágil y cómoda en pantallas móviles.

### Escala tipográfica

- `headline-display` (48px / line-height 1.1 / weight 600): Titulares principales del Hero en versión desktop.
- `headline-lg` (32px / line-height 1.2 / weight 600): Encabezados de sección (h2 en desktop, h1 en mobile).
- `headline-md` (24px / line-height 1.25 / weight 600): Subtítulos de sección y nombres de producto en ficha individual.
- `title-md` (18px / line-height 1.3 / weight 600): Nombres de producto en tarjetas (`card-product`) y títulos de blog.
- `body-lg` (18px / line-height 1.6 / weight 400): Bajadas explicativas del Hero y párrafos introductorios.
- `body-md` (16px / line-height 1.6 / weight 400): Texto de párrafos estándar, artículos de blog y descripciones.
- `body-sm` (14px / line-height 1.5 / weight 400): Explicaciones breves en guías de uso, textos legales y notas al pie.
- `label-md` (16px / line-height 1.0 / weight 600): Etiquetas de botones y navegación.
- `label-sm` (13px / line-height 1.0 / weight 600): Chips de filtro, badges de tipo de piel y metadatos de lectura.

## Layout

- **Ancho máximo de contenedor:** 1200px centrado horizontalmente con `margin: 0 auto`.
- **Escala de espaciados:**
  - `xs` (4px): Separación entre ícono y texto.
  - `sm` (8px): Espacio entre tags, chips contiguos y elementos compactos.
  - `md` (16px): Padding interno de tarjetas y espacio entre columnas móviles.
  - `lg` (24px): Padding de tarjetas destacadas y separación estándar entre filas.
  - `xl` (32px): Separación entre bloques de contenido y márgenes de tablet.
  - `2xl` (48px): Espacio vertical entre secciones secundarias y padding desktop.
  - `3xl` (64px): Espacio vertical entre secciones mayores en desktop.

### Breakpoints y adaptación responsiva

- **Mobile (hasta 767px):**
  - Márgenes laterales: 16px.
  - Catálogo de productos: 1 columna (o 2 columnas compactas de 160px de ancho mínimo).
  - Blog: 1 columna de tarjetas verticales.
  - Navegación: Barra superior con logo, buscador colapsado, ícono de carrito y menú hamburguesa que despliega drawer lateral.
  - Filtros: Botón desplegable "Filtrar por tipo de piel" que abre panel modal inferior.
- **Tablet (768px a 1023px):**
  - Márgenes laterales: 32px.
  - Catálogo de productos: Grilla de 2 columnas.
  - Blog: Grilla de 2 columnas.
  - Navegación: Menú horizontal compacto con buscador visible.
- **Desktop (desde 1024px):**
  - Márgenes laterales: 48px con tope máximo de 1200px.
  - Catálogo de productos: Grilla de 3 o 4 columnas con barra lateral izquierda fija para filtros por necesidad cutánea.
  - Blog: Grilla de 3 columnas para artículos.
  - Navegación: Navbar completa con todos los enlaces, buscador expandido y acceso directo al carrito.

## Elevation & Depth

La jerarquía visual se construye mediante planos claros y contraste sutil, evitando sombras oscuras para preservar la frescura luminosa de la marca:

- **Capa 0 (Base plana):** Fondo `neutral` (`#FAF8F5`) sin sombra.
- **Capa 1 (Superficies de contenido):** Tarjetas `surface` (`#FFFFFF`) con borde de 1px sólido en `#E2DFD6` y sombra sutil `0 2px 8px rgba(34, 36, 33, 0.04)`.
- **Capa 2 (Interacción hover):** En hover, las tarjetas elevan su sombra a `0 8px 24px rgba(45, 90, 67, 0.08)` con una traslación vertical de -2px.
- **Capa 3 (Superficies flotantes y modales):** Modales de guía gratuita, carrito deslizante y drawer móvil con fondo `#FFFFFF`, borde perimetral sutil y sombra `0 16px 40px rgba(34, 36, 33, 0.14)`. Fondo oscurecido con overlay `rgba(34, 36, 33, 0.4)`.

## Shapes

- `rounded.sm` (4px): Badges técnicos y casillas de selección.
- `rounded.md` (8px): Tarjetas de artículo (`card-article`), bloques de paso de rutina (`guide-usage`) y campos de código postal.
- `rounded.lg` (14px): Tarjetas de producto (`card-product`), contenedores de lead magnet y resumen del carrito (`cart-summary`).
- `rounded.full` (9999px): Botones primarios y secundarios, inputs de texto (`input-field`), chips de filtro (`chip-filter`) y tags identificadores (`tag-routine`, `tag-offer`), reflejando la fluidez orgánica y ligereza de Nabi Skin.

## Components

### `button-primary`

Botón de acción principal ("Ver productos", "Comprar", "Quiero la guía").

- **Contenido:** Texto centrado en `label-md`, padding 12px horizontal y 24px vertical, bordes redondeados completos (`rounded.full`).
- **Regla:** Solo puede existir un `button-primary` por bloque visual visible para no saturar al usuario.
- **Estados:**
  - *Normal:* Fondo `primary`, texto `on-primary`.
  - *Hover (`button-primary-hover`):* Fondo `primary-hover`, cursor pointer.
  - *Active (`button-primary-active`):* Fondo `primary-active`.
  - *Disabled (`button-primary-disabled`):* Fondo `disabled`, texto `on-disabled`, cursor not-allowed.

### `button-secondary`

Botón secundario para acciones alternativas ("Ver detalle", "Leer guías", "Test de rutina").

- **Contenido:** Fondo blanco `surface`, texto en `primary`, borde de 1px sólido en `primary`, padding 12px 24px, `rounded.full`.
- **Regla:** Acompaña al botón primario o actúa dentro de las tarjetas de producto.
- **Estados:**
  - *Normal:* Fondo `surface`, texto `primary`.
  - *Hover (`button-secondary-hover`):* Fondo `secondary`, texto `primary-hover`.
  - *Active:* Fondo `secondary` con opacidad atenuada.
  - *Disabled:* Fondo `disabled`, borde `disabled`, texto `on-disabled`.

### `card-product`

Tarjeta individual del catálogo de productos.

- **Contenido:** Imagen superior con ratio 1:1, badge `tag-routine` en esquina superior, nombre en `title-md` (máximo 2 líneas; si excede, termina en "…"), precio en `title-md` con peso semibold y botón secundario `button-secondary` ("Ver detalle").
- **Regla:** El precio siempre debe ser visible sin necesidad de interactuar con la tarjeta.
- **Estados:**
  - *Normal:* Borde de 1px sólido en `#E2DFD6`, fondo `surface`.
  - *Hover (`card-product-hover`):* Sombra elevada Capa 2 y micro-escala de imagen al 103%.
  - *Agotado:* Imagen desaturada al 50% con tag "Agotado" y botón secundario inhabilitado.

### `tag-routine`

Etiqueta de indicación de tipo de piel ("Piel sensible", "Barrera cutánea", "Piel mixta").

- **Contenido:** Texto en `label-sm` mayúscula ligera, fondo `secondary`, texto `on-secondary`, padding 4px 10px, bordes `rounded.full`.
- **Regla:** Máximo 2 tags por producto para no generar ruido visual a Sofía.

### `tag-offer`

Etiqueta para ofertas especiales ("10% OFF", "Ahorra $2.500", "Kit exclusivo").

- **Contenido:** Texto en `label-sm` en blanco `on-tertiary`, fondo `tertiary`, padding 4px 10px, bordes `rounded.full`.
- **Regla:** Se ubica sobre la esquina superior derecha de la tarjeta y desaparece cuando la promoción no está activa.

### `chip-filter`

Botón de filtrado rápido por categoría de producto o necesidad ("Todos", "Limpiadores", "Sérums", "Cremas", "Protectores").

- **Contenido:** Texto en `label-sm`, padding 8px 16px, forma píldora `rounded.full`.
- **Regla:** Siempre hay un chip activo por defecto ("Todos").
- **Estados:**
  - *Inactivo (`chip-filter`):* Fondo `surface`, borde 1px en `#D4D2C5`, texto `on-surface`.
  - *Activo (`chip-filter-active`):* Fondo `primary`, texto `on-primary`, borde `primary`.
  - *Hover:* Fondo `#F5F3EC` para los inactivos.

### `input-field`

Campo para ingreso de datos (buscador, correo del lead magnet, calculadora de despacho).

- **Contenido:** Texto en `body-md`, padding 12px 18px, borde de 1px sólido en `#D4D2C5`, fondo `surface`.
- **Regla:** Siempre incluye placeholder explicativo en `on-surface-variant` ("tu@correo.cl", "Buscar por ingrediente...").
- **Estados:**
  - *Normal:* Borde `#D4D2C5`.
  - *Focus (`input-field-focus`):* Borde de 1.5px en `primary` con halo suave `0 0 0 3px rgba(45, 90, 67, 0.12)`.
  - *Error:* Borde en `error` con mensaje inferior en `message-error`.

### `card-article`

Tarjeta de contenido educativo y blog de K-Beauty.

- **Contenido:** Imagen de portada rectangular (ratio 16:9), categoría en `label-sm`, título del artículo en `title-md`, tiempo estimado de lectura en `on-surface-variant` ("3 min de lectura").
- **Regla:** El título tiene un límite estricto de 3 líneas. El tiempo de lectura siempre va precedido por el ícono de reloj o texto explícito.

### `guide-usage`

Bloque didáctico de rutina en ficha de producto que desglosa cómo aplicar el cosmético.

- **Contenido:** Estructura de 3 columnas o filas: "Para qué sirve", "Cómo usarlo" y "Paso de la rutina" (ej. "Paso 6: Sérum").
- **Regla:** Textos redactados en lenguaje simple y directo para personas principiantes, sin jerga científica incomprensible.

### `cart-summary`

Contenedor del resumen de compra y calculadora de despacho.

- **Contenido:** Subtotal de productos, campo de cálculo de comuna con botón `Calcular`, costo de envío explícito, total en negrita `headline-md` y botón primario "Ir a pagar".
- **Regla:** El costo de despacho debe mostrarse antes de pedir datos de pago para eliminar la frustración de costos sorpresivos.

### `message-error` y `message-success`

Alertas contextuales de retroalimentación en formularios.

- **Contenido:** Texto en `body-sm` acompañado de ícono semántico.
- **Regla:** Se sitúan inmediatamente debajo del campo correspondiente, nunca en popups intrusivos.

## Do's and Don'ts

### Do's (Lo que siempre se hace)

- **Sí** mantener el fondo de página en `neutral` (`#FAF8F5`) para sostener una sensación cálida y libre de deslumbramiento.
- **Sí** especificar en cada producto a qué tipo de piel beneficia y en qué paso de la rutina coreana se aplica.
- **Sí** asegurar que todo botón principal utilice exclusivamente `button-primary` con esquinas redondeadas completas (`rounded.full`).
- **Sí** verificar que todo texto conserve un ratio de contraste mínimo de 4.5:1 (AA) sobre su superficie de fondo.
- **Sí** priorizar la visualización fluida y touch-friendly en pantallas móviles menores a 768px.

### Don'ts (Lo que nunca se hace)

- **No** usar colores saturados como rojo chillón, azul eléctrico o negro puro `#000000`.
- **No** ocultar el precio de un producto ni postergar el cálculo del despacho hasta el último paso del checkout.
- **No** usar tipografía decorativa `Playfair Display` en párrafos largos o textos de navegación pequeña.
- **No** recargar la interfaz con más de dos sombras en un mismo plano.
- **No** colocar más de un botón primario con color `primary` compitiendo en la misma sección.
