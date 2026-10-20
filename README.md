# Registro Informático — Android

Proyecto Android Kotlin + Jetpack Compose con estética futurista oscura y módulos Inicio, Reportes, Análisis, Informes y Ajustes.

## Funciones incluidas
- Alta, edición, búsqueda, filtrado, cambio de estado y eliminación de incidencias.
- Formulario de reportes con campos de usuario, departamento, técnico, software/equipo, tipo de trabajo, prioridad, problema, diagnóstico, solución, tiempo y observaciones.
- Diálogo de tipo de trabajo que permite seleccionar una categoría, escribir un tipo personalizado y describir el problema o la tarea realizada.
- Validación del campo problema antes de guardar y formulario desplazable para poder acceder a todos los campos en teléfonos pequeños.
- Persistencia local mediante SharedPreferences JSON.
- Panel con métricas y análisis de incidencias por software y tipo.
- Exportación/compartición CSV.
- GitHub Actions localiza la carpeta del proyecto Gradle y genera el APK como artefacto.

## Compilar desde GitHub en Android
1. Sube el contenido de este ZIP al repositorio, o reemplaza los archivos del proyecto existentes.
2. Comprueba que `.github/workflows/android.yml` esté incluido.
3. Abre **Actions** y selecciona **Compilar APK Android**.
4. Pulsa **Run workflow** o espera a que compile después del commit.
5. Abre la ejecución terminada y descarga **Registro-Informatico-APK** en la sección Artifacts.
6. Descomprime el artefacto y busca `app-debug.apk`.

La compilación no se ha ejecutado en este entorno porque no hay Android SDK/Gradle instalados; GitHub Actions debe validar la compilación real.


## Actualización visual
- Identidad visual azul noche con acentos cian y paneles con bordes degradados.
- Icono de lanzamiento incluido en densidades Android habituales.
- El icono identifica la aplicación al instalarla.


## Actualización de configuración y datos (v1.5)
- Icono identificativo nuevo en los recursos launcher Android (todas las densidades).
- Configuración reorganizada en tarjetas: base local, copias de seguridad, transferencia con hojas de cálculo y mantenimiento.
- Exportación de copia completa en JSON e importación/restauración desde JSON.
- Exportación CSV UTF-8 con separador punto y coma para abrir en Excel; importación de CSV con las columnas exportadas por la app.
- La importación CSV añade los registros importados a los existentes; restaurar JSON reemplaza la lista actual.

Nota: el almacenamiento sigue siendo local mediante SharedPreferences JSON, no una base de datos SQLite/Room. Verificar la compilación con GitHub Actions antes de instalar.


## Revisión v1.5
- El formulario no reemplaza silenciosamente un campo de software vacío al editar reportes antiguos.
- Se permite especificar software o equipo personalizado mediante la opción “Otro”.
- La pantalla Informes guarda un archivo CSV mediante el selector de archivos de Android.
- Los filtros de reportes se desplazan horizontalmente en pantallas estrechas.
- Se ajusta el encabezado del formulario para respetar la barra de estado.


## Registro Informático 2.0 Beta

Esta entrega conserva el identificador `com.registroinformatico.app`, usa `versionCode = 3` y `versionName = 2.0-beta01`, e incluye una pantalla de presentación inicial. El flujo de GitHub Actions está en `.github/workflows/android.yml` y publica el APK de depuración como artefacto.

**Firma:** este APK de depuración no configura una clave de firma permanente. Para que futuras actualizaciones se instalen encima de una instalación previa, los APK deben compartir certificado de firma. Si la firma de esta compilación no coincide con la aplicación instalada, Android pedirá desinstalar la anterior.
