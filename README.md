# gael-web

Repositorio oficial de la web del libro **Gael**, de **Arruda Van der Ley**.

> Una historia profunda y conmovedora sobre la identidad, el poder de los vínculos y la valentía que requiere ser tierno en un mundo envenenado por la ignorancia.

**Web en vivo:** https://arrudavanderley.com

---

### Sobre el libro

Gael es una novela de aventura introspectiva, realismo mágico y fantasía. Un joven condenado al olvido inicia una búsqueda a través de reinos donde la mentira brilla y el silencio es una sinfonía, para redescubrir quién es.

### Sobre este repositorio

Este repo contiene el código fuente de la web oficial. Es una web editorial, clara, accesible y centrada por completo en la lectura. La página principal presenta la sinopsis, un fragmento, reseñas, información sobre el autor y los enlaces de compra, y se apoya en páginas secundarias que amplían el universo y la transparencia del proyecto.

### Páginas del sitio

- **`index.html`** — Página principal. Sinopsis, primeras páginas, reseñas, sobre el autor y compra.
- **`universogael.html`** — Expansión del universo de Gael. Contexto, conceptos y material complementario de la historia.
- **`aventurasintrospectivas.html`** — Espacio temático sobre la aventura introspectiva que propone el libro.
- **`accesibilidad.html`** — Declaración de accesibilidad. Principios y medidas aplicadas para una navegación inclusiva.
- **`contacto.html`** — Canal de contacto directo con el autor.
- **`robot-literario.html`** — Recurso / experimento literario vinculado al proyecto.

Todas estas páginas están incluidas en el `sitemap.xml` y comparten la misma identidad visual y criterios de accesibilidad.

### Características

- Contenido editorial completo y organizado por secciones
- Soporte trilingüe ES / EN / PT con selector persistente
- Accesibilidad cuidada: navegación por teclado, enlaces de salto, contraste, respeto a `prefers-reduced-motion`
- Optimizada para SEO y para compartir: meta tags, Open Graph, `sitemap.xml`, `robots.txt` y URL canónica
- Performance ligera: sin frameworks, sin dependencias, sin paso de compilación

### Tecnologías

- HTML5 semántico
- CSS3 con variables y diseño responsive
- JavaScript vanilla para interacciones mínimas (animaciones de entrada, progreso de lectura y cambio de idioma)
- GitHub Pages para hosting
- Dominio personalizado configurado vía `CNAME`

### Estructura del proyecto

```
/
├── index.html                      # Principal
├── universogael.html               # Universo expandido
├── aventurasintrospectivas.html     # Temática introspectiva
├── accesibilidad.html              # Accesibilidad
├── contacto.html                   # Contacto
├── robot-literario.html            # Recurso literario
├── favicon.png / og-image.jpg      # Identidad y preview
├── CNAME / robots.txt / sitemap.xml
└── .github/workflows/              # Automatizaciones
```

### Uso local

No necesitas instalar nada:

```bash
git clone https://github.com/arrudavanderley/gael-web.git
cd gael-web
```

Abre `index.html` en tu navegador. Si prefieres un servidor:

```bash
npx serve .
# o
python -m http.server 8000
```

### Despliegue

Despliegue automático con GitHub Pages desde la rama `main`. Cada push actualiza:

- https://arrudavanderley.com
- https://arrudavanderley.github.io/gael-web

### Autor

**Arruda Van der Ley** (Brasil, 1990) — educador social y escritor. Gael es su primera novela publicada.

- Amazon Author: https://amazon.com/author/arrudavanderley
- Threads: @authorarrudavanderley
- Web: https://arrudavanderley.com
- ISNI: 0000 0005 3060 7185

### Contacto y licencia

Este proyecto usa licencia dual, coherente con el universo de Gael:

- **Código (HTML/CSS/JS):** MIT License — puedes reutilizar la estructura citando el origen.
- **Contenido literario y visual:** © Arruda Van der Ley. Todos los derechos reservados. Textos, fragmentos, portada, fotos y universo expandido no pueden ser reutilizados sin permiso.

Ver archivo `LICENSE` para el texto legal completo.

---
Gracias por visitar el universo de Gael.
