# Apex Advisory — Sitio Web de Consultoría

Página web estática para firma de consultoría financiera y estratégica.  
Lista para publicar en **GitHub Pages** sin ninguna dependencia externa (excepto fuentes de Google Fonts).

---

## 📁 Estructura de archivos

```
consultora-web/
├── index.html          ← Página principal
├── css/
│   └── style.css       ← Todos los estilos
├── js/
│   └── main.js         ← Animaciones, menú, formulario
└── README.md
```

---

## 🚀 Cómo publicar en GitHub Pages

### Paso 1 — Crear repositorio en GitHub
1. Ve a [github.com](https://github.com) e inicia sesión.
2. Haz clic en **"New repository"**.
3. Ponle un nombre (ej: `mi-consultora`).
4. Déjalo **público**.
5. Haz clic en **"Create repository"**.

### Paso 2 — Subir los archivos
**Opción A — Desde el navegador (más fácil):**
1. En tu nuevo repositorio, haz clic en **"uploading an existing file"**.
2. Arrastra toda la carpeta `consultora-web/` o sube los archivos uno a uno manteniendo la estructura de carpetas.
3. Haz clic en **"Commit changes"**.

**Opción B — Con Git (recomendado):**
```bash
cd consultora-web
git init
git add .
git commit -m "Primer commit — sitio web"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/mi-consultora.git
git push -u origin main
```

### Paso 3 — Activar GitHub Pages
1. En tu repositorio, ve a **Settings** → **Pages**.
2. En "Source", selecciona **Deploy from a branch**.
3. Selecciona la rama **main** y la carpeta **/ (root)**.
4. Haz clic en **Save**.
5. En unos minutos tu sitio estará en:  
   `https://TU_USUARIO.github.io/mi-consultora`

---

## ✏️ Cómo personalizar el contenido

### Cambiar el nombre de la firma
Busca `Apex Advisory` en `index.html` y reemplázalo con tu nombre.

### Cambiar información del equipo
Edita la sección `<!-- NOSOTROS -->` en `index.html`:
- Nombre, cargo y bio de cada persona en `.about__card-main` y `.about__card-secondary`.

### Cambiar colores
En `css/style.css`, edita las variables en `:root {}`:
```css
--black: #111110;      /* Color principal / botones */
--gray-50: #f7f6f4;    /* Fondo secciones alternas */
```

### Conectar el formulario de contacto
El formulario actualmente simula el envío. Para hacerlo funcional:

**Opción recomendada — [Formspree](https://formspree.io) (gratis):**
1. Regístrate en formspree.io.
2. Crea un nuevo formulario y copia tu endpoint (ej: `https://formspree.io/f/xyzabc`).
3. En `js/main.js`, reemplaza el bloque `setTimeout` con:
```javascript
const data = new FormData(form);
fetch('https://formspree.io/f/TU_ID', {
  method: 'POST',
  body: data,
  headers: { 'Accept': 'application/json' }
}).then(() => {
  form.style.display = 'none';
  formSuccess.classList.add('visible');
});
```

---

## 🎨 Fuentes utilizadas
- **Cormorant Garamond** — Títulos (serif elegante)
- **DM Sans** — Cuerpo de texto (sans-serif limpio)

Ambas cargadas desde Google Fonts, sin instalación necesaria.

---

## 📄 Licencia
Uso libre para tu proyecto personal o comercial.
