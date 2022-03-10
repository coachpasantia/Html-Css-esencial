# CSS esencial

## Conceptos basicos
![img](https://mdn.mozillademos.org/files/11925/csspartes.png)
- Selector
    El elemento HTML en el que comienza la regla.
- Declaración
    Especifica a cuál de las propiedades del elemento quieres dar estilo.
- Propiedades
    Maneras en las cuales puedes dar estilo a un elemento HTML.
- Valor de la propiedad
    Después de los dos puntos (:), tienes el valor de la propiedad, para elegir una de las muchas posibles apariencias para una propiedad determinada.

### Tipos de selectores
- Selector universal:
    ```css
    *{
        /*- Declaracion -*/
    }
    ```
- Selector de tipo(tag): 

    Este grupo incluye selectores que delimitan un elemento HTML.

    Ejemplo:
    ```css
    h1{
        /*- Declaracion -*/
    }
    ```
- Selector de clase:
    Ejemplo:
    ```css
     .box{
         /*- Declaracion -*/
     }   
    ```
- Selector por ID:
    Ejemplo:
    ```css
    #unique{
        /*- Declaracion -*/
    }
    ```
- Selectores por atributo:
   Ejemplo:
    ```css
    a[title]{
        /*- Declaracion -*/
    }

    a[href="https://example.com"] {
        /*- Declaracion -*/
     }
    ```
## Pseudoclases y los pseudoelementos

Aplican estilo a ciertos estados de un elemento.

Ejemplo:
```css
    a: hover {
        /*- Declaracion -*/
    }

    p::first-line {
        /*- Declaracion -*/
     }
```

Documentación psedoclases:
[pseudoclases](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements#%c2%bfqu%c3%a9_es_una_pseudoclase)

## Combinadores
El último grupo de selectores combina otros selectores con el fin de delimitar elementos de nuestros documentos.

Ejemplo:
```css
    article > p { 
        /*- Declaracion -*/
    }
```
Selecciona los párrafos que son hijos directos del elemento ``<article>`` utilizando el operador de combinación hijo (>):

Documentación combinadores:
- [Combinador descendente](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectors/Combinators#selector_de_descendientes)


- [Combinador hijo](https://developer.mozilla.org/es/docs/Web/CSS/Child_combinator)

- [Combinador adyacente](https://developer.mozilla.org/es/docs/Web/CSS/Adjacent_sibling_combinator)



# Cascada y herencia

## Casacada

La cascada en las hojas de estilo significa que el orden de las reglas importa en CSS: cuando dos reglas tienen la misma especificidad, se aplica la que aparece en último lugar en el CSS.

Ejemplo:
```css
h1 { 
    color: red; 
}
h1 { 
    color: blue; 
}
```

## Especificidad:
La especificidad es el modo que tiene el navegador de decidir qué regla se aplica si diversas reglas tienen selectores diferentes pero podrían aplicarse a un mismo elemento.
Ejemplo:
```html
<h1 class="main-heading">This is my heading.</h1>
```
```css
.main-heading { 
    color: red; 
}
        
h1 { 
    color: blue; 
}
```

## Herencia
La herencia también debe entenderse en este contexto: algunos valores de las propiedades CSS que se han establecido para los elementos padre los heredan los elementos hijo, pero otros no.

Ejemplo:
```css
body {
    color: blue;
}

span {
    color: black;
}
```

# Modelo de Caja de CSS
El modelo de caja CSS  es un módulo  CSS que define cajas rectangulares, incluyendo sus rellenos y márgenes, que son generadas para los elementos y que se disponen de acuerdo al modelo de formato visual.

Mas información:

[Modelo caja](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Box_Model#especificaciones)


# Diseño CSS
Las técnicas de diseño de páginas web con CSS nos permiten controlar dónde se ubican los elementos que están contenidos en una página web en relación con su posición predeterminada en el flujo de diseño normal, así como el resto de elementos a su alrededor, su contenedor principal o la vista/ventana principal. 

- Flujo normal
- La propiedad display
- Flexbox
- Grid
- Floats
- Posicionamiento
- Diseño de tablas
- Diseño a varias columnas

## Flujo normal
El flujo normal es el modo como el navegador presenta las páginas HTML de forma predeterminada cuando no haces nada para controlar el diseño de página.

Ejemplo:
```html
<p>Amo a mi gato.</p>

<ul>
  <li>Comprar comida para gatos</li>
  <li>Ejercicio</li>
  <li>Anímate amigo</li>
</ul>

<p>¡Fin!</p>
```

## Flexbox ó Cajas Flexibles
Para usar el método Flexbox, aplica display: flex al elemento padre de los elementos que deseas distribuir; todos sus elementos hijo directos se convierten en elementos flexibles.

Ejemplo:
```html
<div class="wrapper">
  <div class="box1">Uno</div>
  <div class="box2">Dos</div>
  <div class="box3">Tres</div>
</div>
```
```css
.wrapper{
    display: flex;
}
```

# CSS Grid Layout
Mientras que el método Flexbox está pensado para distribuir elementos unidimensionalmente, el diseño de cuadrícula está diseñado para distribuir elementos en dos dimensiones: alinear elementos en filas y columnas.

![grid css](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2F1.bp.blogspot.com%2F-U3rHRyiwlSA%2FXjonukZGY3I%2FAAAAAAAAJ_U%2F-K_pNt8tpIoXKLI_zoYhApo_GdmE0T4mwCLcBGAsYHQ%2Fs1600%2Fcss-grid-module.png&f=1&nofb=1)

Mayor información de diseño en css:
[Enlace](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout/Introduction)

# ¿Qué es la metodología BEM?
BEM CSS es una metodología de nomenclatura para definir las clases en los nodos HTML del documento.

Es decir, es una manera de nombrar las clases de los nodos de tu HTML para posteriormente atacarlos con CSS de una manera fácil, sencilla y clara.

El objetivo de BEM es dar mucha más transparencia y claridad en tu estructura HTML y CSS.

BEM te dice cómo se relacionan las clases entre sí, lo que es particularmente útil en secciones complejas del documento.

BEM son tres siglas.

- **B** de bloque.
- **E** de elemento.
- **M** de modificador

- **Un bloque** es una sección independiente que tiene significado propio por sí solo.
- **Un elemento** son porciones más pequeñas internas a un bloque. Se usa para ir dividiendo el bloque en  segmentos más pequeños.

- **Un modificador** sirve para modificar algunas propiedades de un bloque o elemento.

```html
<!-- EJEMPLO 1 -->
<div class="block">
    <div class="block__element">Elem 1</div>
    <div class="block__element">Elem 2</div>
    <div class="block__element block__element--modifier">Elem 3</div>
</div>

<!-- EJEMPLO 2 -->
<div class="item item--modifier">
    <div class="item__element">Elem 1</div>
    <div class="item__element">
        <div class="item__another-element">Elem 2</div>
        <div class="item__another-element">Elem 3</div>
    </div>
    <div class="item__element item__element--modifier">Elem 4</div>
</div>
```
código css

```css
// EJEMPLO 1
.block{ color: inherit; }
.block__element{ color: inherit; }
.block__element--modifier{ color: inherit; }

// EJEMPLO 2
.item{ color: inherit; }
.item--modifier{ color: inherit; }
.item__element{ color: inherit; }
.item__element--modifier{ color: inherit; }
.item__another-element{ color: inherit; }
```
Con preprocesador
```css
// EJEMPLO 1
.block{ 
    color: inherit;
    &__element{
        color: inherit;
        &--modifier{ 
            color: inherit;
        }
    }
}

// EJEMPLO 2
.item{ 
    color: inherit;
    &--modifier{
        color: inherit;
    }
    &__element{
        color: inherit;
        &--modifier{
            color: inherit;
        }
    }
    &__another-element{
        color: inherit;
    }
}
```

# Otras metodologias

## Object-Oriented CSS (OOCSS)
Más información:
[Documentación](http://oocss.org/)

## Scalable and Modular Architecture for CSS (SMACSS)
Más información:
[Documentación](https://smacss.com/)



# buenas practicas css
1. Comentar tu CSS
Al igual que en cualquier otro idioma, es una gran idea comentar tu código en secciones. 
```css
/*-------- MAIN CONTENT---------*/

/*Here's how you comment CSS */
```
2. Alfabetizar tus propiedades
Mientras que esto es más de una extremidad frívola, puede venir en práctico para la exploración rápida.
```css
#cotton-candy {
    color: #fff;
    float: left;
    font-weight:
    height: 200px;
    margin: 0;
    padding: 0;
    width: 150px;
}
```

# Referencia recomendada
[Documentacion Css](https://developer.mozilla.org/es/docs/Web/CSS)