# sesion-15a
Martes 24 de Noviembre

## Apuntes sesión
Máquina sonora interactiva con 9 perillas (4 selectoras de especies, 4 de probabilidad y 1 de tempo), un botón de encendido y un parlante. La mayor parte del cuerpo es de terciado, los detalles y el resto de impresión 3D.

---

## 1. Medidas generales (a validar)

| Pieza | Medida (mm) |
|---|---|
| Panel frontal (terciado 3 mm) | 300 × 150 |
| Profundidad del cuerpo | ~120 |
| Tapa superior de madera (parlante) | ~110 × 120 |
| Perilla grande | Ø 30 |
| Perilla chica | Ø 15 |
| Perilla de tempo | Ø 45 (propuesta, por definir) |
| Separación entre perillas grandes | 56 entre centros |

---

## 2. Componentes y distribución interior

| Componente | Medida aprox. | Nota |
|---|---|---|
| Raspberry Pi Pico 2W | 51 × 21 | Recorte para el micro USB en la pared trasera. |
| Protoboard 830 puntos | 165 × 55 × 10 | Va en el piso, bajo la zona de ranuras. |
| Potenciómetro B100k (9: 4 selectores, 4 de nivel, 1 de tempo) | Rosca M7, eje 6, profundidad 25 a 30 (*) | Definen la altura interior. |
| Multiplexor CD74HC4067 | ~33 × 18 (*) | Necesario: la Pico tiene solo 3 entradas ADC. Sus 16 canales alcanzan para los 9 potenciómetros. |
| Amplificador MAX98357A (I2S) | ~18 × 19 (*) | |
| Parlante 3 W | Ø 40 a 50 (*) | **Medir.** Define la malla. |

(*) Valor típico, no medido.

**Altura interior:** con 120 mm de fondo, descontando ~30 mm de potenciómetros, quedan ~90 mm para protoboard, Pico y cableado.

---

## 3. Lógica de armado
- **Panel frontal:** atornillado con 4 tornillos M3 a pilares de la carcasa impresa. Bolsillos hexagonales para las tuercas en el PLA, para no roscar directo.
- **Acceso al interior:** se abre sacando el panel, que lleva los potenciómetros. Dejar ~100 mm de cable sobrante para apoyar el panel boca abajo sin desconectar. GND y 3V3 compartidos entre potenciómetros.
- **Tapa del parlante:** de madera, atornillada, para poder cambiar el parlante. Malla de agujeros Ø 4 a un paso de 9 mm, dentro de un campo un poco menor que el diámetro del parlante, y anillo impreso por debajo que lo sostiene.
- **Electrónica:** protoboard en el piso bajo las ranuras de ventilación. Recorte para micro USB atrás.
- **Folleto:** bolsillo impreso en el costado derecho. Su tamaño depende del formato del folleto.
- **Cama de impresión:** el cuerpo de 300 mm no cabe en una cama típica de 220 mm. Dividir en 2 o 3 piezas unidas con tornillos.
- **Prototipo en cartón:** misma geometría que la versión final. Si el cartón no mide 3 mm, compensar en los encajes. Para el corte láser considerar el kerf (~0,1 a 0,2 mm).

---

## 4. Lista de materiales (grupo-03)

| Material | Proveedor | Precio unit. | Cant. | Total | Notas |
|---|---|---|---|---|---|
| Raspberry Pi Pico 2W | MCI Electronics | $14.990 | 1 | $14.990 | Se usa la de la universidad. |
| Cable micro USB | Mechatronic Store | $2.190 | 1 | $2.190 | Se usa un cable propio. |
| Protoboard 830 puntos | Mechatronic Store | $3.790 | 1 | $3.790 | Sin stock en Afel. |
| Potenciómetro B100k | Afel | $500 | 9 | $4.500 | 4 selectores + 4 de nivel + 1 de tempo. |
| Parlante 3 W | Afel | $3.000 | 1 | $3.000 | Alternativa 8 Ω 1 W en Mechatronic: $3.290. |
| Botón pulsador | Afel | $100 | 1 | $100 | Ver observaciones. |
| Multiplexor CD74HC4067 | Afel | $2.000 | 1 | $2.000 | |
| Cables dupont M-M, M-H, H-H (pack 20) | Afel | $1.000 | 3 | $3.000 | |
| Amplificador MAX98357A | Mercado Libre | $1.114 | 1 | $1.114 | Ya encargado en AliExpress. |
| Filamento PLA | Todotoner | $10.990 | 1 | $10.990 | Por comprar. |
| Resistencia 10 kΩ | Mechatronic Store | $100 | 1 | $100 | Ver observaciones. |
| Plancha terciado 3 mm | Imperial | $9.310 | 1 | $9.310 | Pedido por hacer, ~2 días de dimensionado. |
| Tornillo M3 con tuerca (pack 20) | Mechatronic Store | $1.290 | 1 | $1.290 | |
| **Total** | | | | **$56.374** | - |

---

## 5. Observaciones y decisiones pendientes
1. **Botón de encendido:** el pulsador 12×12×7
2. **Perilla de tempo:** es la novena. Validar con Yai y con el replanteamiento de Cata, porque su función puede cambiar el diseño del agarre o del recorrido.
3. **Resistencia de 10 kΩ:** probablemente no hace falta, porque la Pico tiene pull-up interno.
4. **Colores:** las perillas son verde y burdeo, y la carcasa también es burdeo. Con un solo PLA hay que elegir un color.
5. **Recorrido del potenciómetro:** los íconos ocupan ~90°, pero el potenciómetro recorre ~270°. Decidir entre un tope impreso en la perilla o asignar las zonas por código.
6. **Filamento:** 1 kg probablemente alcanza para la carcasa y las perillas.

---

## 6. Perillas 3D (primer planteamiento)

| Parámetro | Perilla grande | Perilla chica |
|---|---|---|
| Diámetro | 30 mm | 15 mm |
| Tempo | Ø 45 mm propuesto, mismo encaje y estriado que la grande | |
| Alto | ~16 mm | por definir |
| Agarre | Borde estriado | Borde estriado |
| Marcador | Relieve | Relieve |

Eje: estándar de 6 mm, con estría o plano en D (confirmar con el potenciómetro de Afel).

---

## 7. Entregables de la semana 2

- [x] Medidas generales y específicas (propuestas, por validar)
- [x] Distribución interna de los componentes (propuesta)
- [ ] Planos y moldes para corte láser (panel y tapa listos; faltan fondo, laterales y pilares)
- [ ] Prototipo físico en cartón a escala real
- [x] Lógica y sistema de armado definidos (por validar)
- [ ] Primer modelado 3D de las perillas
- [ ] Pseudocódigo actualizado según la investigación de Cata
- [x] Madera seleccionada y lugar de compra identificado (terciado 3 mm, Imperial)
- [x] Lista de materiales, cantidades y cotizaciones (con ajustes pendientes)

---

## 8. Pendientes para validar con Yai

1. Posición y tamaño de la perilla de tempo.
2. Diámetro real y profundidad del parlante.
3. Tamaño del folleto.
4. Rosca, eje y profundidad del potenciómetro, medidos con calibre.
5. Tamaño de la cama de la impresora.
6. Pseudocódigo del tempo (a la espera de la investigación de Cata, y revisión posterior con Magda).

## encargos

## lectura
