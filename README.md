# XV Launcher

Launcher para radio Android (1280x720, horizontal) con el Subaru XV animado sobre una carretera
que avanza según la velocidad del GPS.

## Compilar
1. Android Studio → Open → carpeta `XVLauncher`. Deja que sincronice Gradle (descarga todo solo).
2. Build → Build Bundle(s) / APK(s) → Build APK(s).
3. APK: `app/build/outputs/apk/debug/app-debug.apk`

## Instalar en el radio
- Pendrive/USB: copia el APK y ábrelo desde el explorador de archivos del radio (permitir fuentes desconocidas), o
- `adb install app-debug.apk`
- Pulsa Home → "XV Launcher" → "Siempre".

## Uso
- 4 atajos: toca el "+" para elegir app; mantén pulsado para cambiarla o quitarla.
- "Apps": cajón con todas las aplicaciones.
- Tocar el auto: activa/desactiva modo demo (50 km/h) para cuando el GPS no entrega velocidad.

## Personalizar
- Foto del auto: `app/src/main/res/drawable-nodpi/car.png`
- Fondo: `bg.jpg`, carretera: `road.png` (mismo directorio; la carretera debe repetirse sin costuras).
- Cantidad de atajos y velocidad visual: constantes al inicio de `MainActivity.kt`.

## Volver al launcher original
Ajustes → Apps → Predeterminadas → Aplicación de inicio.

## Compilar sin Android Studio (GitHub Actions)
1. Crea un repositorio nuevo en github.com y sube todo el contenido de esta carpeta (incluida `.github`).
2. Ve a la pestaña **Actions**; el workflow "Build APK" corre solo al subir los archivos (o con "Run workflow").
3. Cuando termine (unos 5 min), abre la ejecución y descarga **XVLauncher-apk** en la sección Artifacts.
   Dentro está `app-debug.apk`.
