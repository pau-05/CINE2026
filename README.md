# CINE2026

1️⃣ Preparar el proyecto

Ubiqué la ruta de mi proyecto del cine (C:\Users\paula\Documents\cine\CINE2025CURSO0GIT-main), donde se encuentran los archivos necesarios para hacer subir la página.


2️⃣ Crear el Dockerfile 🐳

Dentro de aquella ruta, he creado un archvio Dockerfile.txt y he escrito las siguientes líneas:

FROM nginx:alpine
COPY ./ /usr/share/nginx/html

Estas son las que le van a indicar a Nginx:
1. Que versión vamos a usar (en este caso la ligera)
2. Donde tiene que buscar el HTML para mostrarlo una vez iniciemos el Docker.

Luego de añadirle las líneas he tenido que quitarle la extensión .txt desde el explorador de archvios ya que sino, no funciona.


3️⃣ Construir la imagen de Docker 🏗️

Ahora abro el cmd y desde la ruta del proyecto (cd C:\Users\paula\Documents\cine\CINE2025CURSO0GIT-main) utilicé la siguiente línea: 
docker build -t mi-aplicacion-nginx .

Donde:

🔹 -t mi-aplicacion-nginx    → le da un nombre a la imagen.
🔹 .                         → le dice a Docker que use el Dockerfile de la carpeta en la que estoy.


4️⃣ Ejecutar el contenedor 🔥

Para ejecutar el Docker lo hice como de costumbre con el comando: docker run -d -p 8081:80 --name mi-app mi-aplicacion-nginx (aquí utilicé el puerto 8081 ya que el 8080 estaba ocupado por otro Docker).


5️⃣ Verificar que funciona ✅

Abrí el navegador y probé:
 
http://localhost:8081/ventaentradas.html   ← Página principal

Ya que en el proyecto hbaían varios HTMLs tuve que especificar cual de ellos quería que mostrara, ya que sino, mostraba la página default de Nginx.

Paula Tobar
