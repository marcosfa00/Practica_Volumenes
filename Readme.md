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







