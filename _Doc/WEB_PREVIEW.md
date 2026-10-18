# Prueba del juego en navegador

La demo WebGL inicia en Plaza_Central e incluye las escenas habilitadas y guardadas del proyecto (Lobby y Sala ABC entre ellas). Sin selección previa de rol, el jugador entra como Visitante y puede recibir el carnet para convertirse en Aprendiz.

## Sitio de pruebas

URL: https://cenigraf-parque-central-20261017.awakesquid14.chatgpt.site

Sitio privado para la cuenta propietaria. La página y la build publicada se conservan en el directorio hermano `web-preview`. Los cambios del editor requieren guardar las escenas, regenerar la build y publicar otra versión.

## Generar otra versión

Requisito: Unity 6000.3.18f1 con WebGL Build Support instalado. Guarda las escenas y ejecuta desde la raíz del proyecto:

    python3 tools/build_web_preview.py

La salida queda en Builds/WebGL y el log en Builds/web-preview-build.log. El script compila una copia separada, por lo que puedes mantener el editor abierto. También existe el menú Cenigraf → Build → Compilar versión Web de prueba dentro de Unity.

## Probar localmente

    python3 -m http.server 8080 --directory Builds/WebGL

Abre http://localhost:8080 y haz clic dentro del juego para activar el teclado. Usa los controles del juego: movimiento con WASD/flechas y E para interactuar.

La build usa Gzip con Decompression Fallback para poder alojarse en hosting estático sin configurar Content-Encoding. El destino publicado debe conservar todos los archivos de la build. El juego necesita un navegador con WebGL/WebAssembly y se prueba primero en escritorio.
