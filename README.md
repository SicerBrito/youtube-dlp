# youtube-dlp
Manual de manejo ademas de instrucciones y recomendaciones

## Instalación

### Chocolatey
Esta fue la forma mas facil en la que yo lo pude descargar y fue con el chocolatey ya que esta disponible dentro de este gestor de paquetes en linea
  - Instalacion de chocolatey (Recordar que se hace en el Powershell como administrativo). Documentación https://chocolatey.org/install  
  Con PowerShell, debe asegurarse de que Get-ExecutionPolicy no esté restringido. Se sugiere usar Bypass para omitir la política para instalar cosas o AllSigned para obtener un poco más de seguridad.
  Correr ```Get-ExecutionPolicy```. Si regresa Restricted, ejecute ```Set-ExecutionPolicy AllSigned``` o ```Set-ExecutionPolicy Bypass -Scope Process```. 
    ```
    Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
    ```
    Si no se ve ningún error, ¡está listo para usar Chocolatey! Puedes escribir ```choco``` o ```choco -?``` para verificar la instalacion

  - Y instalar ahora si el youtube-dlp
    ```
    choco install yt-dlp
    ```
