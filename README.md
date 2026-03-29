# 🚀 Plataforma de Gestión Dinámica de Microservicios

## 📝 Descripción del Proyecto
[cite_start]Este proyecto consiste en una plataforma diseñada para la administración dinámica de microservicios utilizando contenedores Docker[cite: 59, 61]. [cite_start]A través de un dashboard web, los usuarios pueden crear, listar, habilitar, deshabilitar y eliminar microservicios en tiempo real[cite: 62, 79]. 

[cite_start]Cada microservicio se define como una aplicación independiente empaquetada en su propio contenedor, que expone un endpoint HTTP y retorna respuestas en formato JSON[cite: 65, 66, 67, 68].

## 🏗️ Arquitectura del Sistema
La solución implementa un modelo de **Docker-out-of-Docker (DooD)**, permitiendo que el contenedor de la plataforma gestione otros contenedores en el host.

1.  **Dashboard (Frontend):** Interfaz desarrollada en HTML/JS para la gestión de servicios.
2.  **Orquestador (Backend):** Servidor Flask en Python 3.11 que interactúa con el Docker Engine a través del socket de Unix (`/var/run/docker.sock`).
3.  [cite_start]**Docker Engine:** Motor encargado de construir las imágenes y desplegar los contenedores de forma aislada[cite: 66, 85, 86].

> **[INSERTE AQUÍ SU DIAGRAMA DE ARQUITECTURA]**

## 🛠️ Tecnologías Utilizadas
* **Lenguaje Base:** Python 3.11 (Flask).
* [cite_start]**Contenerización:** Docker y Docker Compose[cite: 61].
* **Lenguajes Soportados:** Python y Node.js.
* **Gestión de Red:** Exposición automática de puertos dinámicos para cada servicio.

## 🚀 Instalación y Despliegue
[cite_start]Para levantar la plataforma completa, asegúrese de tener Docker instalado y ejecute el siguiente comando en la raíz del proyecto[cite: 90, 91]:

```bash
docker-compose up
