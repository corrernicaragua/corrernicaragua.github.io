# Correr en Nicaragua · encuesta

Encuesta anónima de Xolo Run sobre cómo se vive el correr (y el caminar) en Nicaragua, para todas las edades.

Qué cambió y por qué: [CHANGELOG.md](CHANGELOG.md). La versión anterior está respaldada en la rama `respaldo/encuesta-2026-10-06` y la etiqueta `respaldo-2026-10-06`.

- Encuesta: https://corrernicaragua.github.io/
- Cartel con QR para imprimir: https://corrernicaragua.github.io/cartel.html
- Quiénes somos: https://corrernicaragua.github.io/#quienes
- Kit para compartir: https://corrernicaragua.github.io/#compartir (personas) y https://corrernicaragua.github.io/#grupos (clubes, páginas y grupos)

## Cómo funciona

- Una sola página estática (`index.html`), sin dependencias más allá de Google Fonts.
- Las respuestas van a la tabla `survey_responses` de Supabase. La clave del archivo es la **clave publicable**, que es pública por diseño: con ella solo se puede **enviar** una respuesta, no leerlas (RLS, migración `0010_discovery_survey.sql` del repositorio de la app).
- Sin señal, la respuesta queda guardada en el teléfono y se envía sola cuando vuelve la conexión.
- No pide nombre, cédula ni teléfono.

## Canales

Agrega `?c=<canal>` al enlace para saber de dónde llega cada respuesta (por ejemplo `?c=ig`, `?c=wa`, `?c=kits`). `?c=prueba` marca envíos del equipo y muestra lo que se envió.

El kit para compartir genera sus propios canales: `p-historia`, `p-post` y `p-mensaje` (personas) y `g-<tipo>-<nombre>` (comunidades; tipo `cl`, `pg`, `gr`, `or` u `ot`).

En `localhost` la encuesta no envía nada a Supabase. Para probar el envío real: `?enviar=1&c=prueba`.
