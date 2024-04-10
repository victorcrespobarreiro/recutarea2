## 1.Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Descargamos la imagen con el comando:

    docker pull httpd

![Alt text](images/Screenshot_20240410_182700.png)

Comprobamos que está en el equipo con el comando:

    docker images

![Alt text](images/Screenshot_20240410_182829.png)


## 2.Crea un contenedor con el nombre 'asir_httpd'


El contenedor se crea con:


      docker run -d --name asir_httpd httpd

![Alt text](images/Screenshot_20240410_183450.png)