# youtube-dlp
Manual de manejo e instalación ademas de instrucciones y recomendaciones

## Instalación

### Desde Chocolatey
Esta fue la forma más facil y rapida en la que yo lo pude descargar, descargamos directamente el paquete yt-dlp utilizando chocolatey ya que estos paquetes se encuentran disponibles dentro de este gestor de paquetes en linea
  - 1. Instalación de chocolatey (Recordar que se hace en el Powershell como administrador). Documentación https://chocolatey.org/install  <br/><br/>
  Con PowerShell, debemos asegurarnos de que ```Get-ExecutionPolicy``` no esté restringido. Se sugiere usar ```Bypass``` para omitir la política para instalar cosas o ```AllSigned``` para obtener un poco más de seguridad.<br/><br/>
  Ejecutar ```Get-ExecutionPolicy```. Y si regresa Restricted, ejecute ```Set-ExecutionPolicy AllSigned``` o ```Set-ExecutionPolicy Bypass -Scope Process```.<br/><br/>
  Y ejecute ahora si este comando para realizar la instalación<br/><br/>
        ```
        Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
        ```
        
        Si no se ve ningún error, ¡estara listo para usar Chocolatey! Puedes escribir ```choco``` o ```choco -?``` para verificar la instalacion

  - 2. Instalación del paquete youtube-dlp <br/><br/>
       Simplemente ejecutamos desde la terminal el siguiente comando
    
          ```
          choco install yt-dlp
          ```
        Si la instalación sale exitosamente ya podremos descargar videos desde la terminal con este comando ```yt-dlp url```, aunque estos videos suelen descargarse con una resolución muy baja y se llegan a ver pixeleados

  - 3. Intalación del paquete ffmpeg <br/><br/>
  En este caso vamos a utilizar este paquete para que ```yt-dlp``` pueda combinar el video y el audio a la hora de descargar videos con la mayor calidad de video y de audio, además de que es requerido para poder ejecutar algunos comandos que vamos a ver y utilizar despues <br/><br/>
        <details>
        <summary>Descripción de este paquete</summary>
        <br>
        Descripción encontrada en la web
        <br><br>
        FFmpeg es el marco multimedia líder, capaz de decodificar, codificar, transcodificar, mux, demux, transmitir, filtrar y reproducir prácticamente cualquier cosa que los humanos y las máquinas hayan creado. Admite desde los formatos antiguos más oscuros hasta los más modernos. No importa si fueron diseñados por algún comité de estándares, la comunidad o una corporación. También es altamente portátil: FFmpeg compila, ejecuta y pasa nuestra infraestructura de prueba FATE en Linux, Mac OS X, Microsoft Windows, BSD, Solaris, etc. en una amplia variedad de entornos de compilación, arquitecturas de máquinas y configuraciones.
        </details>

        ---

  - 3. Comandos más útiles y comunes de yt-dlp <br/><br/>
  Si deseas conocer todos los comandos disponibles de ```yt-dlp``` puedes ver la información del paqute dentro de la terminal utilizando el comando ```yt-dlp --help``` o ir a revisar directamente la documentación original https://github.com/yt-dlp/yt-dlp#usage-and-options <br/><br/>

  
    - 3.1 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.2 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.3 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.4 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.5 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.6 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.7 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.8 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.9 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    - 3.10 Descargar un video:
      ```
      yt-dlp URL
      ```
      Usado para descargar un video de la URL proporcionada.

      ---
    

### Documentación de comandos disponibles en la web
En esta pagina podemos ver algunos comandos que podremos utilizar para realizar la descarga de los videos en el caso de ralizar descargas con caracteristicas espesificas ademas de una documentación bastante completa
 - https://www.rapidseedbox.com/es/blog/yt-dlp-complete-guide#04

O leer la documentación oficial dejarnos de pendejadas 🤣🤣🤣
  - https://github.com/yt-dlp/yt-dlp#usage-and-options


