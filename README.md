# Sistema ERP - Documentación de Arquitectura (arc42)

## Descripción

Este repositorio contiene la documentación de arquitectura de un Sistema ERP desarrollada como parte del taller de Ingeniería de Software de la Universidad Manuela Beltrán.

La documentación sigue el estándar **arc42** e incluye la definición de la arquitectura del sistema, historias de usuario, criterios de aceptación, priorización del backlog y diagramas UML elaborados con PlantUML.

El proyecto está enfocado principalmente en el **Módulo de Compras**, sin dejar de considerar la arquitectura general del ERP.

---

# Módulos del ERP

- Módulo de Compras
- Módulo de Facturación
- Módulo Stock / Costos
- Módulo Activos Fijos
- Módulo Empleados
- Módulo EIS (Executive Information System)

---

# Objetivo

Diseñar la arquitectura de un Sistema ERP utilizando el estándar **arc42**, aplicando buenas prácticas de documentación de software y modelado mediante diagramas UML y C4.

---

# Tecnologías Utilizadas

## Desarrollo

- Java 21
- Spring Boot
- React
- PostgreSQL

## Gestión del Proyecto

- Jira
- GitHub

## Documentación

- arc42
- PlantUML
- Markdown

---

# Arquitectura

El sistema sigue una arquitectura **Monolítica** compuesta por:

- Frontend (React)
- Backend (Spring Boot)
- Base de Datos PostgreSQL

La comunicación entre el Frontend y el Backend se realiza mediante una API REST.

---

# Funcionalidades del Módulo de Compras

- Registro de Productos
- Registro de Proveedores
- Generación de Órdenes de Compra
- Consulta del Historial de Compras
- Actualización de Productos
- Aprobación de Órdenes de Compra

---

# Diagramas Incluidos

- Diagrama de Contexto (C1)
- Diagrama de Contenedores (C2)
- Diagrama de Secuencia
- Modelo Entidad-Relación (MER)

---

# Gestión del Proyecto

El proyecto fue gestionado mediante Jira, donde se definieron:

- Épicas
- Historias de Usuario
- Criterios de Aceptación
- Priorización MoSCoW

---

# Estructura del Proyecto

```text
.
├── README.md
├── docs
│   ├── images
│   │   ├── c1_context.png
│   │   ├── c2_containers.png
│   │   ├── sequence_register_product.png
│   │   └── mer.png
│   │
│   ├── 01_introduction_and_goals.md
│   ├── 02_architecture_constraints.md
│   ├── 03_system_scope_and_context.md
│   ├── 05_building_block_view.md
│   ├── 06_runtime_view.md
│   ├── 07_deployment_view.md
│   └── 10_glossary.md
```

---

# Autor

**Julian Andres Peñuela Alfonso**

Estudiante de Ingeniería de Software

Universidad Manuela Beltrán

---

# Enlaces

## Repositorio GitHub

https://github.com/andresalfnso3-sys/erp-software-architecture

## Tablero Jira

https://andresalfnso3.atlassian.net/jira/software/projects/KAN/boards/2?filter=&groupBy=none

---

# Herramientas Utilizadas

- GitHub
- Jira
- PlantUML
- arc42
- Markdown
- Visual Studio Code

---

# Universidad

**Universidad Manuela Beltrán**

**Programa:** Ingeniería de Software

**Asignatura:** Arquitectura de Software

**Actividad:** Taller de Documentación de Arquitectura utilizando arc42

**Autor:** Julian Andres Peñuela Alfonso
