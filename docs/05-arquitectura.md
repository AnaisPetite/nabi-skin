# Arquitectura de la información — Nabi Skin

## Mapa de sitio

<!-- Incluye landing, blog, tienda y las páginas obligatorias:
contacto, preguntas frecuentes, términos, privacidad y 404. -->


Inicio (landing)
├── Tienda
│   ├── Categoría: Limpiadores
│   ├── Categoría: Tónicos y Esencias
│   ├── Categoría: Sérums y Tratamientos
│   ├── Categoría: Hidratantes
│   ├── Categoría: Protectores solares
│   ├── Categoría: Kits de rutina
│   ├── Ficha de producto
│   └── Carrito
├── Blog
│   ├── Categoría: Rutina coreana
│   ├── Categoría: Tipos de piel
│   ├── Categoría: Ingredientes clave
│   └── Artículo
├── Nosotros
├── Contacto
├── Preguntas frecuentes
├── Términos y condiciones
├── Política de privacidad
└── 404


## User flows

> Guía: [User flow](../evaluacion/guias/fase-1-requerimientos/06-user-flow.md)

### Flujo 1: compra

Instagram (reel sobre rutina coreana para piel sensible)
→ Landing
→ [Clic en "Ver productos"]
→ Tienda
→ [Filtra por "Kits" y "Piel sensible"]
→ Ficha de producto: Kit Limpieza y Cuidado Facial Coreano
→ [Revisa para qué sirve, sus ingredientes y elige la variante]
◇ ¿Tiene dudas?
    ├── Sí → [Clic en "Consultar por WhatsApp"] → WhatsApp
    └── No → [Clic en "Agregar al carrito"]
→ Carrito
→ [Calcula despacho con su comuna]
→ Fin: carrito listo para pagar



### Flujo 2: contenido

Flujo 2: contenido

Google ("cómo restaurar la barrera cutánea")
→ Artículo: "Barrera cutánea dañada: 5 claves para recuperarla"
→ [Lee y hace clic en el producto recomendado]
→ Ficha de producto: Cera Hidratante K-Beauty
◇ ¿Quiere comprar ahora?
    ├── Sí → [Agregar al carrito] → Carrito
    └── No → [Ir a página Contacto para asesoría personalizada]
        → Fin: mensaje enviado



## Categorías

> Guía: [Categorías de productos y temas del blog](../evaluacion/guias/fase-1-requerimientos/07-categorias.md)

### Categorías de productos

| Categoría | Productos |
| Piel Irritada y Rojez | Crema hidratante reparadora de barrera cutánea, Limpiador acuoso en espuma de centella asiática, Kit rutina básica para piel sensible |
| Manchas y Opacidad  | Sérum de niacinamida y vitamina C, Tónico hidratante con ácido hialurónico, Protector solar coreano SPF 50+ |
| Limpieza y Poros | Aceite limpiador desmaquillante, Gel limpiador suave de bajo pH, Kit rutina anti-imperfecciones |

### Categorías del blog

| Categoría | Idea de artículo | Necesidad o motivación de la proto-persona | Producto relacionado |
| Rutina Coreana | "Doble limpieza coreana: Guía paso a paso para limpiar tu rostro sin irritarlo" | Quiere aprender a armar su rutina paso a paso de forma simple y sin dañarse la piel. |Aceite limpiador desmaquillante, Limpiador acuoso en espuma. |
| Soluciones para la piel | "¿Piel roja o tirante? 5 señales de que tu barrera cutánea está dañada y cómo recuperarla" | Necesita entender por qué su piel se ve mal o irritada y cómo solucionarlo rápidamente. | Crema hidratante reparadora de barrera cutánea. |
| Ingredientes clave | "Niacinamida y Centella Asiática: para qué sirven y cómo transforman la textura de la piel" | Desea saber para qué sirve cada ingrediente en lenguaje simple antes de comprar. | Serúm de niacinamida y vitamina C |
