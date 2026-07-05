# FLUXWEB

Sitio web de FLUXWEB construido con **Vite + React + TypeScript + Tailwind CSS 4**.

## 🚀 Desarrollo local

```bash
npm install
npm run dev      # servidor de desarrollo en http://localhost:5173
```

## 📦 Build de producción

```bash
npm run build    # genera la carpeta dist/
npm run preview  # previsualiza el build localmente
```

## 🌐 Deploy en Netlify

La configuración se hace **desde el dashboard de Netlify** (los archivos `public/_redirects` y `public/_headers` ya están en el repo para fallback SPA y headers de seguridad).

### 1. Subir a GitHub

Si aún no creaste el repo remoto:

```bash
git remote add origin https://github.com/TU-USUARIO/fluxweb.git
git branch -M main
git push -u origin main
```

### 2. Conectar con Netlify

1. Entrá a [https://app.netlify.com](https://app.netlify.com) e iniciá sesión.
2. Click en **"Add new site" → "Import an existing project"**.
3. Elegí **GitHub** como proveedor y autorizá el acceso.
4. Seleccioná el repositorio `fluxweb`.
5. En **Build settings** configurar manualmente:
   - **Base directory:** *(dejar vacío — el proyecto está en la raíz del repo)*
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
   - **Environment variables** → agregar `NODE_VERSION` = `20`
6. Click en **"Deploy site"**.

> ⚠️ **Importante:** no uses un `netlify.toml` propio para este proyecto. Netlify valida el TOML
> *antes* de correr el build y suele fallar con errores tipo "Base directory does not exist"
> cuando el `publish = "dist"` aún no fue generado. La config desde la UI evita ese problema.

### 3. Deploys automáticos

Cada `git push` a la rama `main` va a disparar un nuevo deploy automáticamente.

## ⚙️ Variables de entorno

Si necesitás variables de entorno (por ejemplo claves de API), configuralas en:
**Netlify Dashboard → Site settings → Environment variables**

## 📁 Estructura

```
fluxweb/
├── public/           # assets estáticos servidos tal cual
├── src/              # código fuente (componentes, páginas, etc.)
├── index.html        # HTML raíz
├── netlify.toml      # configuración de Netlify
├── vite.config.ts    # configuración de Vite
├── tailwind.config.js
└── package.json
```
