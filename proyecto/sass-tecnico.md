# Documentación del Sistema de Estilos y Sass (FestivAll)

Este documento detalla la arquitectura de diseño, la paleta de colores, los componentes personalizados y la integración de **Bootstrap 5** utilizados en la interfaz de la plataforma **FestivAll**.

---

## 🎨 Paleta de Colores (Theme Colors)

El proyecto utiliza una estética oscura (*Dark Mode*) con contrastes vibrantes inspirados en la vida nocturna y los festivales de música.

### Colores Principales
| Tipo | Selector / Hex | Uso Principal | Vista / Ejemplo |
| :--- | :--- | :--- | :--- |
| **Fondo Principal** | `#0b0b12` | Fondos de página (`<body>`, `<main>`). | Fondo general en `home.html`, `explorador.html` |
| **Fondo de Tarjetas** | `#161624` | Contenedores secundarios, modales, footer. | `card.html`, `footer.html`, Modal de compra |
| **Color de Acento** | `#ff6b35` | Botones de acción (CTA), realces de marca. | Botón "Ver Detalles", "Comprar", Logo "All" |
| **Color Secundario** | `#7a5cff` | Subtítulos de marca o detalles finos. | Subtexto "Almería" en el Navbar |

### Estados de Texto
* **Texto Principal:** `#ffffff` (Blanco con variaciones de opacidad `text-opacity-90` para legibilidad).
* **Texto Secundario:** `#6c757d` / Clases `text-secondary` (Gris para ubicaciones, géneros y precios).

---

## 🏗️ Estructura y Clases Personalizadas (Custom Utility Classes)

Además de los utilitarios nativos de Bootstrap, el proyecto cuenta con clases de CSS/Sass personalizadas encargadas de la identidad visual (definidas en tu `custom.css`):

### 1. Componentes de Interfaz
* `.banner-evento`: Genera la sección superior en las fichas de los festivales. Aplica centrado de texto y gestiona el contraste sobre imágenes de fondo.
* `.caja-info`: Contenedor con bordes suavizados (`rounded-4`) y padding interno diseñado para estructurar la información clave (Ubicación, fechas, precios).
* `.badge-favorito`: Elemento flotante con posición absoluta (`position-relative` en el contenedor padre) para destacar la interacción de añadir a favoritos mediante un icono de estrella (`bi-star-fill`).
* `.alert-custom`: Modificación del contenedor de alertas de Bootstrap adaptado a la estética oscura del sitio.

### 2. Efectos y Animaciones
* `.hover-white`: Aplicado en los enlaces del Footer (`footer.html`). Genera una transición suave (`transition: color 0.2s ease-in-out`) cambiando el texto de gris a blanco brillante al pasar el cursor.

---

## ⚡ Integración de Bootstrap 5 y Buenas Prácticas

El proyecto aprovecha el potencial de Bootstrap 5 mediante personalizaciones directas en línea y clases utilitarias del framework:

### Sistema de Rejilla (Grid System) adaptativo:
En `explorador.html` se hace un uso avanzado de las filas de columnas variables para asegurar que las tarjetas de los festivales se adapten perfectamente a cualquier pantalla:
```html
<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-3">