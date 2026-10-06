# Correr en Nicaragua · encuesta

Encuesta anónima sobre cómo se vive el correr (y el caminar) en Nicaragua, para todas las edades.

- Encuesta: https://corrernicaragua.github.io/
- Cartel con QR para imprimir: https://corrernicaragua.github.io/cartel.html

## Cómo funciona

- Una sola página estática (`index.html`), sin dependencias más allá de Google Fonts.
- Las respuestas van a la tabla `survey_responses` de Supabase. La clave del archivo es la **clave publicable**, que es pública por diseño: con ella solo se puede **enviar** una respuesta, no leerlas (RLS, migración `0010_discovery_survey.sql` del repositorio de la app).
- Sin señal, la respuesta queda guardada en el teléfono y se envía sola cuando vuelve la conexión.
- No pide nombre, cédula ni teléfono.

## Canales

Agrega `?c=<canal>` al enlace para saber de dónde llega cada respuesta (por ejemplo `?c=ig`, `?c=wa`, `?c=kits`). `?c=prueba` marca envíos del equipo y muestra lo que se envió.
