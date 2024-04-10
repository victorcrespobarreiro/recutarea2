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

## 3.Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.


Utilizamos el comando:


       docker run -d --name asir_httpd -p 8000:80 httpd

![Alt text](images/Screenshot_20240410_183829.png)

## 4.Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.

Utilizamos el siguiente comando:

       docker run -d --name asir_httpd -p 8000:80 -v "$PWD/htdocs:/usr/local/apache2/htdocs/" httpd

![Alt text](images/Screenshot_20240410_184058.png)

## 5.Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.

Creamos el html dentro de la carpeta htdocs:

![Alt text](images/Screenshot_20240410_184416.png)



Y comprobamos que funciona escribiendo localhost:8000 en el navegador:

![Alt text](images/Screenshot_20240410_184521.png)

## 6.Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000.




Creamos el contenedor 'asir_web1' con:




       docker run -d --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

![Alt text](images/Screenshot_20240410_185055.png)

## 7.Utiliza Code para hacer un hola mundo en html.

Html creado en visual code studio:


![Alt text](images/Screenshot_20240410_185432.png)

## 8.Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.




Creamos otro contenedor con el puerto 9080 con el comando:




       docker run -d --name asir_web2 -p 9080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

![Alt text](images/Screenshot_20240410_185922.png)

## 9 y 10. Comprueba que los dos servidores muestren la misma página.

Comprobamos que muestren el mismo "hola mundo" poniendo en el navegador:

         localhost:8000

![Alt text](images/Screenshot_20240410_190158.png)


   localhost:9080

![Alt text](images/Screenshot_20240410_190243.png)
