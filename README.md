# MindFlow — Landing Page

Landing page oficial de **MindFlow**, un diario de estado de ánimo con IA pensado para estudiantes y jóvenes profesionales. Ayuda a detectar patrones de estrés, sugerir intervenciones (respiración/meditación) y exportar reportes para uso clínico.

**Demo en vivo:** https://1asi0730-2610-20177-cognitech-mindflow.github.io/MindFlow-Landing-Page/
**App:** https://mindflow-frontend-cognitech-mindflow.vercel.app/

## Stack

HTML + CSS + JavaScript vanilla, sin frameworks ni build step. El sitio se sirve tal cual desde GitHub Pages.

## Estructura

```
index.html                  # Página principal (hero, problema, features, pricing, equipo, CTA)
assets/
  styles.css                 # Estilos del sitio
  script.js                  # i18n, scroll suave, menú móvil, animaciones
  i18n/
    en.json                  # Textos en inglés (idioma por defecto)
    es.json                  # Textos en español
  images/                     # Logo y fotos del equipo
  legal/
    privacy.html              # Política de privacidad
    terms.html                 # Términos y condiciones
    cookies.html                # Política de cookies
```

## Internacionalización (i18n)

Todo el texto visible se resuelve en tiempo de carga a partir de `assets/i18n/{en,es}.json` mediante atributos `data-i18n`, `data-i18n-attr` y `data-i18n-list` en el HTML (ver `assets/script.js`). El idioma se guarda en `localStorage` (`mindflow-locale`) y el botón de la navbar alterna entre EN/ES.

Para editar un texto: buscar la clave (p. ej. `hero.description`) en ambos archivos JSON y actualizar el valor — no hace falta tocar el HTML.

⚠️ `getI18nBasePath()` en `script.js` asume la ruta base `/MindFlow-Landing-Page/`, propia de GitHub Pages. Si se sirve el sitio desde otra ruta (dominio propio, otro subpath), hay que ajustar esa función.

## Desarrollo local

No requiere instalación de dependencias. Basta con abrir `index.html` en el navegador o servirlo con cualquier servidor estático, por ejemplo:

```bash
npx serve .
# o
python -m http.server 8080
```

(Usar un servidor evita problemas de CORS al hacer `fetch` de los archivos de `assets/i18n/`.)

## Despliegue

El sitio se publica con GitHub Pages desde este mismo repositorio.

## Equipo

| Nombre | Rol |
|---|---|
| Camila Cabrera | Product & UX |
| Becker Caisahuana | Backend Engineering |
| Sebastian Diaz | AI & Data |
| Jean Jauregui | Frontend Engineering |
| Angel Rocca | Quality & DevOps |
