#  API para la Gestión de Eventos UG

¡Bienvenido al sistema backend de **Gestión de Eventos**! Esta es una API REST profesional, robusta y escalable desarrollada con **Spring Boot 4** y **Java 21**. El sistema cuenta con autenticación segura basada en tokens (JWT), persistencia en la nube utilizando PostgreSQL (Neon), mapeo eficiente de objetos con MapStruct y documentación automatizada con Swagger.

---

##  Descripción del Proyecto

Esta API ha sido diseñada como el motor central para una plataforma integral de **Gestión de Eventos**. Su propósito principal es administrar de manera eficiente el ciclo de vida completo de conferencias, congresos y reuniones, estructurando la información a través de un modelo de datos altamente relacional y optimizado.

La API permite operar de forma segura sobre cinco pilares fundamentales (Entidades de Dominio):
* **Usuarios (`User`) y Roles (`Role`):** Gestión de accesos, registro y control de permisos mediante roles dentro del sistema.
* **Eventos (`Event`):** Planificación y control de las actividades principales, fechas, horarios y logísticas.
* **Categorías (`Category`):** Clasificación y organización taxonómica de los eventos para facilitar búsquedas y filtrados.
* **Ponentes (`Speaker`):** Control del catálogo de expositores, conferencistas y profesionales asociados a cada sesión.

Desarrollada bajo una **arquitectura limpia orientada a capas**, la aplicación separa estrictamente las responsabilidades desde la recepción de la solicitud HTTP en los controladores, pasando por la validación de reglas de negocio en los servicios, hasta la persistencia final en la base de datos. Gracias al uso de hilos virtuales, la API está preparada para soportar una alta carga de peticiones concurrentes con un consumo mínimo de recursos.

---

##  Características Principales

* **Java 21 & Virtual Threads:** Aprovechamiento máximo del rendimiento nativo mediante hilos virtuales de Java para una concurrencia masiva y eficiente.
* **Seguridad Blindada:** Autenticación y autorización mediante **Spring Security** e implementando **JWT (JSON Web Tokens)**.
* **Arquitectura Limpia & Desacoplada:** Estructura organizada por capas (`Controller`, `Service`, `Repository`, `Domain/Entity`, `DTO`, `Mapper`, `Exception`).
* **Mapeo de Datos Eficiente:** Uso de **MapStruct** para transformaciones rápidas y limpias entre Entidades de Dominio y DTOs, evitando código repetitivo.
* **Persistencia Avanzada:** Integración con **Spring Data JPA** e Hibernate sobre base de datos **PostgreSQL** alojada de manera Serverless en **Neon**.
* **Documentación Interactiva:** Exposición de endpoints y esquemas mediante **Swagger UI** y **OpenAPI 3**.

---

##  Stack Tecnológico

* **Lenguaje:** Java 21
* **Framework Base:** Spring Boot 4.0.1 (Web MVC, Data JPA, Validation, Security)
* **Base de Datos:** PostgreSQL / H2 (en memoria para perfiles de pruebas)
* **Mapeadores:** MapStruct 1.6.3
* **Utilidades:** Project Lombok
* **Seguridad:** io.jsonwebtoken (JJWT 0.13.0)
* **Documentación:** Springdoc OpenAPI Starter 2.8.13

---

##  Estructura del Proyecto

El diseño de paquetes sigue las convenciones más estrictas de desarrollo en Spring Boot:

```text
src/main/java/com/gestion/eventos/api/
├── controller/          # Controladores REST (CategoryController, EventController, SpeakerController)
├── data/                # Clases de inicialización de datos o utilidades de persistencia estática
├── domain/              # Modelos de dominio / Entidades JPA (Category, Event, Role, Speaker, User)
├── dto/                 # Data Transfer Objects para requests y responses seguros
├── exception/           # Manejador global de excepciones y excepciones personalizadas
├── mapper/              # Interfaces de MapStruct para conversión entre entidades y DTOs
├── repository/          # Repositorios de Spring Data JPA para cada entidad
├── security/            # Configuración de Spring Security, filtros JWT y lógica de autenticación
│   ├── config/
│   ├── controller/
│   ├── dto/
│   ├── jwt/
│   └── service/
├── service/             # Capa de lógica de negocio (Interfaces e Implementaciones)
└── ApiApplication.java  # Clase principal (Punto de entrada de la aplicación)
