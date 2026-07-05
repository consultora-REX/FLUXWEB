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

El proyecto ya está configurado para Netlify (`netlify.toml`). Pasos para desplegar:

### 1. Subir a GitHub

Si aún no creaste el repo remoto:

```bash
# Crea un repo vacío en https://github.com/new (no inicialices con README)
git remote add origin https://github.com/TU-USUARIO/fluxweb.git
git branch -M main            # Netlify trabaja mejor con main; si prefieres master, déjalo así
git push -u origin main
```

> **Nota:** si tu rama es `master` y querés que Netlify la use, podés cambiarlo en la config del sitio en Netlify (Build settings → Branch to deploy).

### 2. Conectar con Netlify

1. Entrá a [https://app.netlify.com](https://app.netlify.com) e iniciá sesión.
2. Click en **"Add new site" → "Import an existing project"**.
3. Elegí **GitHub** como proveedor y autorizá el acceso.
4. Seleccioná el repositorio `fluxweb`.
5. Netlify detecta automáticamente la configuración desde `netlify.toml`:
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
   - **Node version:** 20+ (recomendado, agregala en `netlify.toml` si hace falta)
6. Click en **"Deploy site"**.

### 3. Deploys automáticos

Cada `git push` a la rama principal va a disparar un nuevo deploy automáticamente.

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
