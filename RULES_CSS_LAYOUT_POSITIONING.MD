
# CSS Layout and positioning 
- Responde a la pregunta ¿Dónde debe aparecer un elemento en la página?

## Layout - display (inline, block, grid, flex, none)

- El layout define cómo se organizan varios elementos dentro de un contenedor.
- Las herramientas más utilizadas para crear un layout son:
- Organiza grupos de elementos. Crea la estructura de la página

```txt
display: none -> desaparece el elemento (hidden)
display: block
display: inlines
display: flex
display: grid
````

```txt
[A] [B] [C]

[A]
[B]
[C]

[A] [B]
[C] [D]
```
## Positioning (static, relative, absolute, fixed, sticky)

- El positioning controla la posición exacta de un elemento.
- z-index es una propiedad de CSS que controla el orden de apilamiento de los elementos.
a mayor z-index más cerca del usuario.
- z-index no funciona con elementos estáticos. Debes utilizar una propiedad position distinta de static.

El eje X controla el movimiento horizontal (izquierda y derecha).
El eje Y controla el movimiento vertical (arriba y abajo).
El eje Z controla qué elemento está más cerca del usuario.


```txt
position

├── static
│   ├── Sigue el flujo, por default
│   ├── No usa top, left ni z-index
│
├── relative
│   ├── Sigue el flujo
│   ├── Se mueve respecto a sí mismo
│   ├── Conserva su espacio
│
├── absolute
│   ├── Sale del flujo
│   ├── Busca un ancestro con position siempre busca un padre con position.
│   ├── No conserva su espacio
│
├── fixed
│   ├── Sale del flujo
│   ├── Se posiciona respecto al viewport(pantalla)
│   ├── No se mueve con el scroll
│
└── sticky
    ├── Sigue el flujo
    ├── Se comporta como relative
    ├── Se pega durante el scroll
```

## Alignment and spacing (top, right, bottom, left, z-index)
- No funcionan con el position:static (por default)
top, right, bottom y left son propiedades que indican la distancia entre un elemento y alguno de los cuatro lados de su referencia.
- z-index es una propiedad de CSS que controla el orden de apilamiento de los elementos.
a mayor z-index más cerca del usuario.
- z-index no funciona con elementos estáticos. Debes utilizar una propiedad position distinta de static.

¿Con respecto a qué pared estoy midiendo la distancia?

```txt
+--------------------------------+
|              top               |
|                ↓               |
|                                |
| left →        [A]       ← right|
|                                |
|                ↑               |
|             bottom             |
+--------------------------------+
```
.box {
    position: absolute;
    top: 20px;
    bottom: 20px;
}

```txt
+----------------------+
|       20px (top)           
| (left)  ↓       (right)             
| 20px → [A]   ← 20px                  
|         ↑  
        20px (bottom)                 
+----------------------+
```


## Overflow handling