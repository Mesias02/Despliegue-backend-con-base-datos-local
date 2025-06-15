# Despliegue backend con base datos local

## TAS8 - Despliegue backend con base de datos local

### 1. Título
Contenerización de una Aplicación Backend con PostgreSQL y pgAdmin utilizando Docker

![image](https://github.com/user-attachments/assets/7c76ca17-fadc-4d3b-9504-8059b5805926)

### 2. Tiempo de duración

El tiempo estimado para completar el despliegue fue de 200 minutos.

### 3. Fundamentos
Dockerfile
Un Dockerfile define los pasos para construir una imagen Docker. Es un archivo de texto que contiene un conjunto de instrucciones utilizadas para construir una imagen Docker. Este archivo permite personalizar el entorno de ejecución de la aplicación, partiendo de una imagen base y agregando las dependencias necesarias para su ejecución. A través del comando docker build, estas instrucciones se ejecutan en orden, generando una imagen compuesta por múltiples capas, cada una representando un paso del proceso de construcción (Docker Docs, n.d.).

![image](https://github.com/user-attachments/assets/aea108aa-47f7-49a3-9675-5889d42587c9)

La técnica de multi-stage build permite definir múltiples etapas dentro de un mismo Dockerfile, separando el entorno de construcción del entorno de ejecución. Esto es especialmente útil para reducir el tamaño de la imagen final y eliminar herramientas innecesarias o archivos temporales. Con este enfoque, los artefactos compilados en una etapa anterior se copian a una imagen limpia de producción, mejorando la seguridad y eficiencia del contenedor (Merkel, 2014; Docker Docs, n.d.).

Por ejemplo, al construir una aplicación con Spring Boot, se puede usar una imagen con Java y Maven para compilar el proyecto y luego copiar el archivo .jar resultante a una imagen basada solo en Java, lista para producción.

![image](https://github.com/user-attachments/assets/6530dbf8-7e68-40e2-bf70-84bd79c21658)

Optimización del Tamaño de la Imagen
Las imágenes Docker pueden volverse muy pesadas si incluyen dependencias innecesarias. Multi-stage build permite eliminar archivos temporales y herramientas de desarrollo antes de generar la imagen final, lo que resulta en imágenes más ligeras y rápidas de desplegar.

![image](https://github.com/user-attachments/assets/6cc810da-ed05-48f4-b661-2a9e4b48743e)

### 4. Conocimientos previos

Para realizar el despliegue, es necesario conocer:

Fundamentos de Spring Boot.

Comandos básicos de Docker.

Escritura y lectura de archivos Dockerfile.

Uso de .env para definir variables de configuración.

Fundamentos de bases de datos relacionales y PostgreSQL.

### 5. Objetivos a alcanzar

Contenerizar la aplicación backend mediante Docker.

Implementar multi-stage build para optimizar la imagen.

Configurar servicios de base de datos y administración con Docker Compose.

Gestionar variables de entorno con un archivo .env.

Verificar la conectividad entre el backend y PostgreSQL.

Validar el acceso a la base de datos desde pgAdmin.

### 6. Equipo necesario

Computador con Docker instalado.

Navegador web para acceder a pgAdmin.

Conexión a internet para obtener imágenes y documentación.

### 7. Material de apoyo

Documentación oficial de Docker.

Guía de Docker Cheatsheet.

Repositorio del proyecto backend.

Videos tutoriales para referencia.

### 8. Procedimiento

Pasos

Clonar el repositorio del proyecto backend.
----
![image](https://github.com/user-attachments/assets/f6bc9c0e-bada-476e-93cd-ee301f6b01d4)
----
Crear archivo .env con las variables necesarias.
----
![image](https://github.com/user-attachments/assets/a2f04274-c07b-4ebd-a4aa-0f1a92e0f476)
----
Definir el archivo Dockerfile
----
![image](https://github.com/user-attachments/assets/36036b20-86ec-40a4-8e31-8c78a97d7c55)
----
Configurar docker-compose.yml para PostgreSQL y pgAdmin.
----
![image](https://github.com/user-attachments/assets/3a84b2f7-1ded-4e00-8f03-bb50b08ef8ca)
----
Levantar los contenedores con docker-compose up --build -d.
----
![image](https://github.com/user-attachments/assets/27e630d2-8b39-4265-bf9b-db36c9a46d33)
-----
Acceder a pgAdmin y conectar con PostgreSQL correctamente.
----
![image](https://github.com/user-attachments/assets/6022aced-4825-4265-830c-ea1a0b04ea45)
---
![image](https://github.com/user-attachments/assets/27a64138-4e5d-48e7-9231-4fd36f83bfa6)
---
Demostración en el localhost
![image](https://github.com/user-attachments/assets/02de7daa-b1d3-4d9a-bc1b-1542bf9ed6c7)
---
![image](https://github.com/user-attachments/assets/f5a61d96-9115-49c6-87c9-621f0f177712)


### 9. Resultados esperados

La aplicación backend ha sido contenerizada con éxito usando Dockerfile y multi-stage build.

Se generó una imagen ligera y optimizada.

Se ejecutó Docker Compose para levantar los servicios PostgreSQL y pgAdmin.

Se verificó la correcta comunicación entre la aplicación y la base de datos con logs de Spring Boot.

La conexión desde pgAdmin fue establecida, garantizando persistencia y acceso a la base de datos.

Capturas de pantalla evidencian el proceso desde la clonación hasta el despliegue exitoso.

### 10. Bibliografía

Documentación oficial de Docker sobre Multi-stage Builds: Explica cómo optimizar imágenes Docker utilizando múltiples etapas en el Dockerfile.
Stack Overflow - Cómo dividir un Dockerfile en múltiples archivos: Discusión sobre cómo estructurar Dockerfiles en proyectos complejos.
KeepCoding - ¿Qué es Docker Multi-stage Build?: Explicación detallada sobre el concepto y su evolución en Docker.

Docker Docs. (n.d.). Use multi-stage builds. Docker Documentation. Recuperado el 15 de junio de 2025, de https://docs.docker.com/develop/develop-images/multistage-build/

Merkel, D. (2014). Docker: Lightweight Linux containers for consistent development and deployment. Linux Journal, 2014(239). https://www.linuxjournal.com/content/docker-lightweight-linux-containers-consistent-development-and-deployment


