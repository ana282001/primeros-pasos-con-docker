# primeros-pasos-con-docker

Este proyecto demuestra cómo crear y ejecutar una imagen Docker que ejecuta código Python.

## Creación carpeta primeros_pasos_docker

- Dockerfile
- main.py

## Editar archivo main.py

!/usr/bin/env python3
print("¡Docker es mágico!")

## Editar archivo Dockerfile

Un archivo docker (dockerfile) comienza siempre importanto la imagen base. 
Utilizamos la palabra clave 'FROM' para hacerlo.
En nuestro ejemplo, queremos importar la imagen de python.
Así que escribimos 'python' para el nombre de la imagen y 'latest' para la versión.
FROM python:latest

Para lanzar nuestro código python, debemos importarlo a nuestra imagen.
Utilizamos la palabra clave 'COPY' para hacerlo.
El primer parámetro 'main.py' es el nombre del archivo en el host.
El segundo parámetro '/' es la ruta donde poner el archivo en la imagen.
Aquí ponemos el archivo en la carpeta raíz de la imagen. 
COPY main.py /

Necesitamos definir el comando a lanzar cuando vayamos a ejecutar la imagen.
Utilizamos la palabra clave 'CMD' para hacerlo.
El siguiente comando ejecutará "python ./main.py".
CMD [ "python", "./main.py" ]


## Crear la imagen Docker

docker build -t python-test .

docker images

docker run python-test
