# Intervalos: APK para Android

Cronómetro de intervalos (ejercicio / descanso) con pitidos en la cuenta regresiva, voz y vibración.
Este proyecto empaqueta la app web como app de Android con Capacitor, y GitHub compila el APK por ti, gratis.

## Cómo obtener el APK

1. **Descomprime** este archivo.
2. Entra a [github.com](https://github.com) (crea una cuenta gratuita si no tienes) y crea un repositorio nuevo: botón **+ → New repository**. Nómbralo `intervalos`, puede ser privado, y pulsa **Create repository**.
3. En la página del repositorio elige **uploading an existing file**. Arrastra **todo el contenido** de la carpeta descomprimida (incluida la carpeta `.github`) y pulsa **Commit changes**.
   - Si no ves la carpeta `.github` porque está oculta, activa «mostrar archivos ocultos» en tu sistema. Otra opción: en el repositorio usa **Add file → Create new file**, escribe como nombre `.github/workflows/build-apk.yml` y pega el contenido de ese archivo.
4. Abre la pestaña **Actions**. El flujo **Compilar APK** arranca solo al subir los archivos (si no, entra a él y pulsa **Run workflow**). Tarda entre 5 y 10 minutos y termina con una marca verde.
5. Abre esa ejecución, baja hasta **Artifacts** y descarga **Intervalos-APK**. Es un zip con `app-debug.apk` dentro.
6. Pasa el APK al celular (cable USB, Drive, correo o WhatsApp a ti mismo) y ábrelo. Android pedirá permiso para instalar apps de esa fuente; acéptalo. Si Play Protect avisa que la app no es conocida, elige **Instalar de todos modos**.

## Cambiar algo después

Toda la app está en `www/index.html`. Si lo editas en GitHub (lápiz → Commit), el flujo vuelve a compilar y genera un APK nuevo. Los tiempos por defecto están en la línea que empieza con `var DEF = {`.

## Cosas que conviene saber

- El APK está firmado con la clave de depuración. Sirve para instalarlo tú o compartirlo, pero no para subirlo a Google Play (eso pide una firma de publicación).
- La app mantiene la pantalla encendida mientras está abierta. Si la bloqueas o cambias de app, Android puede pausar los avisos.
- La voz depende del motor de texto a voz del celular. Si no suena en español, los pitidos funcionan igual.
- Funciona sin internet; las tipografías van incluidas.

## Estructura

- `www/`: la app web (HTML, CSS, JS y fuentes).
- `android/`: proyecto de Android generado por Capacitor, con ícono propio, permiso de vibración y pantalla siempre encendida.
- `.github/workflows/build-apk.yml`: receta que compila el APK en GitHub.
