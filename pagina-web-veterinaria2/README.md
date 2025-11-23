# Página Web Veterinaria

Página web pública y responsive para una veterinaria que centraliza toda la información y permite reservar citas mediante Google Calendar.

## 🚀 Características

- ✅ Diseño moderno y responsive (móvil, tablet, desktop)
- ✅ Secciones completas: Inicio, Servicios, Equipo, Testimonios, Galería, Blog, Contacto
- ✅ Formulario de contacto funcional
- ✅ Integración con Google Calendar para reservas
- ✅ Animaciones suaves y transiciones
- ✅ SEO básico optimizado
- ✅ Fácil personalización de colores

## 📁 Estructura del Proyecto

```
veterinaria-web/
│
├── index.html          # Página principal
├── css/
│   ├── style.css       # Estilos principales
│   └── responsive.css  # Media queries responsive
├── js/
│   └── main.js         # Funcionalidad JavaScript
├── images/             # Carpeta para imágenes (logo, galería, etc.)
└── README.md           # Este archivo
```

## 🛠️ Instalación y Uso

### Opción 1: GitHub Pages (Recomendado - Gratis)

1. Crea un repositorio en GitHub
2. Sube todos los archivos del proyecto
3. Ve a Settings > Pages
4. Selecciona la rama `main` y la carpeta `/root`
5. Tu sitio estará disponible en `https://tu-usuario.github.io/nombre-repo`

### Opción 2: Netlify (Gratis)

1. Ve a [netlify.com](https://www.netlify.com)
2. Arrastra la carpeta del proyecto o conéctala con GitHub
3. Tu sitio se desplegará automáticamente

### Opción 3: Vercel (Gratis)

1. Ve a [vercel.com](https://vercel.com)
2. Importa el proyecto desde GitHub o sube los archivos
3. Despliegue automático

### Opción 4: Servidor Local

Simplemente abre `index.html` en tu navegador o usa un servidor local:

```bash
# Con Python
python -m http.server 8000

# Con Node.js (http-server)
npx http-server
```

## ⚙️ Configuración

### 1. Integrar Google Calendar

En `index.html`, busca la sección "Reservar Cita" y reemplaza:

```html
<a href="TU_ENLACE_DE_GOOGLE_CALENDAR_AQUI" target="_blank" class="btn btn-primary btn-large">
```

Con el enlace de tu Google Calendar. Para obtenerlo:

1. Ve a tu Google Calendar
2. Crea un nuevo evento o usa uno existente
3. Copia el enlace de "Más opciones" > "Copiar enlace"
4. O usa el enlace público de tu calendario

**Alternativa con iframe:**
Si prefieres mostrar el calendario directamente en la página, puedes usar:

```html
<iframe src="TU_ENLACE_DE_GOOGLE_CALENDAR_EMBED" width="100%" height="600" frameborder="0"></iframe>
```

### 2. Configurar Formulario de Contacto

El formulario necesita un servicio para enviar emails. Opciones gratuitas:

#### Opción A: Formspree (Recomendado)

1. Ve a [formspree.io](https://formspree.io) y crea una cuenta gratuita
2. Crea un nuevo formulario
3. Copia el ID del formulario
4. En `js/main.js`, descomenta y configura:

```javascript
const response = await fetch('https://formspree.io/f/TU_ID_AQUI', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify(data)
});
```

#### Opción B: EmailJS

1. Ve a [emailjs.com](https://www.emailjs.com) y crea una cuenta
2. Configura un servicio de email y template
3. En `js/main.js`, agrega:

```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
```

Y en el código:

```javascript
emailjs.init('TU_PUBLIC_KEY');
emailjs.send('TU_SERVICE_ID', 'TU_TEMPLATE_ID', data)
    .then(() => { /* éxito */ })
    .catch(() => { /* error */ });
```

### 3. Personalizar Colores

En `css/style.css`, modifica las variables CSS al inicio del archivo:

```css
:root {
    --primary-color: #4CAF50;      /* Color principal (verde) */
    --secondary-color: #2196F3;    /* Color secundario (azul) */
    --accent-color: #FF9800;       /* Color de acento (naranja) */
    /* ... más variables */
}
```

### 4. Agregar Logo

1. Coloca tu logo en la carpeta `images/` como `logo.png`
2. El código ya está configurado para cargarlo automáticamente
3. Si no hay logo, se mostrará el texto "🐾 Veterinaria"

### 5. Agregar Imágenes

- **Galería**: Reemplaza los placeholders en la sección de galería
- **Equipo**: Agrega fotos del equipo en lugar de los emojis
- **Blog**: Agrega imágenes para los artículos

### 6. Personalizar Contenido

Edita `index.html` para actualizar:
- Información de contacto (dirección, teléfono, email, horarios)
- Descripción de servicios
- Información del equipo
- Testimonios
- Artículos del blog
- Enlaces de redes sociales

## 📱 Responsive Design

La página está optimizada para:
- 📱 Móviles (320px - 768px)
- 📱 Tablets (768px - 968px)
- 💻 Desktop (968px+)

## 🌐 SEO

La página incluye:
- Meta tags básicos
- Estructura semántica HTML5
- Títulos y descripciones optimizados

Para mejorar el SEO:
1. Agrega más contenido único
2. Optimiza las imágenes (alt text, compresión)
3. Agrega un sitemap.xml
4. Configura Google Analytics

## 🔧 Tecnologías Utilizadas

- HTML5
- CSS3 (Variables CSS, Flexbox, Grid)
- JavaScript (Vanilla)
- Google Fonts (Poppins)

## 📝 Notas Importantes

- **Formulario**: Actualmente usa una simulación. Debes configurar Formspree o EmailJS para que funcione.
- **Google Calendar**: Debes agregar tu enlace personalizado.
- **Imágenes**: Los placeholders deben ser reemplazados con imágenes reales.
- **Contenido**: Todo el contenido de ejemplo debe ser actualizado con información real.

## 🆘 Soporte

Si tienes problemas:
1. Verifica que todos los archivos estén en las carpetas correctas
2. Revisa la consola del navegador (F12) para errores
3. Asegúrate de que los servicios externos (Formspree/EmailJS) estén configurados

## 📄 Licencia

Este proyecto es de código abierto y está disponible para uso personal y comercial.

---

**¡Listo para usar!** Solo necesitas personalizar el contenido y configurar los servicios externos.

