# MatchLab — PWA de estadísticas de fútbol

Primera versión funcional, sin coste mensual ni servicios externos.

## Qué funciona
- Interfaz adaptable a móvil con diseño oscuro.
- Nueve competiciones preconfiguradas.
- Añadir partidos manualmente con goles, córners, tiros a puerta y amarillas.
- Histórico, búsqueda y filtro por competición.
- Comparador de dos equipos con medias de los partidos guardados.
- Exportación de copia JSON e importación CSV.
- Almacenamiento local en el navegador.
- Service worker y manifiesto PWA para instalación y uso offline después de la primera carga.

## Qué no está conectado todavía
Esta versión NO descarga calendarios ni estadísticas automáticamente. Los datos se introducen manualmente o mediante CSV. No incluye una API externa, porque el objetivo acordado es mantener el coste mensual en 0 €. La automatización dependerá de encontrar una fuente gratuita que permita legal y técnicamente obtener los campos y competiciones deseados.

## Cómo probarla
Para que el navegador permita instalar la PWA y registrar el service worker, sirve esta carpeta desde un origen HTTPS o desde `localhost`.
- En un ordenador: `python -m http.server 8000` dentro de esta carpeta y abre `http://localhost:8000`.
- Para instalar en Android: publica la carpeta en un alojamiento estático HTTPS gratuito (por ejemplo GitHub Pages) y abre la URL en Chrome; menú ⋮ → Instalar aplicación / Añadir a pantalla de inicio.

## CSV
Encabezados esperados:
`date,league,home,away,home_goals,away_goals,home_corners,away_corners,home_shots_on_target,away_shots_on_target,home_yellows,away_yellows`

Usa una fila por partido. Fechas en formato `YYYY-MM-DD`. No uses comas dentro de los nombres de equipos o competiciones.
