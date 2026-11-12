# FilaLab: de HTML a APK

Este proyecto envuelve `www/index.html` (el simulador) en una app Android con Capacitor 7.
El botón de informe PDF ya usa los plugins nativos `Filesystem` y `Share`, que vienen incluidos:
en el celular el PDF se guarda en **Documentos** y se abre el menú para compartirlo.

## Opción A: GitHub Actions (no hay que instalar nada)
1. Crear un repositorio en GitHub y subir esta carpeta (sin `node_modules`).
2. Ir a la pestaña **Actions**. El flujo "Compilar APK" se ejecuta solo con cada push
   (o con el botón **Run workflow**).
3. Cuando termine (unos 5 min), abrir la ejecución y descargar el artefacto **FilaLab-apk**:
   es un .zip que contiene `FilaLab.apk`.

## Opción B: Android Studio
```bash
npm install
npx cap sync android
npx cap open android      # abre Android Studio
```
En Android Studio, ir a **Build > Build App Bundle(s) / APK(s) > Build APK(s)**.
El archivo queda en `android/app/build/outputs/apk/debug/app-debug.apk`.

## Instalar en el celular
Pasar el .apk al teléfono, abrirlo y permitir "Instalar apps de origen desconocido".
Si aparece una advertencia de Play Protect, elegir "Instalar de todas formas"
(sale porque la app no viene de la Play Store).

## Si cambian el HTML
Reemplazar `www/index.html` y volver a compilar (push en la opción A, o `npx cap sync android` + Build en la B).
