# Clase 11 | FyMW | SASS!

En esta clase comenzamos a aprender SASS.

- Slides: https://drive.google.com/file/d/14HOaSRhOBB7ekpaOgjE2g09elrfL83rO/view
- Grabación:
  https://drive.google.com/file/d/1QZ0kXigI3RGI94bqypUAA4q1hPowK-3H/view
- Extensiones VSCode:
  - **syler.sass-indented** (Sass) - Agrega soporte para la sintaxis SASS en
    VSCode.
  - **glenn2223.live-sass** (Live Sass Compiler) - Convierte archivos `.sass` o
    `.scss` a archivos `.css`.
  - **ritwickdey.liveserver** (Live Server) - Para poder servir el index.html
    desde nuestro localhost y ver el resultado en el browser.
- Herramientas online: https://www.sassmeister.com o
  https://jsonformatter.org/scss-to-css
- Sitio oficial y documentación: https://sass-lang.com

## Temas abarcados

- Archivos `.sass` versus archivos `.scss`.
- Formas de compilar sass a css plano usando vscode o herramientas online.
- Variables SASS.
- Anidación en SASS.

## Demo

Un demo simple que muestra el uso de variables y la forma de anidar
declaraciones de estilo (ver [estilos.scss](estilos.scss) y
[index.html](index.html)).

Para poder ver la demo es necesario usar las extensiones VSCode "Live Sass
Compiler" (glenn2223.live-sass) para compilar el archivo `estilos.scss` y luego
"Live Server" (ritwickdey.liveserver) para servir el archivo
[index.html](index.html) desde nuestro localhost.

> Notar que el archivo [index.html](index.html) necesita usar el archivo `.css`
> compilado y no el archivo fuente `.scss`
> (`<link rel="stylesheet" href="estilo.css" />`).
