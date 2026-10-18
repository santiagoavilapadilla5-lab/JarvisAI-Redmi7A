# JARVIS AI para Android — prototipo inicial

Este es un proyecto fuente de Android Studio, no un APK compilado. Incluye una interfaz futurista sencilla, entrada por texto, reconocimiento de voz del sistema Android y respuestas habladas mediante TextToSpeech.

## Compatibilidad
- Android 6.0 (API 23) o superior.
- En un Redmi 7A debería funcionar si los servicios de voz de Android/Google están instalados y el permiso de micrófono está concedido.
- El reconocimiento de voz puede necesitar internet y depende del motor de voz configurado en el teléfono.

## Qué funciona en este prototipo
- Interfaz JARVIS azul oscuro.
- Botón para hablar en español.
- Respuestas por voz.
- Respuestas locales básicas de demostración.

## Qué todavía no incluye
- No se conecta aún a un modelo de IA real.
- No escucha continuamente la frase “Hola, JARVIS” en segundo plano.
- No controla libremente el sistema Android.

## Cómo generar el APK
1. En una computadora, instala Android Studio desde https://developer.android.com/studio
2. Descomprime esta carpeta.
3. En Android Studio, elige **Open** y selecciona la carpeta `JarvisAI_Android_Project`.
4. Espera a que Gradle sincronice el proyecto. Si pide instalar Android SDK 35, acepta.
5. Ve a **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. Al finalizar, Android Studio mostrará un enlace para localizar el APK.
7. Transfiere el APK al Redmi 7A e instálalo. Android puede pedir que autorices la instalación desde esa fuente.

## Conectar IA de forma segura
No incluyas una API key secreta dentro del APK: puede extraerse de la aplicación. Para una versión conectada a IA, utiliza un pequeño backend HTTPS que guarde la clave en el servidor y reenvíe las peticiones. También puedes usar un proveedor de IA compatible con las condiciones y límites de tu cuenta.

## Privacidad
La aplicación pide permiso de micrófono solo para la función de reconocimiento de voz iniciada por el usuario. El comportamiento del reconocimiento puede depender del servicio de voz instalado en Android. No se guarda intencionalmente un historial en disco en este prototipo.


## Compilar APK con GitHub Actions

Este paquete incluye un flujo de GitHub Actions en `.github/workflows/android.yml`. Sube el contenido del ZIP al repositorio (manteniendo la carpeta `.github`) y abre la pestaña **Actions**. Ejecuta **Build JarvisAI APK** con **Run workflow** o realiza un push a la rama. Cuando termine, descarga el artefacto **JarvisAI-debug-apk** desde la ejecución.

Esto configura la compilación en la nube; el ZIP sigue siendo código fuente y no contiene un APK precompilado.
