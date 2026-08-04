\---

date: August 2026

title: "Sistema ERP - Documentación de Arquitectura (arc42)"

\---



\# Introduction and Goals



\## Requirements Overview



El proyecto consiste en el diseño de la arquitectura de un Sistema ERP (Enterprise Resource Planning) orientado a la gestión de los principales procesos administrativos de una empresa.



El sistema estará compuesto por los siguientes módulos:



\- Compras

\- Facturación

\- Stock/Costos

\- Activos Fijos

\- Empleados

\- EIS (Executive Information System)



Para el desarrollo del presente taller se documentará principalmente el Módulo de Compras, el cual permitirá administrar productos, proveedores y órdenes de compra.



\### Requisitos Funcionales



\- Registrar productos.

\- Registrar proveedores.

\- Generar órdenes de compra.

\- Consultar historial de compras.

\- Actualizar información de productos.

\- Aprobar órdenes de compra.



\---



\## Quality Goals



Los principales objetivos de calidad del sistema son:



\- Disponibilidad del sistema.

\- Integridad de la información.

\- Seguridad mediante autenticación de usuarios.

\- Escalabilidad para agregar nuevos módulos.

\- Facilidad de mantenimiento.

\- Alto rendimiento en las consultas.



\---



\## Stakeholders



| Rol | Contacto | Expectativas |

|------|----------|--------------|

| Administrador de Compras | Empresa | Gestionar productos, proveedores y compras. |

| Gerente | Empresa | Consultar indicadores y reportes. |

| Administrador del Sistema | Equipo de Desarrollo | Mantener la disponibilidad del sistema. |

| Proveedor | Empresa Externa | Recibir órdenes de compra correctamente. |



\---



\# Architecture Constraints



\## Restricciones Tecnológicas



Backend



\- Java 21

\- Spring Boot



Frontend



\- React



Base de Datos



\- PostgreSQL



Arquitectura



\- Monolítica



Comunicación



\- API REST



Diagramas



\- PlantUML



Control de versiones



\- GitHub



Gestión del proyecto



\- Jira



Documentación



\- arc42



\---



\# Context and Scope



\## Business Context



El Sistema ERP será utilizado por diferentes usuarios de la empresa para administrar sus procesos internos.



Los usuarios principales son:



\- Administrador de Compras

\- Gerente

\- Administrador del Sistema



Además, el ERP intercambiará información con un Sistema Contable Externo.



\### Diagrama de Contexto



!\[Diagrama C1](images/c1\_context.png)





\---



\## Technical Context



Los usuarios accederán mediante un navegador web.



El Frontend se comunicará con el Backend mediante HTTPS utilizando servicios REST.



El Backend accederá a PostgreSQL mediante JDBC.



\---



\# Solution Strategy



Para simplificar el desarrollo del proyecto se utilizará una arquitectura monolítica.



La interfaz de usuario será implementada utilizando React.



La lógica de negocio será implementada en Spring Boot.



Toda la información será almacenada en PostgreSQL.



La documentación seguirá el estándar arc42.



\---



\# Building Block View



\## Whitebox Overall System



\### Diagrama de Contenedores



!\[Diagrama C2](images/c2\_containers.png)



\### Motivation



El sistema se divide en tres componentes principales para separar responsabilidades y facilitar el mantenimiento.



\### Building Blocks



\### Frontend (React)



Responsabilidades



\- Mostrar la interfaz gráfica.

\- Capturar información del usuario.

\- Consumir la API REST.



\### Backend (Spring Boot)



Responsabilidades



\- Validar la información.

\- Ejecutar las reglas de negocio.

\- Gestionar productos.

\- Gestionar proveedores.

\- Gestionar órdenes de compra.

\- Comunicarse con PostgreSQL.



\### Base de Datos (PostgreSQL)



Responsabilidades



\- Almacenar productos.

\- Almacenar proveedores.

\- Almacenar órdenes de compra.

\- Mantener la integridad de la información.



\### Interfaces



Frontend → Backend



REST API



Backend → PostgreSQL



JDBC



\---



\## Level 2



\### Frontend



\- Login

\- Gestión de Productos

\- Gestión de Proveedores

\- Gestión de Compras



\### Backend



\- API Productos

\- API Proveedores

\- API Compras



\### Base de Datos



\- Tabla Productos

\- Tabla Proveedores

\- Tabla OrdenCompra

\- Tabla DetalleCompra



\---



\# Runtime View



\## Escenario



Registrar un Producto



\### Flujo



1\. El Administrador abre el formulario de productos.



2\. Ingresa la información del producto.



3\. El Frontend envía la información al Backend.



4\. El Backend valida los datos.



5\. El Backend guarda el producto en PostgreSQL.



6\. PostgreSQL confirma el registro.



7\. El Backend responde al Frontend.



8\. El Frontend muestra un mensaje indicando que el producto fue registrado correctamente.



\### Diagrama de Secuencia



!\[Diagrama de Secuencia](images/sequence\_register\_product.png)



\---



\# Deployment View



\## Infrastructure Level 1



El sistema será desplegado sobre un servidor Linux.



Los usuarios accederán mediante un navegador web utilizando HTTPS.



Componentes:



\- Navegador Web

\- Servidor Spring Boot

\- PostgreSQL



\### Arquitectura Física



Cliente



↓



Navegador Web



↓



Servidor Spring Boot



↓



PostgreSQL



\---



\# Cross-cutting Concepts



\## Seguridad



El acceso al sistema requerirá autenticación mediante usuario y contraseña.



Los permisos dependerán del rol asignado.



\---



\## Persistencia



Toda la información será almacenada en PostgreSQL.



\---



\## API REST



La comunicación entre Frontend y Backend se realizará mediante servicios REST utilizando JSON.



\---



\## Manejo de Errores



Las validaciones impedirán el registro de información incompleta o incorrecta.



Los errores serán mostrados mediante mensajes descriptivos.



\---



\# Architecture Decisions



Las principales decisiones arquitectónicas son:



\- Arquitectura Monolítica.

\- Backend desarrollado con Spring Boot.

\- Frontend desarrollado con React.

\- PostgreSQL como base de datos.

\- GitHub como repositorio.

\- Jira para la gestión del proyecto.

\- PlantUML para los diagramas.

\- Documentación siguiendo arc42.



\---



\# Quality Requirements



\## Requisitos de Calidad



Disponibilidad



El sistema debe estar disponible el 99% del tiempo.



Seguridad



Solo usuarios autenticados podrán acceder.



Escalabilidad



El sistema permitirá agregar nuevos módulos.



Rendimiento



Las consultas deberán responder en menos de tres segundos.



Mantenibilidad



El código seguirá buenas prácticas para facilitar futuras modificaciones.



\---



\# Risks and Technical Debts



\## Riesgos



\- Retrasos en el desarrollo.

\- Errores en la integración entre Frontend y Backend.

\- Información inconsistente por registros duplicados.



\## Deuda Técnica



\- No se implementará autenticación con OAuth.

\- No se utilizarán microservicios.

\- No se implementará balanceo de carga.



Estas funcionalidades podrán desarrollarse en futuras versiones.



\---



\# Glossary



| Término | Definición |

|----------|------------|

| ERP | Sistema de Planificación de Recursos Empresariales. |

| Producto | Bien registrado para ser adquirido por la empresa. |

| Proveedor | Persona o empresa que suministra productos. |

| Orden de Compra | Documento utilizado para solicitar productos a un proveedor. |

| Inventario | Conjunto de productos disponibles en la empresa. |

| Factura | Documento que registra una transacción comercial. |

| API REST | Servicio utilizado para comunicar el Frontend con el Backend. |

| PostgreSQL | Sistema Gestor de Base de Datos utilizado por el ERP. |

| Spring Boot | Framework utilizado para desarrollar el Backend. |

| React | Framework utilizado para desarrollar el Frontend. |

| Administrador de Compras | Usuario responsable de gestionar productos, proveedores y órdenes de compra. |

| Gerente | Usuario encargado de consultar indicadores y reportes. |



