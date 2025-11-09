# Complemento: SEO, Meta Tags & Estructura de Páginas para Melassa Landing

**Documento complementario a la Guía Melassa Coffee & Bake**

---

## 📊 Tabla de Contenidos

1. [SEO vs Social Media Meta Tags - Diferencias](#seo-vs-social-media)
2. [Listado de Secciones Recomendadas](#listado-de-secciones)
3. [Estructura de Navegación](#estructura-de-navegación)
4. [Checklist Pre-Desarrollo](#checklist-pre-desarrollo)
5. [Consideraciones Importantes](#consideraciones-importantes)

---

## SEO vs Social Media - ¿Diferentes Reglas?

### ⚠️ RESPUESTA CORTA: SÍ, TIENEN NORMAS DIFERENTES

Aunque el contenido puede ser similar, **SEO y redes sociales tienen longitudes y formatos distintos**. Aquí está la comparación completa:

---

## 1. Meta Title (Etiqueta `<title>`)

### Uso: SEO + Navegador

| Aspecto | Especificación |
|--------|------------------|
| **Longitud ideal** | 50-60 caracteres |
| **Máximo recomendado** | 70 caracteres |
| **Pixel limit** | 580 pixels (desktop) |
| **¿Se trunca?** | SÍ, en Google Search |
| **Ubicación en SERP** | Como título clickeable |

### Ejemplo para Melassa:
```html
❌ MALO (67 caracteres - se trunca):
<title>Melassa Coffee & Bake | Galletas Estilo Crumbl, Rollitos de Canela y Tartas Personalizadas Madrid</title>

✅ BUENO (57 caracteres - perfecto):
<title>Melassa Coffee & Bake | Galletas & Café Madrid</title>

✅ MEJOR (55 caracteres - incluye palabra clave):
<title>Galletas Artesanales Madrid | Melassa Coffee & Bake</title>
```

### Reglas SEO para Meta Title:
- ✅ Incluir palabra clave principal al inicio
- ✅ Incluir marca al final (| Nombre)
- ✅ Ser descriptivo pero conciso
- ✅ Usar separadores: | o -
- ❌ NO repetir palabras (keyword stuffing)
- ❌ NO prometer cosas que no cumples

---

## 2. Meta Description (Etiqueta `<meta name="description">`)

### Uso: SEO + Google Search Results

| Aspecto | Especificación |
|--------|------------------|
| **Longitud ideal** | 150-160 caracteres |
| **Máximo para desktop** | 158 caracteres |
| **Máximo para móvil** | 120 caracteres |
| **Pixel limit desktop** | 920 pixels |
| **Pixel limit móvil** | 680 pixels |
| **¿Se trunca?** | SÍ, pero Google reescribe 60% |
| **Ubicación en SERP** | Debajo del título |

### Ejemplo para Melassa:
```html
❌ CORTA (82 caracteres - muy corta):
<meta name="description" content="Melassa Coffee & Bake es una tienda de galletas artesanales en Madrid.">

⚠️ LARGA (189 caracteres - se trunca):
<meta name="description" content="Descubre las mejores galletas estilo Crumbl Cookies, rollitos de canela frescos, brownies de chocolate y tartas artesanales personalizadas en Melassa Coffee & Bake, tu panadería artesanal favorita en Madrid con café de especialidad.">

✅ PERFECTA (156 caracteres):
<meta name="description" content="Galletas artesanales estilo Crumbl, rollitos de canela, brownies y tartas personalizadas en Madrid. ¡Visita Melassa Coffee & Bake hoy!">
```

### Reglas SEO para Meta Description:
- ✅ Incluir palabra clave principal
- ✅ Incluir CTA ("Visita", "Descubre", "Pide ahora")
- ✅ Dirigirse al usuario ("tus", "tu")
- ✅ Ser específico (incluir ubicación si es local)
- ✅ Reflejar contenido real de la página
- ❌ NO duplicar en múltiples páginas
- ❌ NO hacer promesas falsas

---

## 3. Open Graph Tags (RRSS: Facebook, LinkedIn, Whatsapp)

### Uso: Redes Sociales cuando compartes el link

| Elemento | Longitud | Especificación |
|----------|----------|-----------------|
| **og:title** | 60-90 caracteres | Más corto que SEO title |
| **og:description** | 150-200 caracteres | Puede ser más largo que meta description |
| **og:image** | - | 1200x630 px (mínimo 600x314 px) |
| **og:image:alt** | 125 caracteres | Descripción de la imagen |

### Ejemplo para Melassa:
```html
<!-- Facebook / WhatsApp -->
<meta property="og:title" content="Melassa Coffee & Bake | Galletas Irresistibles">
<meta property="og:description" content="Descubre nuestras galletas estilo Crumbl, rollitos de canela, brownies de chocolate y tartas artesanales personalizadas. ¡Visítanos en Madrid!">
<meta property="og:image" content="https://melassa.es/og-image.jpg">
<meta property="og:image:alt" content="Galletas de colores con logo Cookie Monster">
<meta property="og:url" content="https://melassa.es">
<meta property="og:type" content="business.business">
```

### Diferencias clave OG vs SEO:
- **OG:title** (88 caracteres max, pero 60-90 ideal)
- **Meta title** (50-60 caracteres)

**Facebook trunca después de ~88 caracteres**. Ejemplo en feed:
```
"Melassa Coffee & Bake | Galletas Irresistibles 🍪 Descubre nuestras..." ← Texto que ve
```

---

## 4. Twitter Card Tags

### Uso: Twitter / X cuando compartes

| Elemento | Longitud | Especificación |
|----------|----------|-----------------|
| **twitter:title** | 70 caracteres | Más corto aún |
| **twitter:description** | 200 caracteres | Un poco más que Facebook |
| **twitter:image** | - | 1200x630 px (ratio 2:1 recomendado) |
| **twitter:card** | - | "summary_large_image" para fotos grandes |

### Ejemplo para Melassa:
```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Melassa Coffee & Bake">
<meta name="twitter:description" content="Galletas artesanales, rollitos de canela y tartas personalizadas en Madrid 🍪">
<meta name="twitter:image" content="https://melassa.es/twitter-image.jpg">
<meta name="twitter:creator" content="@melassa_bake">
```

---

## 📋 Tabla Comparativa: Longitudes de Meta Tags

| Elemento | SEO | Facebook OG | Twitter |
|----------|-----|-----------|---------|
| **Título** | 50-60 caracteres | 60-90 caracteres | 70 caracteres |
| **Descripción** | 150-160 caracteres | 150-200 caracteres | 200 caracteres |
| **Imagen** | N/A | 1200x630 px | 1200x630 px (2:1) |

### Regla de Oro:
**La descripción de redes sociales PUEDE ser más larga y casual que el meta description SEO**

---

## 🏗️ Listado de Secciones Recomendadas

Para una **panadería artesanal con tienda física y cafetería**, estas son las secciones esenciales:

### Estructura Recomendada para Melassa

```
PÁGINAS PRINCIPALES:
├── Home (Landing Page Principal)
├── Productos / Menú
├── Sobre Nosotros
├── Ubicación & Contacto
└── (Opcional: Blog de Recetas)

SECCIONES DENTRO DE HOME:
├── 1. Hero Section
├── 2. Productos Destacados (4 categorías)
├── 3. Sabor/Producto de la Semana (Carousel)
├── 4. Galería de Tartas Personalizadas
├── 5. Por Qué Elegirnos (Value Proposition)
├── 6. Ubicación & Horarios
├── 7. Testimonios / Reviews
├── 8. Newsletter Signup
├── 9. Formulario de Pedidos Personalizados
└── 10. Footer con Enlaces Rápidos
```

---

## Sección 1: Hero Section

**Propósito:** Captar atención inmediata (first 5 seconds)

**Elementos clave:**
- Imagen impactante (cookie/producto grande)
- Headline principal (beneficio, no features)
- Subheadline (clarificación)
- CTA principal (botón)
- Logo de Cookie Monster visible

**Ejemplos de Headlines:**

❌ MALO: "Panadería Artesanal Melassa"
❌ MALO: "Las Mejores Galletas desde 2020"

✅ BUENO: "Las Galletas Más Irresistibles de Madrid 🍪"
✅ MEJOR: "Galletas que Desaparecen en Segundos | Estilo Crumbl"

**Altura mínima:** 100% viewport (h-screen en Tailwind)

---

## Sección 2: Productos Destacados

**Propósito:** Mostrar variedad de oferta

**Estructura:**
```
┌─────────────────────────────────┐
│     NUESTROS PRODUCTOS          │
├─────────────────────────────────┤
│
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐
│  │ Galletas │  │ Rollitos │  │Brownies  │  │ Tartas   │
│  │ Crumbl   │  │de Canela │  │Chocolate │  │Personal. │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘
│
│  Cada categoría con:
│  - Imagen de producto
│  - Nombre
│  - Descripción breve (1-2 líneas)
│  - Precio (opcional)
│  - Botón "Ver Más"
│
└─────────────────────────────────┘
```

**Recomendación:** Grid 4 columnas (desktop) → 2 columnas (tablet) → 1 columna (móvil)

---

## Sección 3: Sabor/Producto de la Semana

**Propósito:** Crear urgencia y FOMO (Fear of Missing Out)

**Estructura:**
```
┌──────────────────────────────────────┐
│   🌟 SABOR DE LA SEMANA 🌟          │
├──────────────────────────────────────┤
│
│  [← IMAGEN GRANDE DEL PRODUCTO →]
│  
│  NOMBRE ATRACTIVO
│  Descripción detallada y atractiva
│  
│  Disponible hasta el domingo
│  [PEDIR AHORA]
│
└──────────────────────────────────────┘
```

**Funcionalidad:** Carousel con botones anterior/siguiente (React)

**Actualización:** Cambiar cada lunes (estrategia tipo Crumbl)

---

## Sección 4: Galería de Tartas Personalizadas

**Propósito:** Mostrar capacidad de customización + portfolio

**Estructura:**
```
┌──────────────────────────────────────┐
│    CREACIONES PERSONALIZADAS         │
├──────────────────────────────────────┤
│
│  [IMG] [IMG] [IMG] [IMG]
│  [IMG] [IMG] [IMG] [IMG]
│  [IMG] [IMG] [IMG] [IMG]
│
│  Con HOVER: Ampliar imagen (Lightbox)
│  Mostrar: Sabor, porciones, ocasión
│
└──────────────────────────────────────┘
```

**Elementos interactivos:**
- Hover: Escala imagen (1.05x)
- Click: Abre lightbox
- Navegación: Anterior/Siguiente
- Contador: "3 / 12" (imagen actual / total)

---

## Sección 5: Por Qué Elegirnos / Value Proposition

**Propósito:** Construir confianza y diferenciación

**Estructura:**
```
┌─────────────────────────────────────┐
│   POR QUÉ ELEGIR MELASSA           │
├─────────────────────────────────────┤
│
│  🎨 ARTESANAL              👨‍🍳 EXPERTOS
│  Recetas propias,          +10 años en
│  sin aditivos              la industria
│
│  ✨ FRESCO                 🍪 PERSONALIZADO
│  Horneado diario          Pedidos custom
│                            para eventos
│
└─────────────────────────────────────┘
```

**Cada punto debe incluir:**
- Icono o emoji
- Título
- 1-2 líneas de descripción

---

## Sección 6: Ubicación & Horarios

**Propósito:** Información práctica para clientes

**Estructura:**
```
┌────────────────────────────────────────┐
│         VISÍTANOS                      │
├────────────────────────────────────────┤
│
│  [MAPA EMBEBIDO]          │ CONTACTO
│                           │ 
│                           │ 📍 Calle Principal 123
│                           │    Madrid 28001
│                           │
│                           │ 📞 +34 91 234 5678
│                           │ 📧 info@melassa.es
│                           │
│                           │ HORARIOS
│                           │ Lun-Vie: 8:00-20:00
│                           │ Sáb: 9:00-21:00
│                           │ Dom: 10:00-19:00
│
└────────────────────────────────────────┘
```

**Elementos técnicos:**
- Google Maps embebido (con marker personalizado si es posible)
- NAP (Name, Address, Phone) consistente
- Información en Schema.org LocalBusiness

---

## Sección 7: Testimonios / Reviews

**Propósito:** Social proof - aumentar confianza

**Estructura:**
```
┌───────────────────────────────────┐
│      LO QUE DICEN NUESTROS        │
│         CLIENTES                  │
├───────────────────────────────────┤
│
│  ⭐⭐⭐⭐⭐
│  "Las mejores galletas que he probado"
│  - María García
│
│  ⭐⭐⭐⭐⭐
│  "Perfectas para mi cumpleaños"
│  - Juan López
│
│  ⭐⭐⭐⭐⭐
│  "La tarta fue espectacular"
│  - Sarah Chen
│
│  Rating Google: 4.8/5 ⭐
│
└───────────────────────────────────┘
```

**Fuentes de reviews:**
- Google My Business (automático si das permiso)
- Yelp
- Cliente testimonios locales
- Instagram UGC

---

## Sección 8: Newsletter Signup

**Propósito:** Email marketing para repetidas compras

**Estructura:**
```
┌────────────────────────────────────┐
│   ¡No Te Pierdas Nuestras Ofertas! │
│                                    │
│  Suscríbete a nuestro newsletter   │
│  para sabores exclusivos           │
│                                    │
│  [tu@email.com________]            │
│        [SUSCRIBIR]                 │
│                                    │
│  ✓ Recibe sabor de la semana       │
│  ✓ Promociones especiales          │
│  ✓ Eventos exclusivos              │
│                                    │
└────────────────────────────────────┘
```

**Integraciones recomendadas:**
- Mailchimp
- ConvertKit
- Brevo (antes Sendinblue)

---

## Sección 9: Formulario de Pedidos Personalizados

**Propósito:** Facilitar pedidos de tartas personalizadas

**Campos principales:**
```
INFORMACIÓN PERSONAL
├── Nombre completo *
├── Email *
└── Teléfono *

DETALLES DEL EVENTO
├── Fecha del evento *
├── Tipo de ocasión (boda, cumpleaños, etc.)
└── Número de porciones

CUSTOMIZACIÓN
├── Sabor principal (dropdown)
├── Alergias/Restricciones dietéticas
├── Preferencias de decoración
└── Mensaje especial (texto libre)

ENVÍO/ENTREGA
├── ¿Recogida o entrega?
├── Dirección de entrega
└── Mensaje especial (opcional)
```

**Validación cliente:**
- Email válido
- Teléfono válido
- Fecha en futuro
- Campos requeridos marcados

---

## Sección 10: Footer

**Propósito:** Información legal + navegación secundaria

**Estructura:**
```
┌──────────────────────────────────────┐
│ FOOTER                               │
├──────────────────────────────────────┤
│
│ LINKS RÁPIDOS  │ CATEGORÍAS  │ LEGAL
│ • Home         │ • Galletas  │ • Privacidad
│ • Ubicación    │ • Brownies  │ • Términos
│ • Contacto     │ • Rollitos  │ • Cookies
│ • Blog         │ • Tartas    │ • Créditos
│
│ SÍGUENOS              SUSCRÍBETE
│ 📷 Instagram          [email]
│ 📘 Facebook           [SUSCRIBIR]
│ 𝕏 Twitter
│
│ © 2025 Melassa Coffee & Bake
│ Diseñado con ❤️
│
└──────────────────────────────────────┘
```

**Elementos legales a incluir:**
- Política de privacidad
- Términos y condiciones
- Política de cookies
- Información de contacto completa
- Copyright

---

## 🗂️ Estructura de Navegación

### Header - Navegación Principal

**Desktop (pantalla grande):**
```
[LOGO] Productos | Ubicación | Contacto | [CTA: Pedir Ahora]
```

**Móvil (hamburger menu):**
```
[LOGO] [☰ MENÚ]

Cuando se abre el menú:
├── Productos
├── Ubicación
├── Contacto
├── Blog (si existe)
└── [CTA: Pedir Ahora]
```

**Elementos del Header:**
- Logo clickeable (vuelve a home)
- Navegación principal (3-5 items)
- CTA primario (botón destacado)
- Sticky (queda fijo al scroll en móvil)

---

## 📋 Checklist Pre-Desarrollo

### FASE 1: PLANIFICACIÓN (Antes de programar)

#### Contenido
- [ ] Definir headlines principales (H1)
- [ ] Redactar meta titles y descriptions para CADA página
- [ ] Redactar og:title y og:description
- [ ] Redactar twitter:card tags
- [ ] Escribir copy de cada sección
- [ ] Definir palabras clave (keywords) por página
- [ ] Recolectar testimonios de clientes
- [ ] Preparar contenido actualizable (sabor de la semana template)

#### Imágenes & Media
- [ ] Foto hero de producto (1920x1080 mínimo)
- [ ] Fotos de 4 categorías productos
- [ ] Fotos de tartas personalizadas (8-12 mínimo)
- [ ] Foto tienda física (interior/exterior)
- [ ] Logo en blanco, azul, rosa (vectores)
- [ ] Favicon
- [ ] Open Graph image (1200x630 px)
- [ ] Twitter image (1200x630 px, ratio 2:1)

#### Información del Negocio
- [ ] Dirección exacta
- [ ] Teléfono de contacto
- [ ] Email de contacto
- [ ] Horarios de apertura (completos, incluir festivos)
- [ ] Ubicación GPS (lat/long para mapa)
- [ ] URLs de redes sociales (@instagram, @facebook, etc.)

#### Infraestructura
- [ ] Registrar dominio (melassa-coffee-bake.es)
- [ ] Configurar hosting/Netlify
- [ ] Configurar email (info@melassa.es)
- [ ] Google My Business - perfil completo
- [ ] Configurar Google Analytics 4
- [ ] Facebook Pixel (si usas ads)

---

### FASE 2: DESARROLLO

#### Setup Astro
- [ ] Crear proyecto: `npm create astro@latest`
- [ ] Instalar React: `npx astro add react`
- [ ] Instalar Tailwind: `npx astro add tailwind`
- [ ] Configurar astro.config.mjs
- [ ] Configurar tailwind.config.mjs
- [ ] Configurar tsconfig.json

#### Estructura de Carpetas
- [ ] Crear carpeta src/layouts
- [ ] Crear carpeta src/components/Astro
- [ ] Crear carpeta src/components/React
- [ ] Crear carpeta public/images
- [ ] Crear carpeta src/pages

#### Componentes Base
- [ ] MelassaLayout.astro (con props SEO)
- [ ] Header.astro
- [ ] Footer.astro
- [ ] Hero.astro
- [ ] ProductCard.astro

#### Componentes React
- [ ] ProductCarousel.jsx
- [ ] CustomCakeForm.jsx
- [ ] GalleryLightbox.jsx

#### Página Principal
- [ ] index.astro con estructura completa
- [ ] Integrar todos los componentes
- [ ] Validar responsivo

---

### FASE 3: SEO & Optimización

#### Meta Tags
- [ ] Meta title único para cada página
- [ ] Meta description (150-160 chars) para cada página
- [ ] og:title, og:description, og:image
- [ ] twitter:title, twitter:description, twitter:image
- [ ] Canonical URLs
- [ ] Viewport meta tag
- [ ] Robots meta tag (index, follow)

#### Structured Data (Schema.org)
- [ ] LocalBusiness schema
- [ ] PostalAddress schema
- [ ] OpeningHoursSpecification
- [ ] AggregateRating (si tienes reviews)
- [ ] Product schema (para productos)

#### Performance
- [ ] Optimizar imágenes (WebP format)
- [ ] Lazy loading activo
- [ ] CSS minificado
- [ ] JavaScript solo en islands
- [ ] Caché headers configurados
- [ ] Compression gzip activado

#### Accesibilidad
- [ ] Alt text en TODAS las imágenes
- [ ] Contraste de colores (WCAG AA)
- [ ] Links con aria-labels
- [ ] Navegación por teclado
- [ ] Formularios con labels asociados

#### Testing
- [ ] PageSpeed Insights: 95+ score
- [ ] Mobile-Friendly Test: PASS
- [ ] Lighthouse: 90+
- [ ] Prueba en 3+ navegadores
- [ ] Prueba en móvil, tablet, desktop

---

### FASE 4: PRE-DEPLOY

#### Últimas Verificaciones
- [ ] Links internos funcionan
- [ ] Formularios funcionan
- [ ] Mapa embebido funciona
- [ ] Redes sociales vinculan correctamente
- [ ] Email de contacto funciona
- [ ] Newsletter signup funciona
- [ ] 404 page personalizada

#### Configuración Netlify
- [ ] Conectar repositorio GitHub
- [ ] Configurar build command: `npm run build`
- [ ] Configurar publish directory: `dist`
- [ ] Configurar environment variables (si aplica)
- [ ] Configurar redirects (netlify.toml)

#### Google & Búsqueda
- [ ] Verificar sitio en Google Search Console
- [ ] Enviar sitemap.xml
- [ ] Verificar robots.txt
- [ ] Configurar Google My Business
- [ ] Solicitar crawling en GSC

#### Redes Sociales
- [ ] Compartir en Facebook
- [ ] Compartir en Instagram
- [ ] Compartir en LinkedIn
- [ ] Verificar Open Graph preview
- [ ] Verificar Twitter Card preview

---

### FASE 5: POST-DEPLOY (Primeras 2 semanas)

#### Monitoreo
- [ ] Revisar Google Analytics
- [ ] Revisar Search Console
- [ ] Revisar ranking de palabras clave
- [ ] Revisar bounce rate
- [ ] Revisar errores 404

#### Mejoras
- [ ] A/B test en CTAs
- [ ] Ajustar copy si necesario
- [ ] Recolectar feedback de clientes
- [ ] Corregir bugs encontrados

---

## ⚠️ Consideraciones Importantes

### 1. SEO Local es CRÍTICO

Para una **tienda física**, el SEO local es más importante que el SEO general.

**Prioritarios:**
```
✅ NAP Consistency (Name, Address, Phone)
   - Mismo formato en: Sitio, Google My Business, Yelp, etc.

✅ Google My Business
   - Foto de tienda
   - Foto de productos
   - Horarios actualizados
   - Reviews respondidas

✅ Local Reviews
   - Google Reviews
   - Yelp
   - TripAdvisor (si aplica)

✅ Palabras clave locales
   - "Galletas en Madrid"
   - "Brownies artesanales barrio de X"
   - "Tartas personalizadas cerca de mí"
```

### 2. Convergencia de Meta Tags

**Solución elegante: Usar un layout centralizado**

```astro
---
// src/layouts/MelassaLayout.astro
interface Props {
  title: string;           // 50-60 chars
  description: string;     // 150-160 chars
  image: string;
  ogTitle?: string;        // 60-90 chars (default: title)
  ogDescription?: string;  // 150-200 chars (default: description)
  twitterTitle?: string;   // 70 chars (default: ogTitle)
  twitterDescription?: string; // 200 chars (default: ogDescription)
}

const {
  title,
  description,
  image,
  ogTitle = title,
  ogDescription = description,
  twitterTitle = ogTitle.substring(0, 70),
  twitterDescription = ogDescription.substring(0, 200),
} = Astro.props;
---

<head>
  <!-- SEO -->
  <title>{title}</title>
  <meta name="description" content={description} />
  
  <!-- OG (Facebook, WhatsApp) -->
  <meta property="og:title" content={ogTitle} />
  <meta property="og:description" content={ogDescription} />
  
  <!-- Twitter -->
  <meta name="twitter:title" content={twitterTitle} />
  <meta name="twitter:description" content={twitterDescription} />
</head>
```

### 3. Imagen OG vs Twitter

Ambas necesitan imágenes diferentes pero compatible:

```
Open Graph:   1200x630 px (ratio 1.9:1)
Twitter:      1200x630 px (ratio 2:1)  ← Casi igual

✅ Usa 1200x630 px para ambas
```

### 4. El Google My Business es TAN IMPORTANTE como tu sitio web

**Acciones recomendadas:**
```
1️⃣ Completar perfil 100% en GMB
2️⃣ Agregar fotos regularmente (cada mes)
3️⃣ Responder reviews (incluso las negativas)
4️⃣ Crear posts en GMB (tipo stories)
5️⃣ Vincular sitio web en GMB
```

**Impacto:** 40-50% de tráfico local viene de GMB, NO del sitio web.

### 5. Mobile-First es OBLIGATORIO

**Estadísticas:**
- 63% del tráfico es móvil
- Google indexa por móvil PRIMERO

**Verificar:**
- [ ] Touch targets ≥ 44x44px
- [ ] Pantalla no scrollea horizontalmente
- [ ] Botones CTA fáciles de pulsar
- [ ] Tiempo de carga < 3 segundos en 4G

### 6. Velocidad de Carga

**Targets:**
```
Largest Contentful Paint (LCP):  ≤ 2.5 segundos
First Input Delay (FID):         ≤ 100 ms
Cumulative Layout Shift (CLS):   ≤ 0.1
```

**Herramientas:**
```
PageSpeed Insights:     https://pagespeed.web.dev
WebPageTest:            https://webpagetest.org
GTmetrix:               https://gtmetrix.com
```

### 7. Formularios y CTA Claros

❌ CONFUSO:
```
"Más información" - No sabemos qué pasa
```

✅ CLARO:
```
"Solicitar Cotización de Tarta"  - Sabemos exactamente qué hacer
"Llamar Ahora: +34 91 234 5678" - CTA directo con número
"Pedir Online"                   - Acción específica
```

### 8. Testimonios = Conversión

**Recomendación:** Incluir MÍNIMO 3 reviews con:
- Nombre completo
- ⭐⭐⭐⭐⭐ Rating
- Foto (opcional pero potente)
- Cita (1-2 líneas)

**Dónde obtenerlos:**
- Clientes locales
- Google Reviews
- Pedir feedback directo después de compra

### 9. Social Proof Elements

En orden de impacto:
1. **Reviews con foto** (más confianza)
2. **Number of customers** ("Más de 5000 clientes satisfechos")
3. **Badges/Awards** (Certificaciones)
4. **Presencia en media** ("Featured in...")
5. **Testimonios sin foto**

### 10. Responsive Images Strategy

```astro
<!-- Para productos (Astro) -->
<picture>
  <source media="(max-width: 640px)" srcset="/products/cookie-mobile.webp">
  <source media="(min-width: 641px)" srcset="/products/cookie-desktop.webp">
  <img src="/products/cookie.jpg" alt="Cookie Chocolate Chip" />
</picture>
```

---

## 🎯 Resumen de Acciones Inmediatas

### Hoy (Antes de empezar a programar):

1. **Reúne contenido:**
   - [ ] Redacta meta titles y descriptions
   - [ ] Redacta copy de secciones
   - [ ] Recopila testimonios

2. **Recopila imágenes:**
   - [ ] Hero image
   - [ ] Fotos de productos (4 categorías)
   - [ ] Fotos de tartas (8-12)
   - [ ] Foto tienda

3. **Confirma información:**
   - [ ] Dirección exacta
   - [ ] Teléfono
   - [ ] Horarios (con festivos)
   - [ ] Redes sociales

### Semana 1 (Setup):

4. **Configura infraestructura:**
   - [ ] Dominio registrado
   - [ ] Google My Business completo
   - [ ] Gmail corporativo (@melassa)

5. **Crea proyecto Astro:**
   - [ ] `npm create astro@latest`
   - [ ] `npx astro add react tailwind`

### Semana 2 (Desarrollo):

6. **Desarrolla componentes base**
7. **Integra contenido**
8. **Prueba responsivo**

### Semana 3 (Optimización):

9. **SEO & Meta tags**
10. **Performance testing**
11. **Deploy en Netlify**

---

## ✅ Conclusión

Este documento responde tus 3 preguntas principales:

1. **¿Meta tags diferentes para SEO vs RRSS?**
   - ✅ SÍ. Meta title (50-60 chars) vs OG title (60-90 chars) vs Twitter title (70 chars)
   - ✅ Meta description (150-160) vs OG description (150-200) vs Twitter (200)

2. **¿Qué secciones necesito?**
   - ✅ Hero, Productos, Sabor de la Semana, Galería, Value Prop, Ubicación, Reviews, Newsletter, Formulario, Footer

3. **¿Otras cosas importantes?**
   - ✅ SEO local CRÍTICO (Google My Business)
   - ✅ Mobile-first obligatorio
   - ✅ Velocidad < 3 segundos
   - ✅ Formularios claros con CTAs específicos
   - ✅ Testimonios = conversión

**Estás 100% preparado para empezar. ¡Adelante! 🚀**
