# TryHackmeWriteUpSChallege_REvil_Corp

** REvilCorp TryHackMe Writeup

Este writeup documenta la resolución del desafío REvilCorp de TryHackMe, utilizando la herramienta Redline de FireEye para el análisis forense de un host comprometido.

# Escenario del Desafío

Uno de los empleados de Lockman Group contactó al departamento de TI debido a que todos sus archivos habían cambiado a una extensión desconocida. Al revisar la estación de trabajo, el técnico de TI determinó que se trataba de un ataque de ransomware y escaló el caso al equipo de respuesta a incidentes.

## Herramienta Utilizada: FireEye Redline

Redline es una herramienta gratuita de FireEye que permite investigar actividades maliciosas en endpoints mediante el análisis de archivos, memoria y otros indicadores de compromiso (IoCs). Entre sus capacidades destacan:

Recopilación de datos de registro (Windows)

Análisis de procesos en ejecución

Revisión de historial del navegador

Búsqueda de cadenas sospechosas

Análisis de archivos descargados

También se puede complementar con FireEye IOC Editor para gestionar indicadores de compromiso.

## Investigación del Punto Final Comprometido

1. Identificación del Usuario Afectado

Mediante System Information en Redline, identificamos el nombre del usuario comprometido.



2. Sistema Operativo del Host Comprometido

Se obtiene desde System Information dentro de Redline.

3. Identificación del Ejecutable Malicioso

Analizamos los archivos descargados en el sistema para determinar qué ejecutable malicioso fue abierto por el usuario.

4. URL de Descarga del Binario Malicioso

La URL completa se encuentra en el menú de descargas dentro de Redline.

5. Hash MD5 del Binario Malicioso

Ubicamos el archivo dentro del File System en la carpeta de descargas y obtenemos su hash MD5.

6. Tamaño del Binario en KB

El tamaño se encuentra en la sección de detalles dentro del File Path.

7. Extensión de Archivos Renombrados

Identificamos los archivos afectados validando su modificación en el File System.

8. Número de Archivos Renombrados

Utilizamos el timeline para filtrar eventos de modificación de archivos.

9. Ruta Completa del Fondo de Pantalla Cambiado por el Atacante

Filtramos archivos BMP creados en el período del ataque.

10. Nota de Rescate en el Escritorio

Ubicamos el archivo de la nota de rescate en la carpeta del escritorio del usuario.

11. Archivo en "Enlaces para Estados Unidos"

Exploramos la carpeta C:\Users\John Coleman\Favorites\ y localizamos un archivo con nombre en español.

12. Archivo Oculto con 0 Bytes en el Escritorio

Buscamos archivos ocultos dentro del escritorio del usuario.

13. Hash MD5 del Descifrador Fallido

Utilizamos el historial del navegador para identificar la descarga del descifrador y luego obtenemos su hash MD5 desde la carpeta de descargas o escritorio.

Este writeup busca servir de guía para replicar el análisis en la plataforma de TryHackMe, permitiendo a los usuarios mejorar sus habilidades en respuesta a incidentes y análisis forense con Redline.
