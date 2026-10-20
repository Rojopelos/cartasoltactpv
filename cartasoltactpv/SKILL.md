---
name: cartasoltactpv
description: Convertir cartas de restaurantes, bares y cervecerias desde texto, imagen, manuscrito, PDF, Word o listados BDP a Excel de importacion de soltac TPV. Ampliar y corregir cartas existentes aplicando esquema A-S, departamentos dados, formatos, orden alfabetico, codigos correlativos y etiquetas de botones de tres lineas de hasta siete caracteres. Usar al pedir programar una carta para soltac o importar articulos de BDP, no para clientes ni consultas SQL ajenas a cartas.
---

# cartasoltactpv

Version 1.2. Reglas consolidadas el 20-10-2026.

## Prioridad y alcance

Cumplir primero las indicaciones actuales de cada carta, despues su plantilla y datos, y despues estas reglas generales. No transformar excepciones, precios o correcciones de un cliente en normas para otros. Escribir la marca soltac siempre en minusculas. Comunicarse en español de forma breve.

## Procedimiento

1. Leer los origenes completos. Unir listados BDP de departamentos y proporciones por identificador original. Las proporciones corresponden a formatos; no es obligatorio conservar los codigos de origen en cartas nuevas.
2. Respetar los departamentos indicados: no inventar, separar, fusionar ni renombrar salvo orden. Si hay uno solo, usarlo para todo lo indicado, incluidos aperitivos. No duplicar articulos por titulos paraguas como Tapeos.
3. Transcribir precios y significado. Distinguir ENS. GAMBAS (ensaladilla) de GAMBAS. No inventar precios, ingredientes, tamaños o variedades. Preguntar por dudas que bloqueen y avanzar con el resto.
4. Aplicar articulos y formatos segun el modo de venta. No dividir automaticamente alternativas unidas por y/o/barra: entender si son un boton conjunto o productos independientes. Si se enumeran sabores independientes bajo un precio comun, crear los articulos correspondientes. En bufet o botones directos expresos, conservar cada linea independiente y no agrupar en formatos.
5. Normalizar textos y preparar las etiquetas manualmente con criterio semantico.
6. Agrupar por departamento y ordenar los articulos A-Z dentro de cada uno, en español y sin distinguir tildes; conservar Ñ despues de N. Mantener el orden de aparicion de departamentos salvo indicacion. Asignar codigos enteros globales correlativos desde 1; no reiniciar por departamento. Repetir el mismo codigo en todos los formatos del articulo y mantenerlos juntos en orden logico. Al ampliar cartas, ordenar y renumerar el resultado final salvo orden expresa de conservar identificadores.
7. Usar la habilidad de hojas de calculo disponible para crear o editar XLSX. Leer [columnas](references/columnas.md) y usar [plantilla A-S](assets/plantilla_soltac_A-S.csv). Preservar hojas y datos ajenos al alcance de una edicion. Entregar XLSX descargable; mostrar previa si la piden.
8. Aplicar el control final. Para nuevas normas generales, actualizar y guardar esta habilidad mediante el flujo de creacion de habilidades de la plataforma. No confundir una afirmacion de recuerdo con persistencia garantizada.

## Descripciones

- Usar MAYUSCULAS, sin tildes en vocales, conservando Ñ. Quitar diacriticos de vocales.
- Eliminar AL, CON, Y y otros conectores prescindibles cuando no cambie el significado. Conservar SIN. No eliminar fragmentos dentro de palabras o marcas.
- Abreviar palabras largas de forma comprensible: ENS., MONT., TORT., SOL., SOLOMIL. No perder identidad ni diferencias de sabor o producto.
- Usar solo el nombre principal, sin proporcion cuando esta aparece en FORMATO. Distinguir MONT. JAMON del plato JAMON si hace falta.
- Normalizar esta gama como COCA COLA, COLA ZERO y COLA ZERO ZERO. Conservar COCA COLA para la normal; sustituir COCA COLA ZERO por COLA ZERO y COCA COLA ZERO ZERO por COLA ZERO ZERO. En botones usar COCA / COLA, COLA / ZERO y COLA / ZERO / ZERO, respectivamente. Reordenar y renumerar si el cambio de nombre altera el orden alfabetico.

## Formatos

- Si un articulo tiene varias proporciones diferenciadas: mismo codigo y descripcion, D=PVP1=0, L=FORMATO y M=PVP1 FORMATO con su precio.
- Usar T. (tapa), 1/2 (media), R. (racion), C. (copa), BOT. (botella). Conservar otros tamaños expresos como CORTADA y CAÑON.
- No repetir el articulo en FORMATO: ENS. GAMBAS / T.; TINTO VERANO / LIMON.
- Si solo hay una presentacion, dejar L:O vacias y poner el precio en D. No crear un formato unico BOT. o C.
- Se puede agrupar cerveza de barril como CERVEZA / CORTADA y CERVEZA / CAÑON, salvo instrucciones de botones directos.
- Para TINTO VERANO el esquema habitual es LIMON, BLANCA, NARANJA y COLA, las dos ultimas con un euro mas sobre el precio base. Aplicarlo cuando se requiera ese esquema con precio base; no inventar variantes en listas de botones directos.
- No reutilizar precios de otras cartas. Leer [casos](references/casos.md) para limites y excepciones.

## Etiquetas P-R

- Rellenar Descripcion L1, L2 y L3: maximo **7 caracteres por celda contando espacios y signos**, no exactamente siete. Permitir letras mayusculas, numeros, Ñ, espacios y signos +, - y punto. No usar tildes, apostrofes, barras ni parentesis en estas columnas.
- Aprovechar hasta tres lineas con palabras completas o divisiones silabicas naturales antes que abreviaturas excesivas. No cortar mecanicamente cada siete caracteres.
- Evitar fragmentos feos, malsonantes o engañosos: ENSALA / DILLA, nunca ENSA / LADILLA.
- Usar MONT. / BARBA / COA (o MONT. / BAR / BACOA), CORO / NITA y SALCHI. en lugar de SALCH.
- Para SOLOMIL. RELLENO usar SOLO / MILLO / RELLENO; no recuperar ingredientes eliminados expresamente por el usuario.
- Conservar variantes esenciales como ZERO, 00, SIN AZUCAR y sabor. Dejar lineas innecesarias vacias; no rellenar con espacios.
- Repetir las etiquetas del articulo en sus filas de formato; no añadir el formato a las etiquetas principales.
- Incluir siempre S=Descripcion Bajo Boton y dejarla vacia salvo orden.

## Control final

- Reconciliar articulos, variantes y precios con el origen; no omitir ni duplicar.
- Verificar columnas A-S en orden, numeros tipados y precios en D o M. Usar IMPUESTO=10 como convencion acordada salvo indicacion diferente, sin presentarlo como criterio fiscal universal.
- Verificar departamentos contiguos, articulos A-Z y codigos correlativos con repeticion solo para formatos.
- Verificar mayusculas, ausencia de tildes y conectores prescindibles en textos producidos. En modificaciones puntuales preservar datos ajenos al alcance salvo que se pida normalizar toda la carta.
- Medir TODAS las etiquetas P:R: <=7 caracteres admitidos; revisar visualmente significado, cortes y variantes. Comprobar S vacia.
- En ediciones comprobar que ordenar y renumerar no altere precios, formatos ni otros datos.
