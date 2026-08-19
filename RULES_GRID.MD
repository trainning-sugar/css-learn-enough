# El modelo mental de grid

- Trabaja con un contenedor al que se le aplica el display:grid
- El contenedor se convertira en una *hoja cuadriculada* donde hay *filas-row* y *columnas-columns*
- En las grillas hablamos de lineas, 3 columnas - 4  lineas
                                     3 rows - 4 lineas
- fr: fraction del espacio disponible. Eliminates math: You do not need to manually calculate awkward pixel or percentage widths

```txt
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px; (columnas de 100 px c/u)
  grid-template-columns: 1fr 1fr 1fr; (1 fraccion del area disponible)
  grid-template-columns: repeat(3, 1fr); Evitar repeticiones
  grid-template-columns: 1fr 2fr 1fr;
  gap: 20px; la distancia entre las celdas

  "Crea tantas columnas como puedas. Cada columna debe medir, como mínimo, 200 píxeles".
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
}

```


