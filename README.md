# youtube-dlp: Guía Completa de Uso e Instalación

![Logo de yt-dlp](./img/yt-dlp-tutorial-removebg-preview.png "Logo de yt-dlp")

## Introducción

youtube-dlp es una herramienta de línea de comandos potente y versátil para descargar videos de YouTube y otros sitios web de video. Es un fork mejorado del popular youtube-dl, con características adicionales y mejor rendimiento.

Esta guía, creada por Sicer Andres Brito Gutierrez, proporciona instrucciones detalladas sobre la instalación, uso básico y avanzado de youtube-dlp.

## Tabla de Contenidos

1. [Comandos Más Útiles](#comandos-más-útiles)
2. [Instalación](#instalación)
3. [Comandos Comunes](#comandos-comunes)
4. [Uso Avanzado](#uso-avanzado)
5. [Mejores Prácticas](#mejores-prácticas)
6. [Solución de Problemas](#solución-de-problemas)
7. [Recursos Adicionales](#recursos-adicionales)

## Comandos Más Útiles

Estos son los comandos que más utilizarás:

1. Descargar un video con la mejor calidad disponible:
   ```
   yt-dlp -f "bestvideo+bestaudio" --merge-output-format mp4 URL
   ```

2. Descargar solo el audio con la mejor calidad disponible:
   ```
   yt-dlp -f bestaudio --extract-audio --audio-format mp3 URL
   ```

## Instalación

### Windows

#### Opción 1: Archivo `.exe`
Descarga el archivo ejecutable directamente desde [el repositorio oficial](https://github.com/yt-dlp/yt-dlp/releases).

#### Opción 2: Usando Chocolatey

1. Instala Chocolatey:
   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```

2. Instala youtube-dlp:
   ```
   choco install yt-dlp
   ```

3. Instala ffmpeg (necesario para algunas funciones):
   ```
   choco install ffmpeg
   ```

### Linux y macOS

Usa pip para instalar youtube-dlp:

```
pip install yt-dlp
```

## Comandos Comunes

1. Descargar un video:
   ```
   yt-dlp URL
   ```

2. Listar formatos disponibles:
   ```
   yt-dlp --list-formats URL
   ```

3. Seleccionar el mejor video y audio y combinar:
   ```
   yt-dlp -f bestvideo+bestaudio --merge-output-format mp4 URL
   ```

4. Descargar solo el audio:
   ```
   yt-dlp -f bestaudio --extract-audio --audio-format mp3 URL
   ```

5. Especificar el nombre del archivo de salida:
   ```
   yt-dlp -o "NOMBRE_DEL_ARCHIVO.%(ext)s" URL
   ```

6. Descargar una lista de reproducción completa:
   ```
   yt-dlp --yes-playlist URL
   ```

7. Limitar la velocidad de descarga:
   ```
   yt-dlp --limit-rate RATE URL
   ```

8. Descargar subtítulos:
   ```
   yt-dlp --write-sub --sub-lang LANG URL
   ```

9. Incrustar subtítulos:
   ```
   yt-dlp --embed-subs URL
   ```

10. Usar archivo de cookies:
    ```
    yt-dlp --cookies COOKIES_FILE URL
    ```

## Uso Avanzado

### Cómo utilizar el comando `--list-formats`

El comando `--list-formats` muestra todos los formatos disponibles para un video. Aquí te explicamos cómo interpretarlo:

- Para video: Fíjate en las columnas `RESOLUTION` y `TBR (Total Bitrate)`.
- Para audio: Observa las columnas `ACODEC` y `ABR (Audio Bitrate)`.

Ejemplo de salida del comando `--list-formats`:

![Ejemplo de list-formats](./img/list-formats.PNG)

#### Selección de formatos de video

Al seleccionar un formato de video, presta atención a las columnas `RESOLUTION`, `TBR (Total Bitrate)`, y `FILESIZE`. Evita los archivos con el símbolo `~` en la columna `FILESIZE` si buscas una buena relación calidad/peso.

![Selección de formatos de video](./img/list-formats-video.PNG)

En este ejemplo, el `ID 398` sería una buena opción considerando la calidad y el tamaño del archivo.

Para descargar el video seleccionado:
```
yt-dlp -f "398" URL
```

#### Selección de formatos de audio

Para el audio, enfócate en las columnas `ACODEC` y `ABR (Audio Bitrate)`.

![Selección de formatos de audio](./img/list-formats-audio.PNG)

En este caso, el `ID 251` sería la mejor opción debido a la calidad del audio (128k).

Para descargar el audio seleccionado:
```
yt-dlp -f "251" URL
```

#### Combinando video y audio

Para descargar y combinar los mejores formatos de video y audio:
```
yt-dlp -f "bestvideo+bestaudio" --merge-output-format mp4 URL
```

O si quieres limitar la resolución:
```
yt-dlp -f "bestvideo[height<=720]+bestaudio/best[height<=720]" URL
```

### Descarga de Playlists y Canales

- Descargar una playlist completa:
  ```
  yt-dlp -i https://www.youtube.com/playlist?list=PLxxxxxxxxxxxxxxxx
  ```

- Descargar los últimos 20 videos de un canal:
  ```
  yt-dlp -i --playlist-reverse --playlist-end 20 https://www.youtube.com/channel/UCxxxxxxxxxxxxxxxx
  ```

## Mejores Prácticas

1. Usa siempre comillas para los argumentos de `-f` para evitar problemas de interpretación.
2. Actualiza youtube-dlp regularmente para obtener las últimas características y correcciones.
3. Utiliza `--restrict-filenames` si estás trabajando en diferentes sistemas operativos para evitar problemas con caracteres especiales.
4. Considera usar `--download-archive FILE` para evitar descargar videos duplicados en múltiples sesiones.

> [!TIP]
> **DATO A TENER EN CUENTA:** Aunque la mayoría de las veces el no utilizar las comillas para los argumentos de `-f` como `yt-dlp -f "251" URL` a `yt-dlp -f 251 URL` pueden llegar a funcionar a la hora de ejecutarlos en la terminal se recomienda usar las comillas ya que garantiza que todo el argumento de la opción `-f` se interprete correctamente como un único argumento, especialmente en sistemas `Unix` como `Linux` o `macOS` donde es más común que se requieran comillas en tales casos.

## Solución de Problemas

1. **Error: "Unable to extract video data"**
   - Asegúrate de tener la última versión de youtube-dlp.
   - Intenta usar el flag `--no-check-certificate`.

2. **Descarga lenta**
   - Prueba con diferentes servidores usando `--force-ipv4` o `--force-ipv6`.
   - Usa `--limit-rate` para evitar throttling.

3. **Problemas con la fusión de audio y video**
   - Asegúrate de tener ffmpeg instalado y actualizado.
   - Usa `--verbose` para obtener más información sobre el error.

## Recursos Adicionales

- [Documentación oficial de youtube-dlp](https://github.com/yt-dlp/yt-dlp#usage-and-options)
- [Guía completa en RapidSeedbox](https://www.rapidseedbox.com/es/blog/yt-dlp-complete-guide#04)

---

Esta documentación fue creada por Sicer Andres Brito Gutierrez. Si encuentras errores o tienes sugerencias, por favor crea un issue en el repositorio correspondiente.
