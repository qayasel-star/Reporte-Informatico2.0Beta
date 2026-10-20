# Registro Informático — revisión técnica v1.5

## Cambios aplicados
- Se unificó la versión visible y de compilación en 1.5.0 (`versionCode=2`).
- El formulario ya no rellena silenciosamente con Windows el campo de software vacío de un reporte antiguo.
- Se agregó el valor personalizado para software/equipo cuando se selecciona “Otro”.
- El módulo Informes guarda un archivo CSV real mediante el selector de archivos de Android, en vez de compartir texto con apariencia de CSV.
- Los filtros de reportes se desplazan horizontalmente en pantallas estrechas.
- El encabezado del formulario respeta el área de la barra de estado.
- Se retiró del ZIP el archivo ZIP antiguo anidado para evitar confusión al reemplazar el proyecto.

## Revisiones pendientes de entorno
- No se pudo ejecutar `gradle assembleDebug` en este entorno porque no hay instalación de Gradle ni acceso a Internet para descargar la distribución. La compilación final debe verificarse con GitHub Actions.
- No se ha ejecutado una prueba instrumental en dispositivo. Conviene probar creación/edición, cambio de estado, importación/restauración y exportación CSV antes de sustituir la APK instalada.

## Persistencia
Los reportes continúan almacenándose localmente en SharedPreferences en JSON. La importación de una copia JSON reemplaza la lista actual; exportar una copia antes de restaurar evita pérdida accidental de datos.
