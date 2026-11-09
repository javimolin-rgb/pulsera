# Taller de pulseras de hilo

Página web estática (un solo archivo, `index.html`) con patrones de pulsera de
hilo anudado: el gráfico de nudos de cada patrón, el paso a paso fila por fila y
el cálculo de cuánto hilo hay que cortar para el largo de muñeca que se quiera.

## Qué incluye

- **11 patrones.** Siete con gráfico de nudos generado por código (rayas
  diagonales, chevron, chevron ancho, zigzag, rombos, damero y «Ornamento», de
  14 hilos y 38 filas) y cuatro de macramé y trenza explicados con dibujos
  (trenza de 4 hilos, nudo plano, espiral de medio nudo, nudo plano con
  cuentas).
- **Gráfico en notación de patrón.** Cada nudo es un círculo del color del hilo
  que anuda, con una flecha que indica el sentido; entre los nudos se dibuja el
  recorrido real de cada hilo, con las filas numeradas a ambos lados y las
  letras de los hilos arriba y abajo. Encima va una vista de cómo queda tejida.
- **Paso a paso.** Para los patrones de gráfico, la secuencia de nudos de cada
  fila se genera simulando el patrón: qué pareja de hilos se anuda, en qué
  sentido y con qué color. Se puede recorrer fila a fila.

### Sobre el patrón «Ornamento»

Está transcrito de un gráfico de referencia. Los colores de los 247 nudos se
leyeron de la imagen y los tipos de nudo se dedujeron resolviendo qué secuencia
los reproduce, imponiendo la simetría izquierda-derecha del dibujo. La
transcripción se comprueba simulando el patrón: los 247 nudos salen del color
correcto, los hilos acaban en el mismo orden en que empiezan y los dos hilos de
los bordes nunca se mueven de su sitio, igual que en el original.
- **Los nudos.** Diagramas SVG del nudo hacia la derecha, hacia la izquierda,
  el doble de ida y vuelta, el nudo plano y el medio nudo.
- **Cierres.** Trenzas para atar, nudo corredizo ajustable y broche de pinza,
  con lo que cada uno resta de banda y suma a cada hilo.
- **Cálculo de hilo.** A partir de la muñeca, la holgura, el cierre y el tipo de
  hilo, calcula el largo de corte de cada hilo, el total por color y las madejas
  necesarias. La fórmula se muestra en la propia página.

## Las tres formas de conseguir un patrón

La sección «Elige un patrón» tiene tres pestañas, y las tres acaban en el mismo
panel de instrucciones:

1. **Catálogo.** Los once patrones que vienen hechos.
2. **Diseñar en píxeles.** Un lienzo donde se pinta celda a celda, o se sube una
   imagen que se ajusta a la rejilla. Cada celda es un nudo. Al crear el patrón
   se calcula quién anuda en cada celda para que salga ese dibujo.
3. **Leer un gráfico.** Se sube una foto o captura de un gráfico de nudos y se
   lee solo: busca la rejilla, lee el color de cada nudo y deduce el sentido de
   cada uno. La rejilla detectada se dibuja encima de la imagen y se puede
   corregir a mano antes de leerla.

Los colores de cualquier patrón se pueden cambiar desde la leyenda del panel, y
el gráfico, la vista de la pulsera tejida y la tabla de hilo se actualizan.

### Patrones alfa

Los dibujos de píxeles se tejen como patrón alfa: los hilos de fondo cuelgan
rectos y un hilo de trabajo cruza cada fila anudando sobre todos. En cada nudo
se decide quién anuda, y eso es lo que dibuja la figura. La técnica tiene un
límite: una celda solo puede mostrar el color del hilo de fondo de su columna o
el del hilo de trabajo de su fila. Al crear el patrón se eligen ambos para que
coincidan el mayor número de celdas y se informa del porcentaje conseguido.

### Cómo se lee un gráfico

El color de cada nudo dice cuál de los dos hilos anuda; la forma de la flecha
dice si el nudo es simple (los hilos se cruzan) o doble (cada uno vuelve a su
sitio). Con esas dos pistas se busca, fila a fila, la secuencia de nudos que
reproduce los colores leídos, y se puede pedir que respete la simetría del
dibujo y que los hilos acaben en el orden en que empezaron. El resultado se
verifica simulando el patrón y se informa de qué porcentaje de nudos reproduce
la imagen.

## Cómo se calcula el hilo

```
largo final = muñeca + holgura
banda       = largo final − lo que reserva el cierre
filas       = banda × filas por cm del hilo
por hilo    = banda + (nudos que hace ese hilo × 2 cm × factor del hilo)
              + margen del cierre, + 10 %, redondeado a 5 cm
```

En los patrones de gráfico y alfa se cuentan los nudos que hace cada hilo
simulando el patrón, así que cada color sale con su propio largo. En macramé y
trenza se usa un multiplicador sobre el largo de la banda, porque ahí no hay
rejilla de nudos que contar. Son estimaciones: quien anuda apretado gasta más.

## Uso

Abrir `index.html` en el navegador. No necesita servidor ni dependencias; lo
único externo son las tipografías de Google Fonts.
