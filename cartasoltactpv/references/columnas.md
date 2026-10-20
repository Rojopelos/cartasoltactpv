# Esquema fijo

Hoja principal Articulos, cabeceras en primera fila, sin filas vacias iniciales. No modificar el orden.

| Columna | Cabecera | Contenido |
|---|---|---|
| A | CODIGO | Entero global por articulo, repetido en formatos |
| B | DESCRIPCION | Nombre principal |
| C | DEPARTAMENTO | Departamento indicado |
| D | PVP1 | Precio, o cero si hay formatos |
| E | IMPUESTO | 10 salvo orden |
| F | PVP2 | Vacio salvo dato |
| G | PVP3 | Vacio salvo dato |
| H | PR. COMPRA | Vacio salvo dato |
| I | STOCK | Vacio salvo dato |
| J | STOCK MIN. | Vacio salvo dato |
| K | STOCK MAX. | Vacio salvo dato |
| L | FORMATO | Solo variante; vacio si unica |
| M | PVP1 FORMATO | Precio de formato |
| N | PVP2 FORMATO | Vacio salvo dato |
| O | PVP3 FORMATO | Vacio salvo dato |
| P | Descripcion L1 | Hasta 7 caracteres |
| Q | Descripcion L2 | Hasta 7 caracteres |
| R | Descripcion L3 | Hasta 7 caracteres |
| S | Descripcion Bajo Boton | Vacio salvo orden |

Guardar precios numericos con formato 0.00. Cero expreso (extra gratuito) es distinto de dato ausente. No inventar tarifas, stocks o compra. El CSV de assets usa coma y solo contiene cabeceras: convertir a XLSX mediante herramientas de hojas de calculo.
