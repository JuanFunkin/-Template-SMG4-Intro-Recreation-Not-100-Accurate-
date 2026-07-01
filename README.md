# Generador de Intro estilo SMG4

Web de una sola página (`index.html`) que genera una intro animada tipo SMG4:
personajes que hacen pop-in y orbitan, logo final con anillos de choque, tu
propia música, y exportación a vídeo (MP4 nativo cuando el navegador lo
soporta, o WEBM sin necesidad de internet como respaldo).

Todo corre en el navegador del visitante: no hay backend, no hay que subir
nada a ningún servidor, no se guarda ni se sube ninguna imagen/audio del
usuario a ningún sitio.

## Publicarla en GitHub Pages

1. Crea un repositorio nuevo en GitHub (puede ser público o, si tienes
   GitHub Pro/Team/Enterprise, también privado).
2. Sube estos archivos a la raíz del repositorio (o a una carpeta `/docs` si
   prefieres esa opción; ver paso 4):
   - `index.html`
   - `.nojekyll`
   - `README.md` (opcional, solo informativo)
3. Entra en **Settings → Pages** del repositorio.
4. En "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: `main` (o la rama donde subiste los archivos) y carpeta `/ (root)`
     — o `/docs` si pusiste ahí los archivos.
5. Guarda. GitHub te dará una URL parecida a:
   `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`
   Tarda entre 30 segundos y un par de minutos en activarse la primera vez.

### Alternativa por línea de comandos (git)

```bash
git init
git add index.html .nojekyll README.md
git commit -m "Intro maker estilo SMG4"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
git push -u origin main
```

Luego repite el paso 3-4 de arriba en la web de GitHub.

## Notas

- El archivo `.nojekyll` evita que GitHub Pages procese el sitio con Jekyll
  (no lo necesitamos y evita conflictos con el código JavaScript).
- No hace falta ningún paso de "build": es HTML/CSS/JS puro en un solo
  archivo, listo para servirse tal cual.
- La conversión a MP4 (cuando el navegador no puede grabar MP4 nativo) carga
  una librería externa (ffmpeg.wasm) desde un CDN la primera vez que se usa;
  todo lo demás — subir imágenes, previsualizar, reproducir, grabar en WEBM —
  funciona sin conexión una vez cargada la página.
