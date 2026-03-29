# 🚀 Plataforma de Gestión Dinámica de Microservicios

## 📝 Descripción del Proyecto
[cite_start]Esta plataforma permite a los desarrolladores crear, administrar y eliminar microservicios de forma instantánea[cite: 4, 21]. [cite_start]A través de un Dashboard Web, se puede escribir código fuente, elegir un lenguaje (Python o Node.js) y el sistema se encarga de empaquetar, construir y desplegar un contenedor Docker independiente para ese servicio[cite: 8, 18, 19, 23, 27, 28].

### Objetivos del Proyecto:
* [cite_start]**Creación Dinámica:** Generar servicios sin intervención manual en el servidor, pegando el código en el dashboard[cite: 11, 18].
* [cite_start]**Soporte Multi-lenguaje:** Compatibilidad con Python y Node.js[cite: 19].
* [cite_start]**Administración Visual:** Panel para listar, habilitar, deshabilitar y eliminar contenedores[cite: 21].
* [cite_start]**Aislamiento Total:** Cada microservicio vive en su propio entorno aislado y se ejecuta en su propio contenedor Docker[cite: 8, 30].

## 👥 Integrantes del Grupo
* [Nombre Integrante 1]
* [Nombre Integrante 2]
* [Nombre Integrante 3]
* [Nombre Integrante 4]

## 🏗️ Arquitectura del Sistema
El sistema utiliza una arquitectura **DooD (Docker-out-of-Docker)**. El contenedor de la plataforma se comunica con el motor de Docker del sistema anfitrión a través del archivo `/var/run/docker.sock` para desplegar automáticamente los contenedores de los microservicios.

```mermaid
graph TD
    subgraph Usuario
        U[Navegador Web / Dashboard]
    end

    subgraph "Contenedor: Plataforma (Puerto 3000)"
        D[Dashboard HTML/JS]
        B[Backend Flask - main.py]
    end

    subgraph "Infraestructura Host"
        S[Docker Socket]
        DE[Docker Engine]
    end

    subgraph "Microservicios Creados"
        M1[Contenedor: Python Service]
        M2[Contenedor: Node.js Service]
    end

    U -->|1. Envía Código| D
    D -->|2. Solicitud API| B
    B -->|3. Comandos Docker| S
    S -->|4. Construcción/Ejecución| DE
    DE -->|5. Despliegue| M1
    DE -->|5. Despliegue| M2
    U -.->|6. Consumo JSON| M1
    U -.->|6. Consumo JSON| M2
