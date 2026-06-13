# Guía de Contribución: Sube tu Proyecto a CPS Proyectos

¡Hola, Problem Solver! Esta guía detalla la estandarización técnica necesaria para incorporar la landing page de tu proyecto al escaparate (Showcase) central de **CPS Proyectos** (`cpsproyectos.com`). 

Seguir estas reglas garantiza que la plataforma se mantenga rápida, premium, segura y fácil de mantener para toda la comunidad.

---

## 1. Estructura de Carpetas

Cada proyecto debe alojarse en su propia subcarpeta dentro de la raíz del repositorio. El nombre de esta carpeta definirá la URL de tu landing page:

```text
cpsproyectos/             <-- Raíz del repositorio central
│
├── agro/                 <-- Subcarpeta del proyecto "Agricultura Resiliente IA"
│   └── index.html        <-- Punto de entrada principal
│
├── tu-proyecto/          <-- [NUEVO] Carpeta con el nombre de tu proyecto en minúsculas y guiones
│   ├── index.html        <-- [NUEVO] Punto de entrada principal (obligatorio)
│   └── assets/           <-- [OPCIONAL] Subcarpeta para CSS, JS o imágenes locales
│       ├── style.css
│       └── logo.png
│
├── index.html            <-- Home central del Showcase (debes añadir tu tarjeta aquí)
└── style.css             <-- Estilos de la Home central
```

---

## 2. Estándares Técnicos de la Landing Page

Para que tu proyecto sea aprobado e integrado, la landing page (`index.html`) de tu subcarpeta debe cumplir con los siguientes requisitos:

### A. Autocontenido y Rutas Relativas
* **Activos Locales:** Si creas archivos CSS, JS o imágenes locales dentro de tu subcarpeta, debes enlazarlos utilizando **rutas relativas** (p. ej., `href="assets/style.css"` o `src="logo.png"`).
* **NO usar rutas absolutas locales:** Evita enlazar activos usando barras diagonales iniciales (p. ej. `/assets/style.css`) ya que esto romperá el enlace cuando tu landing page se despliegue en un subdirectorio (como `cpsproyectos.com/tu-proyecto/`).
* **Empaquetado recomendado:** Si tu landing page es sencilla, te recomendamos incluir los estilos en un bloque `<style>` y los scripts en un bloque `<script>` dentro del mismo `index.html`. Esto facilita la carga y mantenimiento.

### B. Recursos Externos (CDNs y APIs)
* Se fomenta el uso de librerías o tipografías externas mediante CDNs (como *Google Fonts*, *FontAwesome*, *Chart.js*, etc.).
* Al usar enlaces externos, especifica siempre el protocolo seguro **`https://`** de forma explícita (p. ej., `https://cdnjs.cloudflare.com/ajax/libs/...`). Evita URLs relativas al protocolo como `//cdnjs.cloudflare.com/...` para prevenir problemas de contenido mixto.

### C. Diseño Premium y Responsivo
* La interfaz debe ser **completamente adaptativa** (responsiva) y verse impecable en móviles, tablets y ordenadores portátiles/de escritorio.
* Se recomienda mantener una identidad visual sofisticada y limpia. Evita colores planos chillones y tipografías predeterminadas del navegador. Utiliza fuentes modernas de Google Fonts (como *Inter*, *Outfit*, *Playfair Display*, etc.).
* **Sin placeholders rotos:** No utilices imágenes genéricas rotas o de prueba. Usa imágenes reales de alta calidad alojadas o servicios de stock libres de derechos (como Unsplash).

### D. SEO y Metadatos Básicos
Tu archivo `index.html` debe incluir en la cabecera (`<head>`) las siguientes etiquetas básicas para asegurar su indexación óptima:
```html
<title>Nombre de tu Proyecto — Eslogan corto y descriptivo</title>
<meta name="description" content="Descripción detallada de 1 o 2 líneas sobre el problema que resuelve tu proyecto y su enfoque técnico.">
```

---

## 3. Proceso para Añadir tu Tarjeta al Showcase

Una vez que tengas la landing page de tu proyecto lista en su respectiva subcarpeta, debes dar de alta tu tarjeta en la Home del Showcase (`index.html` en la raíz del repositorio):

1. Abre el archivo `index.html` de la raíz del proyecto.
2. Localiza la sección `<div class="projects-grid">`.
3. Duplica y añade un bloque `<article class="project-card">` estructurado de la siguiente forma:

```html
<article class="project-card">
  <!-- Imagen representativa en resolución óptima -->
  <div class="card-header-img" style="background-image: url('https://images.unsplash.com/... o ruta relativa');">
    <!-- Badge de estado: badge-featured (Insignia), badge-dev (En Desarrollo) o badge-soon (Próximamente) -->
    <span class="card-badge badge-dev">En Desarrollo</span>
  </div>
  <div class="card-content">
    <h3 class="card-title">Nombre de tu Proyecto</h3>
    <p class="card-description">
      Breve resumen (máximo 3 líneas) del problema real que resuelve la herramienta y su valor diferencial.
    </p>
    <!-- Tecnologías clave empleadas -->
    <div class="card-tech-stack">
      <span class="tech-tag">React</span>
      <span class="tech-tag">Python</span>
      <span class="tech-tag">IoT</span>
    </div>
    <!-- Botones de Acción -->
    <div class="card-footer">
      <!-- Enlace relativo a la subcarpeta de tu proyecto -->
      <a href="tu-proyecto/" class="card-btn card-btn-primary">
        Ver Demo <i class="fas fa-arrow-right"></i>
      </a>
      <!-- Enlace a tu repositorio oficial de GitHub -->
      <a href="https://github.com/domoprac/tu-proyecto" target="_blank" class="card-btn card-btn-secondary">
        <i class="fab fa-github"></i> Repositorio
      </a>
    </div>
  </div>
</article>
```

---

## 4. Flujo de Publicación (GitHub)

Para publicar tu proyecto en producción:

1. Haz un **Fork** del repositorio de la comunidad: `github.com/domoprac/cpsproyectos`.
2. Clona tu fork localmente y crea una rama de trabajo: `git checkout -b feature/nombre-proyecto`.
3. Añade tu carpeta de proyecto y realiza la modificación en el `index.html` de la raíz.
4. Confirma tus cambios (`git commit -am "feat: añade proyecto nombre-proyecto"`) y súbelos a tu fork.
5. Abre un **Pull Request (PR)** desde GitHub hacia la rama `main` del repositorio original de `domoprac/cpsproyectos`.
6. Una vez revisado y aprobado por los administradores de la comunidad, el pipeline de GitHub Actions se activará de forma automática y tu landing estará disponible en vivo en `cpsproyectos.com/tu-proyecto/` en cuestión de minutos.

¡Muchas gracias por contribuir y hacer crecer el ecosistema de CPS Proyectos!
