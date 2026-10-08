# Abue · Mi cuidado

Aplicación estática en español para que una cuidadora registre presión, tomas de medicamentos, consultas e indicaciones de una sola persona. Sin cuentas, servidor de datos, analítica ni servicios externos.

## Primera versión

- Hoy: tomas diarias programadas, registro rápido de presión y actividades pendientes.
- Historial: corrección de lecturas y tomas, programa de medicamentos y recomendaciones de consulta.
- Consultas: preguntas, notas, programación de actividades y exportación de evento `.ics` sin notas de salud.
- Reportes por periodo y módulo: tabla detallada, gráfico de presión, promedio descriptivo, Excel `.xlsx` real y vista imprimible para guardar como PDF desde el navegador.
- IndexedDB local, respaldo y restauración JSON con validación, módulos desactivables conservando datos.
- PWA y caché para uso sin conexión después de la primera visita.

## Límites explícitos

Los registros viven solo en el navegador/origen actual; borrar datos del sitio puede borrarlos. No hay sincronización entre dispositivos. El respaldo JSON contiene datos de salud: guárdalo de forma privada. PDF usa la función de impresión del navegador. Los recordatorios son avisos dentro de la app abierta; NO son alarmas en segundo plano. La conexión directa a Google Calendar, Drive y las notificaciones push quedan para una siguiente versión. Los horarios de medicamentos son diarios fijos. No hay diagnóstico, clasificación clínica ni recomendaciones de dosis. Ausencia de registro no implica omisión.

## Desarrollo y publicación

Sin dependencias de producción. Servir por HTTP con `python3 -m http.server 8080`; para publicación usar HTTPS. GitHub Actions publica los archivos públicos en GitHub Pages. Si el repositorio no tiene Pages habilitado, seleccionar **Settings → Pages → Source → GitHub Actions** y volver a ejecutar **Publish Abue**.

Módulos UI en `app.js`, repositorio local en `db.js`, exportación XLSX en `exports.js`. Cada registro tiene UUID y fecha de modificación para facilitar una futura capa de sincronización. Nunca subir respaldos o datos reales al repositorio.
