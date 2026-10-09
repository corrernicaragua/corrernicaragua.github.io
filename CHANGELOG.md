# Cambios de la encuesta «Correr en Nicaragua»

## 2026-10-08 · Ajuste: tarjeta de autoría más corta

A pedido de Saymond, la tarjeta de la primera pantalla queda solo con «Una encuesta de Xolo Run» y el enlace «Quiénes somos y qué hacemos con tus respuestas». Se quitaron los dos párrafos porque ese enlace ya abre el detalle, incluido que quien comparte la encuesta no la organiza ni ve las respuestas. La autoría sigue visible en la tarjeta y en la barra superior.

## 2026-10-08 · Rediseño de confianza (versión `2026-10-08-xolo`)

**Publicado:** 8 oct 2026, commit `ec521ca`, en https://corrernicaragua.github.io/.

**Por qué:** al pedir a administradores de grupos que la compartieran, algunos preguntaron quién está detrás (Pride Run Club Managua). Otros temían que su comunidad creyera que la encuesta era suya (Granada Runners pidió que lo dijera al inicio). La versión anterior no decía de quién era y guardaba el propósito para el final.

**Respaldo de la versión anterior:** rama `respaldo/encuesta-2026-10-06` y etiqueta `respaldo-2026-10-06` (commit `3bc8e6b`). Para volver atrás: `git checkout respaldo-2026-10-06 -- index.html`.

### Preguntas (sin cambios de título, orden ni claves: los datos siguen siendo comparables)

| Clave | Cambio |
|---|---|
| P1 | Solo el texto de ayuda: «No hay respuestas correctas ni respuestas que nos convengan: si hoy todo te funciona bien, eso también nos sirve». Antes: «No hay respuestas correctas. Si no te acuerdas de algo, elige "No me acuerdo"». |
| E18 | Pasa de obligatoria a opcional (botón «Saltar»). Ayuda: «Si no hubo nada, puedes saltarla». |
| Z1 | Pasa de obligatoria a opcional (botón «Saltar»). |
| Z3 | Dos opciones nuevas: `facebook` («Facebook») y `pagina` («Una página o grupo de running que sigo»). |

No se agregó ni se quitó ninguna pregunta. Una pregunta opcional saltada no se guarda (no aparece la clave en `answers`).

### Autoría y confianza

- Vista previa del enlace (título y descripción): «Encuesta de Xolo Run».
- Barra superior de todas las pantallas: «Una encuesta de Xolo Run» debajo de «Correr en Nicaragua».
- Primera pantalla: tarjeta «Una encuesta de Xolo Run». Dice que es un proyecto nicaragüense e independiente que quiere escuchar antes de construir, y que el grupo que la comparte no la organiza ni ve las respuestas.
- Nueva página `#quienes`: quiénes somos, para qué sirven las respuestas, qué se pregunta y qué no, quién ve las respuestas y la lista completa de preguntas.
- Mensaje de mitad del recorrido: ya no promete revelar el propósito al final.
- Final: explica que el detalle de la app se dejó para el final para no influir en las respuestas. Nombra Xolo Run.
- Imagen de la medalla para historias: «Una encuesta de Xolo Run · 2026».

### Compartir

- Nuevo kit (`#compartir` para cualquier persona y `#grupos` para clubes, páginas y grupos). Pregunta cómo la va a compartir, el nombre y el tipo de comunidad y dónde la va a publicar. Entrega una imagen (historia 1080×1920 o publicación 1080×1350 con QR), un texto adaptado, un enlace propio y un botón de WhatsApp.
- Canales nuevos en `channel` (mismo formato permitido por la base, sin migración):
  - Personas: `p-historia`, `p-post`, `p-mensaje`.
  - Comunidades: `g-<tipo>-<nombre>`, donde el tipo es `cl` (club), `pg` (página), `gr` (grupo), `or` (organizador) u `ot` (entrenador, gimnasio o tienda).
- Invitación discreta para administradores en el inicio, el final y `#quienes`.
- El QR usa la misma librería que `cartel.html` (qrcode-generator 1.4.4 de cdnjs) y solo se carga al generar la imagen.

### Diseño

- Misma paleta, tipografía y composición. Se agregó luz sutil: brillo cálido detrás del titular, bordes con luz en las tarjetas, destello lento en el botón dorado y destello único en la medalla. Todo se apaga con «reducir movimiento».
- Al final, tarjeta «Próximamente» con insignias propias de Google Play y App Store. No usa los logos oficiales porque las tiendas solo los permiten con la app publicada.

### Técnico

- `VERSION = '2026-10-08-xolo'`: el tablero separa ambas versiones por `version`.
- Mismas claves de almacenamiento en el teléfono que la versión anterior: los borradores y las respuestas pendientes sin señal se conservan y se envían.
- En `localhost` no se envía nada a Supabase y la pantalla lo avisa. Para probar el envío real en local: `?enviar=1&c=prueba`.
- `CONTACT` (correo o Instagram) está vacío y no se muestra. Falta llenarlo.
- Pendiente en el tablero: agregar al catálogo las opciones nuevas de Z3 y los canales `p-` y `g-`.
