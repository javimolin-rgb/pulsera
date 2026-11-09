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

## Cómo se calcula el hilo

```
largo final = muñeca + holgura
banda       = largo final − lo que reserva el cierre
por hilo    = banda × multiplicador del patrón × factor del hilo
              + margen del cierre, + 10 %, redondeado a 5 cm
```

El multiplicador es lo que cambia entre patrones: un nudo doble consume unos
4 cm de hilo por cada centímetro de pulsera, y los patrones de nudo plano
bastante más, porque los hilos de trabajo rodean los del centro. Son
estimaciones: quien anuda apretado gasta más.

## Uso

Abrir `index.html` en el navegador. No necesita servidor ni dependencias; lo
único externo son las tipografías de Google Fonts.
