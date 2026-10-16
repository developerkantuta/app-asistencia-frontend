# Guía de Despliegue del Frontend en GitHub Pages

Esta guía explica cómo subir los archivos estáticos del frontend (HTML, CSS, JS) a GitHub Pages para que sean accesibles desde cualquier navegador.

## Requisitos previos
- Tener una cuenta en [GitHub](https://github.com).
- Tener instalado [Git](https://git-scm.com/) en la computadora.
- Tener los archivos del frontend listos (por ejemplo: `index.html`, `admin.html`, `dashboard.html`, `bootstrap.css`).

## Paso 1: Preparar la carpeta local
1. Abre la carpeta `frontend` en tu editor de código (VS Code, por ejemplo).
2. Abre una terminal dentro de esa carpeta.

## Paso 2: Inicializar el repositorio Git
Ejecuta los siguientes comandos uno por uno en la terminal:

git init
git add .
git commit -m "Primer commit del frontend"
git branch -M main

## Paso 3: Crear el repositorio en GitHub
1. Ve a [github.com/new](https://github.com/new).
2. Escribe un nombre para el repositorio (ej: `mi-proyecto-frontend`).
3. Déjalo como **Público** (obligatorio para GitHub Pages gratuito).
4. **NO** marques las casillas de "Add a README", ".gitignore" o "License".
5. Haz clic en **Create repository**.
6. Copia la URL que aparece (ej: `https://github.com/TuUsuario/mi-proyecto-frontend.git`).

## Paso 4: Conectar y subir los archivos
En la terminal, ejecuta:

git remote add origin https://github.com/TuUsuario/mi-proyecto-frontend.git
git push -u origin main

*Nota: Si te pide contraseña, debes usar un **Token de Acceso Personal** (PAT) de GitHub, no tu contraseña normal. Para crearlo: Settings > Developer settings > Personal access tokens > Tokens (classic) > Generate new token (classic). Marca la casilla `repo` y copia el token generado.*

## Paso 5: Activar GitHub Pages
1. Ve a tu repositorio en GitHub.
2. Haz clic en **Settings** (Configuración).
3. En el menú lateral izquierdo, busca y haz clic en **Pages**.
4. En **Source**, selecciona **Deploy from a branch**.
5. En **Branch**, selecciona **`main`** y la carpeta **`/(root)`**.
6. Haz clic en **Save**.
7. Espera 1 o 2 minutos. GitHub te mostrará un mensaje con la URL de tu sitio (ej: `https://TuUsuario.github.io/mi-proyecto-frontend/`).

## Paso 6: Verificar y actualizar
- Abre la URL en tu navegador. Deberías ver tu `index.html`.
- Si haces cambios en el futuro, solo debes ejecutar:

git add .
git commit -m "Descripción del cambio"
git push

- GitHub Pages se actualizará automáticamente en 1 o 2 minutos.

## ⚠️ Importante: Conexión con el Backend
Para que el frontend funcione correctamente (login, registro de asistencia, etc.), las URLs dentro de los archivos HTML deben apuntar a la dirección de tu backend en la nube (por ejemplo: `https://tu-backend.azurewebsites.net` o `https://tu-backend.onrender.com`), **no** a `localhost`.

Si el backend está en un servidor con HTTPS, no habrá problemas de seguridad. Si está en HTTP, el navegador bloqueará las peticiones.
