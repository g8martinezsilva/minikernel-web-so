# minikernel-web-so

Simulador web de un **minikernel con arquitectura de microkernel**, desarrollado para la asignatura Sistemas Operativos (Grupo 82) de la Universidad Distrital Francisco José de Caldas.

## Integrantes

| Nombre | Código |
|---|---|
| Gabriela Martínez Silva | 20231020205 |
| Carol Stefanya Velasco Rodríguez | 20231020215 |
| Kaleth Molina Díaz | 20232020096 |
| Camilo Andrés Gamez Camino | 20231020193 |

Docente: Gerald Breek Fuenmayor Rivadeneira

## Arquitectura

El núcleo (`Kernel`) solo ofrece planificación básica de CPU, enrutamiento de mensajes IPC e interrupciones. Los servicios viven en cinco servidores en espacio de usuario que se comunican únicamente mediante `IPCMessage`:

- `ProcessServer`: procesos, PCB, planificación, IPC, semáforos y algoritmo del Banquero.
- `MemoryServer`: particiones fijas y variables (First, Best y Worst-Fit) y fragmentación.
- `FileServer`: sistema de archivos jerárquico (FAT o inodos) y operaciones CRUD.
- `IOServer`: disco (FCFS, SSTF, SCAN, C-SCAN), interrupciones, DMA y red simulada.
- `SecurityServer`: usuarios, roles, ACL y auditoría.

Capas: cliente web, API Spring Boot (WebSocket y REST), servidores, microkernel y hardware simulado.

## Tecnologías previstas

- Java 17 y Spring Boot 3
- WebSocket (STOMP) y REST
- Spring Data JPA con H2 (desarrollo) o PostgreSQL
- Thymeleaf y JavaScript para el cliente web

## Estructura del repositorio

```
backend/    Servidor Spring Boot: Kernel y servidores (un paquete por servidor)
frontend/   Cliente web
docs/       Documentación y diagramas
  avance1/  Informe del Avance 1 (LaTeX, PDF y figuras)
```

## Documentación

- Informe del Avance 1: `docs/avance1/Avance1_Minikernel.pdf` (fuente en `Avance1_Minikernel.tex`; las figuras están en `docs/avance1/figuras/`).
- Diagramas editables: `docs/Avance1_Diagramas.drawio` y código PlantUML en `docs/Avance1_Diagramas_todos.puml`.

## Estado

| Entrega | Contenido | Estado |
|---|---|---|
| Avance 1 | Requerimientos, casos de uso, diagramas de actividad y de clases | Entregado |
| Avance 2 | Prototipo web de Procesos y Memoria | Pendiente |
| Entrega final | Archivos, E/S, Seguridad, persistencia y pruebas | Pendiente |

## Cómo ejecutar

Pendiente: se agregará cuando exista el código del backend (por ejemplo, `mvn spring-boot:run`).
