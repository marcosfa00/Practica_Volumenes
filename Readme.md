# EXPLICACION VOLUMENES CON DOCKER

Creamos un nuevo Repositorio en GITHub llamado **Practica Volumenes**
aquí es donde subiremos esta tarea y su explicación.


Descarga la imagen 'httpd' y comprueba que está en tu equipo.
crea un contenedor con el nombre 'dam_httpd'.
---

Para hacer lo anterior debemos emplear el siguiente comando de docker

        docker run -dit --name dam_httpd httpd:2.4

este comando nos crea el siguiente contenedor:

        f659c860ff8056fa15fcbcba6ea40ce12beefd49543453373495df27fe858c49


### comprobamos

Con el comando **docker ps**


| CONTAINER ID   | IMAGE     | COMMAND            | CREATED            | STATUS            | PORTS      | NAMES    |
| --------------- | --------- | ------------------ | ------------------ | ------------------ | ---------- | -------- |
| f659c860ff80    | httpd:2.4 | "httpd-foreground" | About a minute ago | Up About a minute | 80/tcp     | dam_httpd |



Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.
---
Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.
---        
        Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/


Bien cómo ya teniamos creado el contenedor, ahora no podemos redirigir los puertos, esto se debió hacer anterior mente, por lo que debemos parar el contenedor y finalmente borrarlo, para poder volverlo a crear con estos nuevos parámetros:

**Borramos**

        docker stop dam_httpd
        docker rm dam_httpd

**Lo creamos de Nuevo**
Para esto debemos crear anteriormente la carpeta **htdocs** para montar nuestra web sobre el contenedor, de esta manera podremos ejecutar un unico comando

     docker run -dit --name dam_httpd -p 8080:80 -v /Users/marcosfa/Documents/Dam2/SXE/boletin2/htdocs:/usr/local/apache2/htdocs/ httpd:2.4

**Nuevo Contenedor**
Ahora procederemos a crear un nuevo Contenedor con otros puertos, pero con el mismo volumen

**Utilizaremso los puertos 80:9080**

    docker run -dit --name dam_web2 -p 9080:80 -v /Users/marcosfa/Documents/Dam2/SXE/boletin2/htdocs:/usr/local/apache2/htdocs/ httpd:2.4




