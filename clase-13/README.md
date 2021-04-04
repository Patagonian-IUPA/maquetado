# FyMW - Clase 13 - SASS Mixins

En esta clase:

1. Comenzamos a usar los "[mixins](https://sass-lang.com/guide#topic-6)" de
   SASS.
   - uso de parámetros
   - parámetros opcionales y valores por defecto para los mismos.
   - uso de bloques `@if`
   - uso de bloques `@content`
2. Vimos cómo usar
   [sass usando la linea de comandos](https://sass-lang.com/guide#topic-1) como
   un "pre-procesador" o compilador.

## Links

- Presentación:
  https://drive.google.com/file/d/1K1x0sU78RZn7b50OlA2Zf9vbubykOhoG/view
- Grabación:
  https://drive.google.com/file/d/1KiejwE1C4oAaSpvCIqJm17s9DYtZbjyd/view

## Ejemplos

### Mixin "transform"

Forma de declarar un mixin:

```scss
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}
```

Forma de uso de un mixin:

```scss
// usando el mixin `transform` sobre un elemento
// html que lleva la clase `.box`
.box {
  @include transform(rotate(30deg));
}
```

Resultado CSS después de compilar:

```css
.box {
  transform: rotate(30deg);
}
```

### Mixin "text"

Declaramos un mixin llamado "text" que hacepta 3 parámetros:

```scss
@mixin text($size, $lineHeight, $weight) {
  font-size: $size;
  line-height: $lineHeight;
  font-weight: $weight;
}
```

Uso del mixin "text":

```scss
.MyComponent {
  @include text(18px, 27px, 500);
}
```

Resultado después de compilar:

```scss
.MyComponent {
  font-size: 18px;
  line-height: 27px;
  font-weight: 500;
}
```

### Mixin "text" versión "flexible"

En este caso hacemos el mixin text más flexible haciendo que sus parámetros de
entrada sean optionales asignándoles un valor por defecto `null` para los casos
en que tal parámetro no se especifica y el uso del operador `@if` en el cuerpo
del mixin para decidir si incluir alguna propiedad o no:

```scss
@mixin text($size: null, $lineHeight: null, $weight: null) {
  @if $size != null {
    font-size: $size;
  }

  @if $lineHeight != null {
    line-height: $lineHeight;
  }

  @if $weight != null {
    font-weight: $weight;
  }
}
```

Uso del mixin text (versión flexible):

```scss
.MyComponent {
  &-title {
    @include text(16px, 19px, 600);
  }

  &-author {
    // aquí omitimos el parámetro `$lineHeight`
    // y usamos el nombre de los parámetros que
    // sí queremos pasar
    @include text($weight: 800, $size: 12px);
  }
}
```

Resultado CSS luego de compilar

```css
.MyComponent-title {
  font-size: 16px;
  line-height: 19px;
  font-weight: 600;
}

.MyComponent-author {
  font-size: 12px;
  font-weight: 800;
}
```

## El mixin min-width

En este ejemplo creamos un mixin llamado "min-width" para encapsular el uso de
media queries. En este caso el mixin no solo acepta parámetros sino que también
acepta contenido (ver uso más abajo).

Usamos el operado `@content` para señalar el lugar en donde se ubicará el
contenido de que le pasemos al mixin.

```scss
@mixin min-width($threshold) {
  @media screen and (min-width: $threshold) {
    @content;
  }
}
```

Ejemplo de uso del mixin "min-width":

```scss
.MyComponent {
  display: block; // mobile usara display block
  @include min-width(768px) {
    display: flex; // tablets usara display flex
  }
}
```

Resultado CSS después de compilar:

```css
.MyComponent {
  display: block;
}

@media screen and (min-width: 768px) {
  .MyComponent {
    display: flex;
  }
}
```

### Ejercicio:

Tomando como base el ejemplo sobre media queries visto en la
[clase 10](../clase-10/index.html)

1. Extraer el css que se encuentra en el archivo
   [index.html](../clase-10/index.html) pasarlo a un archivo `.scss`.
2. Incluir la versión css en una etiqueta `<link>` en el head del html.
3. Usar el mixin `min-width` para alterar el estilo de la clase `.container`
   según el tamaño del viewport, en vez de declarar multiples media queries como
   lo hace el ejemplo (el resultado visual debe ser el mismo).
