# Selectors
- Selectors target elements to apply styles
- Types of selectors:Basic selectors / Combinators / Pseudo-classes / Pseudo-elements
fuente: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors

## 1.- Basic Selectors: Seleccionar elementos individuales

```txt
element
.class
#id
*
attribute 
```
```txt
  /*Attibute selectors */
   input[type="text"] {
    border: 2px solid blue;
   }
```

## 2.Combinators: Seleccionar elementos según su relación con otros. Esto es un grafo. Relaciones por nivel.

```txt
Debes conocer:

Relacion entre Padres(contenedores) e hijos(descendiente)

(espacio) : descendiente : «¿Existe algún <p> dentro de .container? No importa cuántos niveles haya entre ellos». Atraviesa todo el grafo

> : hijo directo : Child combinator. Selecciona únicamente a los hijos. Si quieres aplicar un estilo solo al primer nivel del grafo utiliza

Relacion entre hermanos. Tiene un elemento padre como contenedor.
+ : Hermano inmediato o adjacente
~ : Hermano general, todos los hermanos posteriores
```
h1 + p {
  color: red;
}

«¿Cuál es el primer <p> que aparece inmediatamente después de un <h1>?»

```txt
div (Padre contenedor)
├── h1
├── p   ← seleccionado
├── p
├── span
└── p
```
```txt
h1 ~ p {
  color: blue;
}
```

```txt
«¿Qué párrafos aparecen después del <h1> y comparten el mismo padre?»

div (Padre contenedor)
├── h1
├── p   ← seleccionado
├── p   ← seleccionado
├── span
└── p   ← seleccionado

```
```txt
Padre
├── h1
├── p
├── p
├── span
└── p
```
```txt
| Selector         | Significado                    |
| ---------------- | ------------------------------ |
| `.container p`   | Todos los descendientes        |
| `.container > p` | Solo los hijos directos        |
| `h1 + p`         | El hermano inmediato           |
| `h1 ~ p`         | Todos los hermanos posteriores |
```


## 3. Pseudo-classes: Seleccionar elementos según un estado. React to user interactions
Pseudo-classes (:) clases ficticias para seleccionar
se comportan como si se hubiera añadido una clase a su HTML.


```txt
 estado actual
:hover 
:focus, 
:active, 
:disabled

posición dentro del documento
:first-child, 
:last-child,
:only-child
:nth-child()
```

## 4. Pseudo-elements: Insert elements in css 

Hace aparecer Elementos ficticios en el body del html

```txt
::before
::after (permiten insertar contenido decorativo antes o después de un elemento)
::selection (el texto que el usuario selecciona con el ratón).
::first-letter
::first-line (la primera línea de un párrafo).
```

 <!--tabindex="0" hace posible que que el li reciba el foco del teclado con el tab-->
    
    <ul class="items">
      <li tabindex="0" class="html"><span class="text">Learn HTML</span></li>
      <li tabindex="0" class="css"><span class="text">Learn CSS</span></li>
      <li tabindex="-1" class="js"><span class="text">Learn JavaScript</span></li>
    </ul>

 <!-- Los pseudo elementos ::first-letter solo funciona en elementos de bloque (block, inline-block, etc.). -->
span {
  display: inline-block;
}

span::first-letter {
  color: brown;
  font-weight: bold;
}

<!--Pseudo clases nth-child -->
    Odd son los pares 0, 2, 4 
    even son los impares 1, 3, 5
    entre parentesis las variables
   si usas numeros empieza desde el 1 

    li:nth-child(even) {
      background-color: limegreen;
    }


    li:nth-child(3) {
      background-color: rebeccapurple;
    }