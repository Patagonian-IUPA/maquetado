# Clase 12 FyMW

En esta clase exploramos algunas posibles soluciones al punto 12 del trabajo
práctico 2. Vimos que no podemos usar ni la propiedad css `display: inline` ni
`display: block` aunque sí es posible hacerlo utilizando `display: inline-block`
o `float: left` y finalmente la mejor solución de todas utilizando
`display: flex` y algunas otras propiedades flex.

- Slides: https://drive.google.com/file/d/1oqR6g37v2298kQlDPssWWekvifkiQSGQ/view
- Video: https://drive.google.com/file/d/1H0xb0ye9uslb47lVpqwQvqnkfGQZ5-qA/view

## Consigna 12 Trabajo Práctico #2

12. Con una nueva regla, declarar que todos los elementos `<article>` que son
    hijos del elemento cuyo clase es "posts":

    - que tengan un padding horizontal con un valor del 1% del ancho del
      viewport
    - que se comporten de manera "inline" entre sí.
    - ocupen la mitad del espacio horizontal disponible

## Demos

Los ejemplos están hechos en sass, por lo que para poder visualizarlos hay que
usar las mismas extensiones para VSCode mencionadas en el
[README de la clase 11](../clase-11/README.md) y siguiendo los mismos pasos.

1. [solucion-inline.scss](solucion-inline.scss) /
   [solucion-inline.html](solucion-inline.html): este enfoque no soluciona el
   problema (ver comentarios en [solucion-inline.scss](solucion-inline.scss))
2. [solucion-block.scss](solucion-block.scss) /
   [solucion-block.html](solucion-block.html): este enfoque tampoco soluciona el
   problema (ver comentarios en [solucion-block.scss](solucion-block.scss))
3. [solucion-inline-block.scss](solucion-inline-block.scss) /
   [solucion-inline-block.html](solucion-inline-block.html): este enfoque
   soluciona el problema solo parcialmente (ver comentarios en
   [solucion-inline-block.scss](solucion-inline-block.scss))
4. [solucion-float.scss](solucion-float.scss) /
   [solucion-float.html](solucion-float.html): este enfoque soluciona el
   problema pero viene con trampa (ver comentarios en
   [solucion-float.scss](solucion-float.scss))
5. [solucion-flex.scss](solucion-flex.scss) /
   [solucion-flex.html](solucion-flex.html): este enfoque soluciona el por
   completo y es la manera recomendada (ver comentarios en
   [solucion-flex.scss](solucion-flex.scss))
