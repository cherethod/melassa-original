# Guía Completa: Landing Page Melassa Coffee & Bake con Astro

**Versión:** 1.0  
**Fecha:** Noviembre 2025  
**Proyecto:** Melassa Coffee & Bake - Tienda Física de Galletas Artesanales & Café

---

## Tabla de Contenidos

1. [Introducción](#introducción)
2. [Identidad de Marca](#identidad-de-marca)
3. [Arquitectura Técnica](#arquitectura-técnica)
4. [Estructura del Proyecto](#estructura-del-proyecto)
5. [Componentes Astro](#componentes-astro)
6. [Layouts y SEO](#layouts-y-seo)
7. [Componentes Interactivos React/Preact](#componentes-interactivos-reactpreact)
8. [Estilos con Tailwind CSS](#estilos-con-tailwind-css)
9. [Contenido y Secciones](#contenido-y-secciones)
10. [Optimización y Deployment](#optimización-y-deployment)
11. [Roadmap de Desarrollo](#roadmap-de-desarrollo)

---

## Introducción

**Melassa Coffee & Bake** es una tienda física que combina una cafetería artesanal con la producción y venta de:

- Galletas estilo **Crumbl Cookies** (grandes, gourmet, sabores rotativos)
- **Rollitos de canela** frescos y artesanales
- **Brownies de chocolate** premium
- **Tartas artesanales personalizadas** hechas a medida

### Objetivo de la Landing Page

- Informar sobre productos, ubicación y horarios
- Generar conversión: visitas físicas a la tienda
- Crear conexión emocional a través del branding de **Cookie Monster**
- Facilitar pedidos personalizados de tartas
- Optimización SEO para búsquedas locales

### Ventajas de Usar Astro

- **Performance:** Sitio estático ultra-rápido (95-100 PageSpeed)
- **SEO-First:** HTML optimizado nativamente
- **Flexibilidad:** Componentes Astro + React/Preact cuando se necesite interactividad
- **Islands Architecture:** Solo JavaScript donde es necesario
- **Fácil Deployment:** Netlify, Vercel, GitHub Pages

---

## Identidad de Marca

### Logo y Mascota

Tu logo es **Cookie Monster** (mascota) con versiones en:
- **Naranja** (alternativa)
- **Azul** (recomendado como primario)

### Paleta de Colores: Azul + Rosa

La combinación **azul + rosa** es ideal porque:

1. **Consonancia con Cookie Monster:** Los colores icónicos del personaje
2. **Psicología de Color:**
   - **Azul (#00ADEF):** Confianza, profesionalismo, seguridad
   - **Rosa (#FF69B4):** Calidez, diversión, accesibilidad
3. **Balance Perfecto:** Transmite tanto artesanía seria como diversión accesible
4. **Gender-Neutral:** Ampla el alcance de mercado

### Colores Específicos

| Elemento | Color | Código Hex | Uso |
|----------|-------|-----------|-----|
| **Blue Primario** | Azul Vibrante | `#00ADEF` | Logo, headlines, botones primarios |
| **Blue Oscuro** | Azul Profundo | `#2D548B` | Detalles, subheadings, hover states |
| **Pink Vibrante** | Hot Pink | `#FF69B4` | Acentos, decorativos, CTAs secundarias |
| **Pink Claro** | Rosa Suave | `#FFB6D9` | Backgrounds, overlays, secciones |
| **Blanco** | - | `#FFFFFF` | Fondo principal |
| **Gris Claro** | - | `#F5F5F5` | Fondos secundarios |
| **Gris Oscuro** | - | `#333333` | Texto principal |

### Tipografía

| Uso | Fuente | Ejemplo |
|-----|--------|---------|
| **Headings (H1-H4)** | Playfair Display (serif) | "Las Galletas Más Irresistibles" |
| **Body Text** | Inter (sans-serif) | Texto descriptivo de productos |
| **Botones/CTA** | Inter Bold (sans-serif) | "Pedir Ahora" |

---

## Arquitectura Técnica

### Stack Tecnológico

```
┌─────────────────────────────────────┐
│     Frontend (Browser)              │
│  HTML (Astro) + CSS (Tailwind)      │
│  React/Preact (Interactive Islands) │
└────────────┬────────────────────────┘
             │
┌────────────▼────────────────────────┐
│     Build & Static Generation       │
│  Astro (SSG - Static Site Gen)      │
│  Output: Pure HTML/CSS/JS           │
└────────────┬────────────────────────┘
             │
┌────────────▼────────────────────────┐
│     Deployment                      │
│  Netlify / Vercel / GitHub Pages    │
│  CDN Global + SSL Incluido          │
└─────────────────────────────────────┘
```

### Por Qué Esta Arquitectura

- **Astro:** Framework optimizado para landing pages, SSG por defecto
- **Tailwind CSS:** Desarrollo rápido, consistencia de branding, responsive automático
- **React/Preact:** Solo para componentes con interactividad real (carousels, formularios)
- **Deployment en Netlify:** Builds automáticos, formularios integrados, analytics

---

## Estructura del Proyecto

```
melassa-landing/
│
├── public/
│   ├── favicon.svg
│   ├── logo-blue.png
│   ├── logo-orange.png
│   ├── og-image.png              # Open Graph para redes
│   └── images/
│       ├── hero-cookie.jpg
│       ├── products/
│       │   ├── cookies/
│       │   │   ├── chocolate-chip.jpg
│       │   │   ├── red-velvet.jpg
│       │   │   └── (más sabores)
│       │   ├── brownies/
│       │   │   ├── fudgy.jpg
│       │   │   └── cake-style.jpg
│       │   ├── cinnamon-rolls/
│       │   │   └── classic.jpg
│       │   └── cakes/
│       │       ├── cake-portfolio-1.jpg
│       │       └── (más tartas)
│       └── location/
│           └── store-interior.jpg
│
├── src/
│   ├── layouts/
│   │   ├── BaseLayout.astro       # Layout base minimalista
│   │   └── MelassaLayout.astro    # Layout con props SEO
│   │
│   ├── components/
│   │   ├── Astro/
│   │   │   ├── Header.astro
│   │   │   ├── Footer.astro
│   │   │   ├── Hero.astro
│   │   │   ├── ProductCard.astro
│   │   │   ├── SectionDivider.astro
│   │   │   └── ContactInfo.astro
│   │   │
│   │   ├── React/
│   │   │   ├── ProductCarousel.jsx
│   │   │   ├── CustomCakeForm.jsx
│   │   │   ├── GalleryLightbox.jsx
│   │   │   └── LocationMap.jsx
│   │   │
│   │   └── SEO/
│   │       ├── SEOHead.astro      # Meta tags reutilizable
│   │       └── SchemaMarkup.astro # JSON-LD para SEO local
│   │
│   ├── pages/
│   │   └── index.astro            # Landing page principal
│   │
│   └── styles/
│       ├── global.css             # Estilos globales
│       └── tailwind.config.cjs    # Configuración Tailwind
│
├── astro.config.mjs               # Config Astro
├── tsconfig.json                  # Config TypeScript
├── package.json                   # Dependencias
└── README.md
```

---

## Componentes Astro

### 1. Header (Header.astro)

```astro
---
// src/components/Astro/Header.astro
interface Props {
  activeSection?: string;
}

const { activeSection } = Astro.props;
---

<header class="sticky top-0 z-50 bg-white/95 backdrop-blur border-b border-melassa-pink-light">
  <nav class="container mx-auto px-4 py-4 flex items-center justify-between">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 hover:opacity-80 transition">
      <img src="/logo-blue.png" alt="Melassa Logo" class="h-12 w-12" />
      <span class="font-heading text-xl font-bold text-melassa-blue">
        Melassa
      </span>
    </a>

    <!-- Navigation Menu -->
    <ul class="hidden md:flex gap-8 text-gray-700">
      <li>
        <a 
          href="#productos" 
          class={`font-medium transition ${
            activeSection === 'products' 
              ? 'text-melassa-blue' 
              : 'hover:text-melassa-pink'
          }`}
        >
          Productos
        </a>
      </li>
      <li>
        <a href="#ubicacion" class="font-medium hover:text-melassa-pink transition">
          Ubicación
        </a>
      </li>
      <li>
        <a href="#contacto" class="font-medium hover:text-melassa-pink transition">
          Contacto
        </a>
      </li>
    </ul>

    <!-- CTA Button -->
    <button class="hidden md:block bg-melassa-blue text-white px-6 py-2 rounded-full hover:bg-melassa-blue-dark transition">
      Pedir Tartas Personalizadas
    </button>

    <!-- Mobile Menu Toggle -->
    <button id="mobile-menu-toggle" class="md:hidden text-melassa-blue text-2xl">
      ☰
    </button>
  </nav>
</header>

<style>
  header {
    box-shadow: 0 2px 8px rgba(0, 173, 239, 0.1);
  }
</style>
```

### 2. Hero Section (Hero.astro)

```astro
---
// src/components/Astro/Hero.astro
interface Props {
  title: string;
  subtitle: string;
  image: string;
  ctaText?: string;
}

const { title, subtitle, image, ctaText = "Descubre Nuestros Productos" } = Astro.props;
---

<section class="relative h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-melassa-blue to-melassa-blue-dark">
  <!-- Background Image -->
  <div 
    class="absolute inset-0 opacity-30"
    style={`background-image: url('${image}'); background-size: cover; background-position: center;`}
  />

  <!-- Content -->
  <div class="relative z-10 text-center text-white px-4 max-w-4xl">
    <h1 class="font-heading text-5xl md:text-7xl font-bold mb-6 animate-fade-in">
      {title}
    </h1>
    
    <p class="text-xl md:text-2xl mb-8 text-melassa-pink-light opacity-95">
      {subtitle}
    </p>

    <button class="bg-melassa-pink text-melassa-blue-dark px-8 py-4 rounded-full text-lg font-bold hover:bg-melassa-pink-light transition transform hover:scale-105">
      {ctaText}
    </button>
  </div>

  <!-- Scroll Indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce z-10">
    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
    </svg>
  </div>
</section>

<style>
  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(-20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .animate-fade-in {
    animation: fade-in 1s ease-out;
  }
</style>
```

### 3. Product Card (ProductCard.astro)

```astro
---
// src/components/Astro/ProductCard.astro
interface Props {
  name: string;
  description: string;
  image: string;
  price?: string;
  badge?: string;
}

const { name, description, image, price, badge } = Astro.props;
---

<div class="group bg-white rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition transform hover:scale-105">
  <!-- Image Container -->
  <div class="relative h-64 overflow-hidden bg-melassa-pink-light">
    <img 
      src={image} 
      alt={name}
      class="w-full h-full object-cover group-hover:scale-110 transition duration-300"
    />
    
    {badge && (
      <div class="absolute top-4 right-4 bg-melassa-pink text-white px-4 py-2 rounded-full text-sm font-bold">
        {badge}
      </div>
    )}
  </div>

  <!-- Content -->
  <div class="p-6">
    <h3 class="font-heading text-2xl text-melassa-blue-dark mb-2">
      {name}
    </h3>
    
    <p class="text-gray-600 text-sm mb-4">
      {description}
    </p>

    <div class="flex items-center justify-between">
      {price && (
        <span class="text-melassa-pink font-bold text-lg">
          {price}
        </span>
      )}
      
      <button class="bg-melassa-blue text-white px-6 py-2 rounded-full text-sm font-bold hover:bg-melassa-blue-dark transition">
        Ver Más
      </button>
    </div>
  </div>
</div>
```

---

## Layouts y SEO

### 1. Base Layout (BaseLayout.astro)

```astro
---
// src/layouts/BaseLayout.astro
interface Props {
  title: string;
  description: string;
}

const { title, description } = Astro.props;
const canonicalUrl = new URL(Astro.url.pathname, Astro.site);
---

<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    
    <title>{title}</title>
    <meta name="description" content={description} />
    <link rel="canonical" href={canonicalUrl} />
    
    <!-- Open Graph para Redes Sociales -->
    <meta property="og:type" content="website" />
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:image" content="/og-image.png" />
    <meta property="og:url" content={canonicalUrl} />
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content={title} />
    <meta name="twitter:description" content={description} />
  </head>
  
  <body class="bg-white text-gray-900">
    <slot />
  </body>
</html>
```

### 2. Melassa Layout (MelassaLayout.astro)

```astro
---
// src/layouts/MelassaLayout.astro
interface Props {
  title: string;
  description: string;
  image: string;
  businessName?: string;
  address?: string;
  phone?: string;
  hours?: {
    open: string;
    close: string;
    day: string;
  }[];
  includeLocalBusinessSchema?: boolean;
}

const { 
  title, 
  description, 
  image,
  businessName = "Melassa Coffee & Bake",
  address,
  phone,
  hours,
  includeLocalBusinessSchema = true
} = Astro.props;

const canonicalUrl = new URL(Astro.url.pathname, Astro.site);

// Schema.org LocalBusiness para SEO local
const localBusinessSchema = {
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": businessName,
  "image": image,
  "description": description,
  "telephone": phone,
  "address": {
    "@type": "PostalAddress",
    "streetAddress": address?.split(',')[0],
    "addressLocality": address?.split(',')[1]?.trim(),
  },
  "openingHoursSpecification": hours?.map(h => ({
    "@type": "OpeningHoursSpecification",
    "dayOfWeek": h.day,
    "opens": h.open,
    "closes": h.close
  })),
  "priceRange": "€€",
  "servesCuisine": "Bakery, Coffee",
  "url": canonicalUrl.toString(),
};
---

<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    
    <title>{title}</title>
    <meta name="description" content={description} />
    <link rel="canonical" href={canonicalUrl.toString()} />
    
    <!-- Open Graph -->
    <meta property="og:type" content="business.business" />
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:image" content={image} />
    <meta property="og:url" content={canonicalUrl.toString()} />
    <meta property="og:site_name" content={businessName} />
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content={title} />
    <meta name="twitter:description" content={description} />
    <meta name="twitter:image" content={image} />
    <meta name="twitter:creator" content="@melassa_bake" />
    
    <!-- Información de Negocio Local -->
    {phone && <meta name="telephone" content={phone} />}
    {address && <meta name="business-address" content={address} />}
    
    <!-- Schema.org JSON-LD -->
    {includeLocalBusinessSchema && (
      <script type="application/ld+json" set:html={JSON.stringify(localBusinessSchema)} />
    )}
  </head>
  
  <body class="bg-white text-gray-900">
    <slot />
  </body>
</html>
```

---

## Componentes Interactivos React/Preact

### 1. Product Carousel (ProductCarousel.jsx)

```jsx
// src/components/React/ProductCarousel.jsx
import { useState } from 'react';

export default function ProductCarousel({ products }) {
  const [currentIndex, setCurrentIndex] = useState(0);
  
  const nextSlide = () => {
    setCurrentIndex((prevIndex) => 
      prevIndex === products.length - 1 ? 0 : prevIndex + 1
    );
  };
  
  const prevSlide = () => {
    setCurrentIndex((prevIndex) => 
      prevIndex === 0 ? products.length - 1 : prevIndex - 1
    );
  };
  
  return (
    <div className="relative w-full max-w-4xl mx-auto">
      {/* Carousel Container */}
      <div className="relative overflow-hidden rounded-2xl shadow-2xl">
        <div 
          className="flex transition-transform duration-500 ease-out"
          style={{ transform: `translateX(-${currentIndex * 100}%)` }}
        >
          {products.map((product, index) => (
            <div key={index} className="min-w-full">
              <img 
                src={product.image} 
                alt={product.name}
                className="w-full h-96 object-cover"
              />
              <div className="absolute inset-0 flex flex-col justify-end bg-gradient-to-t from-black/60 to-transparent p-6">
                <h3 className="text-white font-heading text-3xl mb-2">
                  {product.name}
                </h3>
                <p className="text-white/90 text-lg">
                  {product.description}
                </p>
              </div>
            </div>
          ))}
        </div>
      </div>

      {/* Navigation Buttons */}
      <button 
        onClick={prevSlide}
        className="absolute left-4 top-1/2 transform -translate-y-1/2 bg-white/80 hover:bg-white text-melassa-blue rounded-full w-12 h-12 flex items-center justify-center transition z-10"
        aria-label="Anterior"
      >
        ←
      </button>
      
      <button 
        onClick={nextSlide}
        className="absolute right-4 top-1/2 transform -translate-y-1/2 bg-white/80 hover:bg-white text-melassa-blue rounded-full w-12 h-12 flex items-center justify-center transition z-10"
        aria-label="Siguiente"
      >
        →
      </button>

      {/* Dots Indicator */}
      <div className="flex justify-center gap-2 mt-4">
        {products.map((_, index) => (
          <button
            key={index}
            onClick={() => setCurrentIndex(index)}
            className={`w-3 h-3 rounded-full transition ${
              index === currentIndex 
                ? 'bg-melassa-blue' 
                : 'bg-gray-300 hover:bg-gray-400'
            }`}
            aria-label={`Ir a producto ${index + 1}`}
          />
        ))}
      </div>
    </div>
  );
}
```

### 2. Custom Cake Form (CustomCakeForm.jsx)

```jsx
// src/components/React/CustomCakeForm.jsx
import { useState } from 'react';

export default function CustomCakeForm() {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    phone: '',
    eventDate: '',
    servings: '10',
    flavor: 'chocolate',
    message: '',
  });

  const [submitted, setSubmitted] = useState(false);

  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData(prev => ({
      ...prev,
      [name]: value
    }));
  };

  const handleSubmit = async (e) => {
    e.preventDefault();
    
    // Aquí enviarías a tu servicio (Formspree, EmailJS, tu backend, etc.)
    console.log('Datos del formulario:', formData);
    
    // Simulación de envío
    setSubmitted(true);
    setTimeout(() => {
      setSubmitted(false);
      setFormData({
        name: '',
        email: '',
        phone: '',
        eventDate: '',
        servings: '10',
        flavor: 'chocolate',
        message: '',
      });
    }, 3000);
  };

  if (submitted) {
    return (
      <div className="bg-melassa-pink-light p-8 rounded-lg text-center">
        <h3 className="text-melassa-blue-dark text-2xl font-bold mb-2">
          ¡Solicitud Recibida! 🎉
        </h3>
        <p className="text-gray-700">
          Nos pondremos en contacto pronto para confirmar tu pedido de tarta personalizada.
        </p>
      </div>
    );
  }

  return (
    <form onSubmit={handleSubmit} className="space-y-6 bg-white p-8 rounded-lg shadow-lg">
      <div className="grid md:grid-cols-2 gap-6">
        {/* Nombre */}
        <div>
          <label htmlFor="name" className="block text-sm font-semibold text-gray-700 mb-2">
            Nombre completo *
          </label>
          <input
            type="text"
            id="name"
            name="name"
            value={formData.name}
            onChange={handleChange}
            required
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
            placeholder="Tu nombre"
          />
        </div>

        {/* Email */}
        <div>
          <label htmlFor="email" className="block text-sm font-semibold text-gray-700 mb-2">
            Email *
          </label>
          <input
            type="email"
            id="email"
            name="email"
            value={formData.email}
            onChange={handleChange}
            required
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
            placeholder="tu@email.com"
          />
        </div>

        {/* Teléfono */}
        <div>
          <label htmlFor="phone" className="block text-sm font-semibold text-gray-700 mb-2">
            Teléfono *
          </label>
          <input
            type="tel"
            id="phone"
            name="phone"
            value={formData.phone}
            onChange={handleChange}
            required
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
            placeholder="+34 91 234 5678"
          />
        </div>

        {/* Fecha del Evento */}
        <div>
          <label htmlFor="eventDate" className="block text-sm font-semibold text-gray-700 mb-2">
            Fecha del evento *
          </label>
          <input
            type="date"
            id="eventDate"
            name="eventDate"
            value={formData.eventDate}
            onChange={handleChange}
            required
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
          />
        </div>

        {/* Porciones */}
        <div>
          <label htmlFor="servings" className="block text-sm font-semibold text-gray-700 mb-2">
            Número de porciones
          </label>
          <select
            id="servings"
            name="servings"
            value={formData.servings}
            onChange={handleChange}
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
          >
            <option value="10">10 porciones</option>
            <option value="15">15 porciones</option>
            <option value="20">20 porciones</option>
            <option value="30">30 porciones</option>
            <option value="custom">Personalizado</option>
          </select>
        </div>

        {/* Sabor */}
        <div>
          <label htmlFor="flavor" className="block text-sm font-semibold text-gray-700 mb-2">
            Sabor principal
          </label>
          <select
            id="flavor"
            name="flavor"
            value={formData.flavor}
            onChange={handleChange}
            className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
          >
            <option value="chocolate">Chocolate</option>
            <option value="vainilla">Vainilla</option>
            <option value="fresa">Fresa</option>
            <option value="red-velvet">Red Velvet</option>
            <option value="otros">Otro (especificar en mensaje)</option>
          </select>
        </div>
      </div>

      {/* Mensaje */}
      <div>
        <label htmlFor="message" className="block text-sm font-semibold text-gray-700 mb-2">
          Detalles adicionales (diseño, alergias, etc.)
        </label>
        <textarea
          id="message"
          name="message"
          value={formData.message}
          onChange={handleChange}
          rows="4"
          className="w-full px-4 py-2 border-2 border-melassa-pink-light rounded-lg focus:outline-none focus:border-melassa-blue"
          placeholder="Cuéntanos todo sobre tu tarta ideal..."
        />
      </div>

      {/* Submit Button */}
      <button
        type="submit"
        className="w-full bg-melassa-blue text-white py-3 rounded-full font-bold text-lg hover:bg-melassa-blue-dark transition transform hover:scale-105"
      >
        Solicitar Cotización
      </button>
    </form>
  );
}
```

### 3. Gallery Lightbox (GalleryLightbox.jsx)

```jsx
// src/components/React/GalleryLightbox.jsx
import { useState } from 'react';

export default function GalleryLightbox({ images }) {
  const [selectedImage, setSelectedImage] = useState(null);
  const [selectedIndex, setSelectedIndex] = useState(0);

  const handleNextImage = () => {
    const nextIndex = (selectedIndex + 1) % images.length;
    setSelectedIndex(nextIndex);
    setSelectedImage(images[nextIndex].full);
  };

  const handlePrevImage = () => {
    const prevIndex = (selectedIndex - 1 + images.length) % images.length;
    setSelectedIndex(prevIndex);
    setSelectedImage(images[prevIndex].full);
  };

  return (
    <>
      {/* Gallery Grid */}
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
        {images.map((img, index) => (
          <div
            key={index}
            className="relative overflow-hidden rounded-lg cursor-pointer group"
            onClick={() => {
              setSelectedImage(img.full);
              setSelectedIndex(index);
            }}
          >
            <img 
              src={img.thumbnail}
              alt={img.alt}
              className="w-full h-64 object-cover group-hover:scale-110 transition duration-300"
            />
            <div className="absolute inset-0 bg-black/0 group-hover:bg-black/30 transition flex items-center justify-center">
              <span className="text-white text-4xl opacity-0 group-hover:opacity-100 transition">
                🔍
              </span>
            </div>
          </div>
        ))}
      </div>

      {/* Lightbox Modal */}
      {selectedImage && (
        <div 
          className="fixed inset-0 bg-black/90 flex items-center justify-center z-50 p-4"
          onClick={() => setSelectedImage(null)}
        >
          <div className="relative max-w-4xl w-full">
            <img 
              src={selectedImage} 
              alt="Galería" 
              className="w-full max-h-[80vh] object-contain"
              onClick={(e) => e.stopPropagation()}
            />

            {/* Navigation Buttons */}
            <button
              onClick={handlePrevImage}
              className="absolute left-0 top-1/2 transform -translate-y-1/2 -translate-x-16 bg-white/20 hover:bg-white/40 text-white rounded-full w-12 h-12 flex items-center justify-center transition"
              aria-label="Anterior"
            >
              ←
            </button>

            <button
              onClick={handleNextImage}
              className="absolute right-0 top-1/2 transform -translate-y-1/2 translate-x-16 bg-white/20 hover:bg-white/40 text-white rounded-full w-12 h-12 flex items-center justify-center transition"
              aria-label="Siguiente"
            >
              →
            </button>

            {/* Close Button */}
            <button
              onClick={() => setSelectedImage(null)}
              className="absolute top-4 right-4 bg-white/20 hover:bg-white/40 text-white rounded-full w-10 h-10 flex items-center justify-center transition text-2xl"
              aria-label="Cerrar"
            >
              ✕
            </button>

            {/* Image Counter */}
            <div className="absolute bottom-4 left-1/2 transform -translate-x-1/2 bg-black/50 text-white px-4 py-2 rounded-full text-sm">
              {selectedIndex + 1} / {images.length}
            </div>
          </div>
        </div>
      )}
    </>
  );
}
```

---

## Estilos con Tailwind CSS

### Configuración Tailwind (tailwind.config.mjs)

```javascript
// tailwind.config.mjs
export default {
  content: ['./src/**/*.{astro,html,js,jsx,md,mdx,svelte,ts,tsx,vue}'],
  theme: {
    extend: {
      colors: {
        'melassa-blue': '#00ADEF',
        'melassa-blue-dark': '#2D548B',
        'melassa-pink': '#FF69B4',
        'melassa-pink-light': '#FFB6D9',
      },
      fontFamily: {
        'heading': ['Playfair Display', 'serif'],
        'body': ['Inter', 'sans-serif'],
      },
      animation: {
        'fade-in': 'fadeIn 1s ease-out',
        'slide-up': 'slideUp 0.6s ease-out',
      },
      keyframes: {
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        },
        slideUp: {
          '0%': { transform: 'translateY(20px)', opacity: '0' },
          '100%': { transform: 'translateY(0)', opacity: '1' },
        },
      },
    },
  },
  plugins: [],
};
```

### Global Styles (global.css)

```css
/* src/styles/global.css */

@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

/* Custom Base Styles */
html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', sans-serif;
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Playfair Display', serif;
}

/* Accessibility */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* Utility Classes */
.container {
  max-width: 1200px;
}

.text-gradient {
  background: linear-gradient(135deg, #00ADEF, #FF69B4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## Contenido y Secciones

### Estructura de la Landing Page Index

```astro
---
// src/pages/index.astro
import MelassaLayout from '../layouts/MelassaLayout.astro';
import Header from '../components/Astro/Header.astro';
import Footer from '../components/Astro/Footer.astro';
import Hero from '../components/Astro/Hero.astro';
import ProductCard from '../components/Astro/ProductCard.astro';
import ContactInfo from '../components/Astro/ContactInfo.astro';

import ProductCarousel from '../components/React/ProductCarousel.jsx';
import CustomCakeForm from '../components/React/CustomCakeForm.jsx';
import GalleryLightbox from '../components/React/GalleryLightbox.jsx';

const SEO_DATA = {
  title: 'Melassa Coffee & Bake | Galletas Artesanales, Tartas & Café',
  description: 'Descubre nuestras galletas estilo Crumbl, rollitos de canela frescos, brownies de chocolate y tartas artesanales personalizadas en Madrid.',
  image: '/og-image.png',
  businessName: 'Melassa Coffee & Bake',
  address: 'Calle Principal 123, Madrid, España',
  phone: '+34 91 234 5678',
  hours: [
    { day: 'Monday', open: '08:00', close: '20:00' },
    { day: 'Tuesday', open: '08:00', close: '20:00' },
    { day: 'Wednesday', open: '08:00', close: '20:00' },
    { day: 'Thursday', open: '08:00', close: '20:00' },
    { day: 'Friday', open: '08:00', close: '21:00' },
    { day: 'Saturday', open: '09:00', close: '21:00' },
    { day: 'Sunday', open: '10:00', close: '19:00' },
  ],
  includeLocalBusinessSchema: true,
};

const FEATURED_PRODUCTS = [
  {
    name: 'Cookie Monster Special',
    description: 'Nuestra galleta insignia inspirada en Cookie Monster',
    image: '/images/products/cookies/monster-special.jpg',
    price: '€4.50',
    badge: 'Best Seller'
  },
  {
    name: 'Brownie Fudgy',
    description: 'Denso, húmedo y lleno de chocolate',
    image: '/images/products/brownies/fudgy.jpg',
    price: '€3.50'
  },
  {
    name: 'Rollito de Canela',
    description: 'Fresco, suave y perfumado',
    image: '/images/products/cinnamon-rolls/classic.jpg',
    price: '€2.95'
  },
];

const GALLERY_IMAGES = [
  {
    thumbnail: '/images/products/cakes/portfolio-1-thumb.jpg',
    full: '/images/products/cakes/portfolio-1-full.jpg',
    alt: 'Tarta de tres capas con ganache'
  },
  // Más imágenes...
];
---

<MelassaLayout {...SEO_DATA}>
  <Header />

  <!-- Hero Section -->
  <Hero 
    title="Las Galletas Más Irresistibles 🍪"
    subtitle="Estilo Crumbl, Rollitos de Canela, Brownies & Tartas Artesanales Personalizadas"
    image="/images/hero-cookie.jpg"
    ctaText="Descubre Nuestros Productos"
  />

  <!-- Sección de Productos Destacados -->
  <section id="productos" class="py-20 bg-white">
    <div class="container mx-auto px-4">
      <h2 class="font-heading text-5xl text-center text-melassa-blue-dark mb-16">
        Nuestros Productos Especiales
      </h2>
      
      <div class="grid md:grid-cols-3 gap-8 mb-20">
        {FEATURED_PRODUCTS.map(product => (
          <ProductCard {...product} />
        ))}
      </div>

      <!-- Product Carousel -->
      <h3 class="font-heading text-3xl text-melassa-blue-dark mb-8 text-center">
        Sabor de la Semana
      </h3>
      <ProductCarousel 
        products={[
          {
            name: 'Red Velvet Dream',
            description: 'Esta semana disfrutamos de nuestra exclusiva galleta Red Velvet con glaseado de queso crema',
            image: '/images/products/cookies/red-velvet-weekly.jpg'
          },
        ]}
        client:idle
      />
    </div>
  </section>

  <!-- Galería de Tartas Personalizadas -->
  <section class="py-20 bg-melassa-pink-light">
    <div class="container mx-auto px-4">
      <h2 class="font-heading text-5xl text-center text-melassa-blue-dark mb-16">
        Nuestras Creaciones Personalizadas
      </h2>
      
      <GalleryLightbox images={GALLERY_IMAGES} client:visible />
    </div>
  </section>

  <!-- Formulario de Tartas Personalizadas -->
  <section id="pedidos" class="py-20 bg-white">
    <div class="container mx-auto px-4 max-w-2xl">
      <h2 class="font-heading text-4xl text-center text-melassa-blue-dark mb-4">
        Pide Tu Tarta Personalizada
      </h2>
      <p class="text-center text-gray-600 mb-12">
        Completa el formulario y nos pondremos en contacto para crear tu tarta perfecta
      </p>
      
      <CustomCakeForm client:load />
    </div>
  </section>

  <!-- Información de Ubicación -->
  <section id="ubicacion" class="py-20 bg-melassa-blue text-white">
    <div class="container mx-auto px-4">
      <h2 class="font-heading text-5xl text-center mb-16">
        Visítanos
      </h2>
      
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div>
          <h3 class="font-heading text-3xl mb-6">Ubicación</h3>
          <p class="text-xl mb-8 text-melassa-pink-light">
            <strong>Melassa Coffee & Bake</strong><br/>
            Calle Principal 123<br/>
            28001 Madrid, España
          </p>

          <h3 class="font-heading text-3xl mb-6">Horarios</h3>
          <ul class="space-y-2 text-lg">
            <li>Lunes a Viernes: 8:00 - 20:00</li>
            <li>Sábados: 9:00 - 21:00</li>
            <li>Domingos: 10:00 - 19:00</li>
          </ul>
        </div>

        <div>
          <h3 class="font-heading text-3xl mb-6">Contacto</h3>
          <p class="text-xl mb-4">
            <strong>Teléfono:</strong> +34 91 234 5678
          </p>
          <p class="text-xl mb-8">
            <strong>Email:</strong> info@melassa.es
          </p>

          <h3 class="font-heading text-3xl mb-6">Síguenos</h3>
          <div class="flex gap-4">
            <a href="https://instagram.com" class="text-melassa-pink-light hover:text-melassa-pink text-2xl transition">
              📷
            </a>
            <a href="https://facebook.com" class="text-melassa-pink-light hover:text-melassa-pink text-2xl transition">
              f
            </a>
            <a href="https://twitter.com" class="text-melassa-pink-light hover:text-melassa-pink text-2xl transition">
              𝕏
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <Footer />
</MelassaLayout>
```

---

## Optimización y Deployment

### 1. Configuración de Astro (astro.config.mjs)

```javascript
// astro.config.mjs
import { defineConfig } from 'astro/config';
import react from '@astrojs/react';
import tailwind from '@astrojs/tailwind';

export default defineConfig({
  integrations: [react(), tailwind()],
  
  // Site URL para URLs canónicas
  site: 'https://melassa-coffee-bake.es',
  
  // Output estático por defecto
  output: 'static',
  
  // Optimizaciones de imagen
  image: {
    service: {
      entrypoint: 'astro/assets/services/sharp'
    }
  },
  
  // Vite config
  vite: {
    build: {
      minify: 'terser',
      sourcemap: false,
    }
  }
});
```

### 2. TypeScript Config (tsconfig.json)

```json
{
  "extends": "astro/tsconfigs/strict",
  "compilerOptions": {
    "jsxImportSource": "react"
  }
}
```

### 3. Package.json

```json
{
  "name": "melassa-landing",
  "type": "module",
  "version": "1.0.0",
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview",
    "astro": "astro"
  },
  "dependencies": {
    "astro": "^5.3.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@astrojs/react": "^3.0.0",
    "@astrojs/tailwind": "^5.1.0",
    "tailwindcss": "^3.4.0"
  }
}
```

### 4. Deployment en Netlify

#### Archivo netlify.toml

```toml
[build]
  command = "npm run build"
  publish = "dist"

[functions]
  directory = "netlify/functions"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200

[dev]
  command = "npm run dev"
  port = 3000
```

#### Pasos para Deploy

1. **Conectar repositorio GitHub a Netlify**
   - Ir a netlify.com → New site from Git
   - Seleccionar repositorio
   - Configurar build command: `npm run build`
   - Configurar publish directory: `dist`

2. **Variables de Entorno** (si es necesario)
   - Site settings → Build & deploy → Environment
   - Agregar variables si usas integraciones externas

3. **Dominio Personalizado**
   - Site settings → Domain management
   - Agregar tu dominio melassa-coffee-bake.es

### 5. Optimización de Performance

```bash
# Instalar dependencias
npm install

# Build optimizado
npm run build

# Preview antes de deploy
npm run preview
```

**Checklist de Performance:**
- [ ] Imágenes optimizadas (WebP format)
- [ ] Lazy loading activado
- [ ] CSS purged (Tailwind lo hace automáticamente)
- [ ] Minificación HTML/CSS/JS
- [ ] Service Worker (opcional, para PWA)

---

## Roadmap de Desarrollo

### Fase 1: MVP (Semana 1-2)

```
✅ Estructura Astro básica
✅ Header y Footer estaticos
✅ Hero section
✅ Grid de productos (4 main)
✅ Información de ubicación/horarios
✅ Links a redes sociales
✅ Meta tags básicos
✅ Deploy en Netlify
```

### Fase 2: Componentes Interactivos (Semana 3-4)

```
⏳ ProductCarousel React
⏳ CustomCakeForm con validación
⏳ GalleryLightbox
⏳ Ubicación en mapa (Google Maps)
⏳ Newsletter signup
⏳ Animaciones on-scroll
```

### Fase 3: Optimización & Marketing (Semana 5-6)

```
⏳ Schema.org JSON-LD completo
⏳ Google Analytics 4
⏳ Meta pixel Facebook
⏳ Sitemap.xml generado
⏳ Robots.txt
⏳ Velocidad PageSpeed 95+
⏳ Mobile testing
```

### Fase 4: Features Avanzados (Mes 2+)

```
⏳ Blog con recetas
⏳ Sistema de comentarios
⏳ Dark mode toggle
⏳ Chatbot/Contact live chat
⏳ Integración CMS (Sanity, Contentful)
⏳ e-commerce básico si aplica
⏳ Multi-idioma (ES/EN)
```

---

## Comandos Útiles

```bash
# Instalación inicial
npm create astro@latest melassa-landing -- --template minimal

# Agregar integraciones
npx astro add react
npx astro add tailwind

# Desarrollo local
npm run dev
# Accede a http://localhost:3000

# Build para producción
npm run build

# Preview del build
npm run preview

# Verificación de tipos
npx astro check

# Limpiar dist
rm -rf dist/
```

---

## Recursos y Referencias

### Documentación Oficial
- **Astro Docs:** https://docs.astro.build
- **Tailwind CSS:** https://tailwindcss.com/docs
- **React:** https://react.dev

### Herramientas Útiles
- **PageSpeed Insights:** https://pagespeed.web.dev
- **Schema.org Validator:** https://validator.schema.org
- **Netlify CLI:** https://docs.netlify.com/cli

### Inspiración
- **Bakery Websites 2025:** Buscar en Dribbble, Behance
- **Landing Page Patterns:** https://landingfolio.com
- **Color Psychology:** https://colormagic.app

---

## Próximos Pasos

1. **Crear repositorio Git**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Melassa Landing Page"
   ```

2. **Configurar GitHub**
   - Crear repo en github.com
   - Push local repo

3. **Conectar Netlify**
   - Autorizar GitHub
   - Seleccionar rama deploy
   - Configurar build settings

4. **Agregar Contenido Real**
   - Fotografías de productos profesionales
   - Textos y descripciones propios
   - Logo y favicon oficial

5. **Testing**
   - Testing en móvil/tablet/desktop
   - Testing en navegadores: Chrome, Firefox, Safari
   - Performance testing

---

## Notas Finales

Esta guía te proporciona una base sólida para crear una landing page profesional para **Melassa Coffee & Bake**. La arquitectura está diseñada para:

- ✨ **Performance extremo:** Astro genera HTML estático sin JavaScript innecesario
- 🎨 **Branding coherente:** Paleta azul/rosa de Cookie Monster bien integrada
- 📱 **Responsive:** Funciona perfectamente en todos los dispositivos
- 🔍 **SEO optimizado:** Meta tags, schema markup, URLs limpias
- ⚡ **Escalable:** Fácil agregar nuevas secciones o funcionalidad

¡Que disfrutes creando tu landing page!

---

**Última actualización:** Noviembre 2025  
**Versión:** 1.0
