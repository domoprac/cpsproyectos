# CPS Proyectos — Showcase y Lanzadera de la Comunidad

Bienvenido al repositorio central de **CPS Proyectos** (`cpsproyectos.com`), la plataforma lanzadera y escaparate para los desarrollos tecnológicos creados por la comunidad de graduados del **Máster en Problem Solving (CPS)**.

Este sitio web estático recopila iniciativas de software, hardware, IA predictiva y automatización desarrolladas de forma colaborativa bajo la organización de GitHub `domoprac`.

---

## 🚀 Estructura del Repositorio

El repositorio está estructurado de manera modular para permitir que cada desarrollador o equipo aloje su proyecto de forma estática en subcarpetas autónomas:

* **`/index.html`**: Página de inicio del escaparate central. Grid responsivo y premium de proyectos activos.
* **`/style.css`**: Hoja de estilos con diseño premium, tipografías personalizadas (`Outfit` + `Playfair Display`) y variables de color en tonos oscuros, rojo vino y dorado cálido.
* **`/agro/`**: Subcarpeta con la landing page y el simulador interactivo de **Agricultura Resiliente IA** (el proyecto insignia inicial de la plataforma).
* **`/docs/`**: Documentación técnica. Contiene la guía de estandarización [contribucion.md](docs/contribucion.md).
* **`/.github/workflows/`**: Pipeline de CI/CD para automatización del despliegue en **GitHub Pages**.

---

## 🛠️ ¿Cómo subir tu proyecto?

Cualquier miembro de la comunidad CPS puede añadir la landing page de su proyecto al escaparate principal. Los pasos generales son:

1. Haz un **Fork** de este repositorio.
2. Crea una carpeta para tu proyecto (p. ej. `cpsproyectos/tu-proyecto/`) y coloca allí tu landing page (`index.html`) con rutas de activos relativas.
3. Edita la Home del repositorio (`index.html` en la raíz) para añadir tu tarjeta interactiva en el grid de Showcase.
4. Sube tus cambios y abre un **Pull Request (PR)** hacia la rama `main` de este repositorio.

> 📘 **Guía Detallada:** Para conocer las especificaciones técnicas completas sobre CDNs, rutas relativas y metadatos SEO, lee la [Guía de Contribución](docs/contribucion.md).

---

## 🌐 Despliegue Continuo (CI/CD)

Este proyecto está integrado con **GitHub Actions** (`.github/workflows/deploy.yml`). Cualquier cambio aprobado y fusionado en la rama `main` se desplegará de forma automática en los servidores de **GitHub Pages**, actualizando en vivo tanto la Home como los subdirectorios de cada proyecto (p. ej., `cpsproyectos.com/tu-proyecto/`).
