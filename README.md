# Pájaro y Bestia — Website

Sitio web oficial de **Pájaro y Bestia** (`pajaroybestia.com`).

Sitio estático en HTML/CSS/JS. Se sube tal cual al hosting del cliente (cPanel / File Manager) — ver [HOW-TO-UPLOAD.txt](./HOW-TO-UPLOAD.txt).

## Cómo subir cambios futuros

El flujo normal es editar archivos localmente y volver a subir todo al hosting. **Siempre** se sube la carpeta completa, no archivos sueltos — para que los assets (CSS/JS) lleguen juntos al HTML.

### Opción 1 — Actualizar desde GitHub (recomendado para cambios grandes)

1. Editar los archivos en este repo (rama `main`).
2. Hacer **Download ZIP** desde la página del repo en GitHub.
3. En el hosting (cPanel → File Manager → `public_html/`):
   - Borrar el contenido viejo de `public_html/`.
   - Subir y descomprimir el ZIP nuevo en la raíz.
   - Confirmar que `assets/styles-XXXX.css` está dentro de `public_html/assets/`.
4. Verificar `https://pajaroybestia.com/` y limpiar caché (Ctrl + F5).

### Opción 2 — Editar un solo archivo (cambios chicos)

1. Editar el archivo (por ejemplo `index.html`) desde GitHub web o localmente.
2. En el hosting, sobreescribir **solo ese archivo** vía File Manager → Upload.
3. Verificar.

### Reglas que NO se rompen

- **El sitio vive en la raíz de `public_html/`**, no en un subfolder.
- **No borrar `assets/`** — sin esa carpeta el sitio se ve sin estilos.
- Si el `.htaccess` no aparece, renombrar `htaccess` → `.htaccess` después de subirlo (File Manager suele esconder archivos que empiezan con punto).
- HTTPS debe estar activo. Si no lo está, activarlo en cPanel → SSL/TLS Status.

## Estructura

```
/
├── index.html              ← landing
├── menu/index.html         ← menú
├── gallery/index.html      ← galería
├── visit/index.html        ← cómo llegar
├── smokers/index.html      ← smokers / catering
├── reheat/index.html       ← reheat (comida recalentada)
├── assets/                 ← CSS/JS bundleado (NO borrar)
├── images/                 ← fotos del restaurante
├── favicon.png / favicon.svg
├── og.jpg                  ← Open Graph (compartir en redes)
├── .htaccess               ← rewrites + cache headers
└── HOW-TO-UPLOAD.txt       ← instrucciones rápidas de upload
```

## Dominio y deploy

- **Producción**: <https://pajaroybestia.com>
- **Hosting**: cPanel del cliente
- **DNS**: gestionado por el cliente
- Mantenedor: **Wizard Systems**

## Stack

HTML5 estático + un bundle de JS/CSS por página (estilo Astro/Vite). Sin backend, sin base de datos. Idioma: español por defecto.

## Licencia

Código propietario de Wizard Systems Corp. Todos los derechos reservados.
