# Guía SEO para el Sitio Hugo

## Funcionalidades SEO Implementadas

### 1. Meta Tags Básicos
- **Title**: Título dinámico basado en la página actual
- **Description**: Descripción específica por página o global
- **Author**: Autor del sitio
- **Keywords**: Palabras clave específicas por página
- **Robots**: Configuración para indexación
- **Canonical**: URLs canónicas

### 2. Open Graph Meta Tags
- **og:title**: Título para redes sociales
- **og:description**: Descripción para redes sociales
- **og:type**: Tipo de contenido (website/article)
- **og:url**: URL canónica
- **og:site_name**: Nombre del sitio
- **og:locale**: Idioma del contenido
- **og:image**: Imagen para redes sociales (1200x630px recomendado)

### 3. Twitter Card Meta Tags
- **twitter:card**: Tipo de tarjeta (summary_large_image)
- **twitter:title**: Título para Twitter
- **twitter:description**: Descripción para Twitter
- **twitter:image**: Imagen para Twitter
- **twitter:creator**: Usuario de Twitter del autor

### 4. Artículo Meta Tags (para posts)
- **article:published_time**: Fecha de publicación
- **article:modified_time**: Fecha de última modificación
- **article:author**: Autor del artículo
- **article:section**: Sección del artículo
- **article:tag**: Etiquetas del artículo

### 5. Otros Elementos SEO
- **Favicon**: Iconos para diferentes dispositivos
- **Web Manifest**: Para PWA
- **RSS Feeds**: Para suscripciones
- **Sitemap XML**: Para indexación
- **Robots.txt**: Para crawlers

## Cómo Usar

### 1. Configuración Global (hugo.toml)
```toml
[params]
  description = "Descripción global del sitio"
  author = "Tu Nombre"
  keywords = ["palabra1", "palabra2"]
  og_image = "/images/og-image.jpg"
  twitter_creator = "@tunombre"
```

### 2. Configuración por Idioma
```toml
[languages.es.params]
  description = "Descripción en español"
  keywords = ["palabra1", "palabra2", "español"]

[languages.en.params]
  description = "Description in English"
  keywords = ["word1", "word2", "english"]
```

### 3. Configuración por Página/Post
```yaml
---
title: "Título de la página"
description: "Descripción específica de esta página"
keywords: ["palabra1", "palabra2"]
author: "Autor específico"
image: "/images/imagen-especifica.jpg"
tags: ["tag1", "tag2"]
---
```

## Imágenes Recomendadas

### Open Graph Images
- **Tamaño**: 1200x630 píxeles
- **Formato**: JPG o PNG
- **Ubicación**: `/static/images/`
- **Nombres sugeridos**: 
  - `og-image.jpg` (imagen global)
  - `home-es.jpg` (inicio español)
  - `home-en.jpg` (inicio inglés)
  - `post-title.jpg` (posts específicos)

### Favicon
- **favicon.ico**: 16x16, 32x32 píxeles
- **apple-touch-icon.png**: 180x180 píxeles
- **favicon-32x32.png**: 32x32 píxeles
- **favicon-16x16.png**: 16x16 píxeles

## Verificación SEO

### 1. Herramientas de Verificación
- **Google Search Console**: Para monitoreo de indexación
- **Facebook Sharing Debugger**: Para verificar Open Graph
- **Twitter Card Validator**: Para verificar Twitter Cards
- **Google PageSpeed Insights**: Para rendimiento

### 2. Comandos de Verificación
```bash
# Verificar meta tags
curl -s http://localhost:1314/ | grep -A 5 -B 5 "meta name=\"description\""

# Verificar Open Graph
curl -s http://localhost:1314/ | grep -A 5 -B 5 "og:"

# Verificar sitemap
curl -s http://localhost:1314/sitemap.xml | head -10
```

## Mejores Prácticas

1. **Descripciones únicas**: Cada página debe tener una descripción única
2. **Títulos descriptivos**: Usar títulos que describan el contenido
3. **Imágenes optimizadas**: Usar imágenes de alta calidad para Open Graph
4. **URLs amigables**: Mantener URLs limpias y descriptivas
5. **Contenido multilingüe**: Asegurar que cada idioma tenga su propio contenido SEO
6. **Actualización regular**: Mantener el contenido actualizado
7. **Velocidad de carga**: Optimizar imágenes y recursos

## Notas Importantes

- Las imágenes referenciadas en los meta tags deben existir en `/static/images/`
- Los parámetros SEO se pueden sobrescribir en cada página individual
- El sitemap se genera automáticamente para cada idioma
- Los feeds RSS están disponibles en `/index.xml` para cada idioma
