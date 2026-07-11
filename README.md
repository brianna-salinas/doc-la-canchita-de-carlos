<div align="center">

<br>

## La Canchita de Carlos

# Sistema de Gestión de Alquiler de Canchas
### Documento de Producto — Propuesta 1 (Uso Interno)

<br>

#  Cliente: Carlos Maldonado

## Desarrolladora: Brianna Salinas

*Plazo: 2 semanas (documentación, diseño, prototipo, desarrollo, pruebas y despliegue)*

<br>

**Fecha**

### **Julio 2026**

<br>

</div>

---

# Tabla de Contenidos

[Capítulo I: Introducción](#capítulo-i-introducción)
* [1.1. Perfil del negocio](#11-perfil-del-negocio)
* [1.2. Alcance del producto](#12-alcance-del-producto)
* [1.3. Objetivos del proyecto](#13-objetivos-del-proyecto)
* [1.4. Usuarios del sistema](#14-usuarios-del-sistema)

[Capítulo II: Especificación de Requisitos](#capítulo-ii-especificación-de-requisitos)
* [2.1. Requisitos Funcionales (RF)](#21-requisitos-funcionales-rf)
* [2.2. Requisitos No Funcionales (RNF)](#22-requisitos-no-funcionales-rnf)
* [2.3. Lenguaje Ubicuo (Glosario del Dominio)](#23-lenguaje-ubicuo-glosario-del-dominio)
* [2.4. User Stories](#24-user-stories)
* [2.5. Product Backlog](#25-product-backlog)

[Capítulo III: Diseño de Producto (UX/UI)](#capítulo-iii-diseño-de-producto-uxui)
* [3.1. Arquitectura de Información](#31-arquitectura-de-información)
* [3.2. Wireframes](#32-wireframes)
* [3.3. Prototipo en Figma](#33-prototipo-en-figma)
* [3.4. Guía de Estilos](#34-guía-de-estilos)

[Capítulo IV: Arquitectura de Software (Domain-Driven Design)](#capítulo-iv-arquitectura-de-software-domain-driven-design)
* [4.1. Event Storming (Diseño)](#41-event-storming-diseño)
* [4.2. Bounded Contexts y Context Map](#42-bounded-contexts-y-context-map)
* [4.3. Diagrama de Contexto (C4 - Nivel 1)](#43-diagrama-de-contexto-c4---nivel-1)
* [4.4. Diagrama de Contenedores (C4 - Nivel 2)](#44-diagrama-de-contenedores-c4---nivel-2)
* [4.5. Diagrama de Componentes (C4 - Nivel 3)](#45-diagrama-de-componentes-c4---nivel-3)
* [4.6. Arquitectura en la Nube (PWA)](#46-arquitectura-en-la-nube-pwa)

[Capítulo V: Diseño Orientado a Objetos](#capítulo-v-diseño-orientado-a-objetos)
* [5.1. Diagrama de Clases — Backend](#51-diagrama-de-clases--backend)
* [5.2. Diagrama de Clases — Frontend](#52-diagrama-de-clases--frontend)

[Capítulo VI: Diseño de Base de Datos](#capítulo-vi-diseño-de-base-de-datos)
* [6.1. Modelo Entidad-Relación](#61-modelo-entidad-relación)
* [6.2. Diagrama de Base de Datos](#62-diagrama-de-base-de-datos)
* [6.3. Diccionario de Datos](#63-diccionario-de-datos)

[Capítulo VII: Gestión del Proyecto (Scrum, 2 semanas)](#capítulo-vii-gestión-del-proyecto-scrum-2-semanas)
* [7.1. Plan de Sprints](#71-plan-de-sprints)
* [7.2. Sprint 1 — Documentación, Diseño y Base del Sistema](#72-sprint-1--documentación-diseño-y-base-del-sistema)
* [7.3. Sprint 2 — Desarrollo, Integración, Pruebas y Despliegue](#73-sprint-2--desarrollo-integración-pruebas-y-despliegue)
* [7.4. Definition of Done](#74-definition-of-done)

[Capítulo VIII: Implementación](#capítulo-viii-implementación)
* [8.1. Configuración del Entorno de Desarrollo](#81-configuración-del-entorno-de-desarrollo)
* [8.2. Gestión de Código Fuente](#82-gestión-de-código-fuente)
* [8.3. Convenciones de Código](#83-convenciones-de-código)
* [8.4. Configuración de Despliegue](#84-configuración-de-despliegue)
* [8.5. Avance por Sprint](#85-avance-por-sprint)

[Capítulo IX: Pruebas y Validación](#capítulo-ix-pruebas-y-validación)
* [9.1. Estrategia de Pruebas](#91-estrategia-de-pruebas)
* [9.2. Casos de Prueba Clave](#92-casos-de-prueba-clave)
* [9.3. Validación con el Cliente](#93-validación-con-el-cliente)

[Capítulo X: Despliegue](#capítulo-x-despliegue)
* [10.1. Ambiente de Producción](#101-ambiente-de-producción)
* [10.2. Checklist de Despliegue](#102-checklist-de-despliegue)
* [10.3. Plan de Rollback](#103-plan-de-rollback)

[Anexos](#anexos)

---

# Capítulo I: Introducción

## 1.1. Perfil del negocio
Descripción del negocio de Carlos Maldonado (complejo de 5 canchas), cómo gestiona hoy las reservas y pagos, y el problema que motiva el sistema (doble reserva, control manual, falta de visibilidad de ingresos).

## 1.2. Alcance del producto
Referencia directa a la Propuesta 1 aceptada: sistema de uso interno (Carlos + 1 trabajador), sin reservas de clientes finales ni pagos online. Se deja constancia de que la Propuesta 2 queda evaluada para una fase futura.

## 1.3. Objetivos del proyecto
- Eliminar la doble reserva de horarios.
- Centralizar la gestión de clientes, alquileres y pagos.
- Dar visibilidad diaria de ingresos y pendientes.
- Entregar una PWA instalable, sin dependencia de tiendas de apps.

## 1.4. Usuarios del sistema
- Carlos (Administrador / dueño)
- Trabajador autorizado (Administrador secundario)

---

# Capítulo II: Especificación de Requisitos

## 2.1. Requisitos Funcionales (RF)
Numerar por módulo, tomando como base el alcance de la Propuesta 1:

**Gestión de usuarios**
- RF01: Inicio de sesión con autenticación segura.
- RF02: Soporte para múltiples administradores.
- RF03: Control de acceso a la información según rol.

**Gestión de alquileres**
- RF04: Calendario de disponibilidad (vista diaria, semanal, mensual).
- RF05: Registrar, editar y cancelar un alquiler.
- RF06: Bloqueo automático de horarios ya ocupados.
- RF07: Bloqueo manual de horario por mantenimiento.
- RF08: Historial de alquileres con búsqueda y filtros.

**Gestión de clientes**
- RF09: Registrar, editar y eliminar clientes.
- RF10: Historial básico de alquileres por cliente.

**Gestión de canchas**
- RF11: Administración de las 5 canchas (alta, edición).
- RF12: Configuración de precios por cancha/horario.
- RF13: Vista general de disponibilidad de todas las canchas.

**Gestión de pagos**
- RF14: Registro de estado de pago (pagado/pendiente).
- RF15: Registro de pagos parciales.
- RF16: Registro de método de pago (efectivo, Yape, etc.).

**Panel principal**
- RF17: Resumen de alquileres del día.
- RF18: Resumen de ingresos del día.
- RF19: Resumen de pagos pendientes.

*(Ajustar numeración/redacción final tras validar con Carlos.)*

## 2.2. Requisitos No Funcionales (RNF)
- RNF01 — Seguridad: autenticación y autorización por rol, datos en tránsito cifrados (HTTPS).
- RNF02 — Disponibilidad: sistema operativo en horario de atención del negocio (definir SLA informal, ej. 99% en horas de uso).
- RNF03 — Usabilidad: interfaz responsive, optimizada para uso desde celular/tablet por el administrador.
- RNF04 — Instalabilidad: PWA instalable sin costo de tienda de apps (manifest + service worker).
- RNF05 — Rendimiento: tiempos de carga y de registro de un alquiler menores a X segundos.
- RNF06 — Escalabilidad: la arquitectura debe soportar crecimiento futuro hacia la Propuesta 2 (clientes finales, pagos online) sin rediseño total.
- RNF07 — Mantenibilidad: código organizado por capas/dominio para facilitar extensión futura.
- RNF08 — Respaldo de datos: backups automáticos de la base de datos en la nube.

## 2.3. Lenguaje Ubicuo (Glosario del Dominio)
Tabla de términos clave y su significado dentro del negocio (ej. "Alquiler", "Bloqueo por mantenimiento", "Pago parcial", "Cancha", "Franja horaria"), consensuada con Carlos para evitar ambigüedad entre negocio y código.

## 2.4. User Stories
Historias de usuario en formato "Como [rol], quiero [acción], para [beneficio]", una por cada RF. Priorizadas por valor para el negocio.

## 2.5. Product Backlog
Tabla con: ID, Historia de usuario, Prioridad (Alta/Media/Baja), Estimación (puntos o días), Sprint asignado, Estado.

---

# Capítulo III: Diseño de Producto (UX/UI)

## 3.1. Arquitectura de Información
Mapa de navegación de la aplicación (login → panel → módulos: calendario, clientes, canchas, pagos, reportes).

## 3.2. Wireframes
Bocetos de baja fidelidad de las pantallas principales: login, panel del día, calendario de reservas, ficha de cliente, ficha de cancha, registro de pago.

## 3.3. Prototipo en Figma
Link al prototipo navegable en Figma + capturas de las pantallas de alta fidelidad, cubriendo el flujo completo de: crear alquiler → asignar cliente → registrar pago → ver panel.

## 3.4. Guía de Estilos
Paleta de colores, tipografía, componentes base (botones, inputs, tarjetas), adaptados para uso responsive/PWA.

---

# Capítulo IV: Arquitectura de Software (Domain-Driven Design)

## 4.1. Event Storming (Diseño)
Eventos de dominio identificados (ej. "Alquiler Registrado", "Alquiler Cancelado", "Pago Registrado", "Horario Bloqueado") y los comandos/actores que los disparan.

## 4.2. Bounded Contexts y Context Map
Propuesta de bounded contexts, por ejemplo:
- **Gestión de Reservas** (alquileres, calendario, bloqueos)
- **Gestión de Clientes**
- **Gestión de Canchas y Precios**
- **Gestión de Pagos**
- **Identidad y Acceso** (usuarios/autenticación)

Relaciones entre contextos (quién depende de quién, integraciones internas).

## 4.3. Diagrama de Contexto (C4 - Nivel 1)
Vista general: administradores ↔ sistema PWA ↔ servicios externos (proveedor de autenticación, base de datos en la nube).

## 4.4. Diagrama de Contenedores (C4 - Nivel 2)
Frontend PWA, API/Backend, Base de datos, servicio de autenticación, almacenamiento en la nube.

## 4.5. Diagrama de Componentes (C4 - Nivel 3)
Desglose interno del backend (controladores, servicios de dominio por bounded context, repositorios) y del frontend (módulos/páginas, servicios de estado, capa de acceso a API).

## 4.6. Arquitectura en la Nube (PWA)
Diagrama de despliegue en la nube: hosting del frontend (PWA), hosting/función del backend, base de datos gestionada, proveedor de autenticación, CDN, dominio/SSL. Justificación de por qué esta arquitectura soporta bajo costo y despliegue rápido en 2 semanas.

---

# Capítulo V: Diseño Orientado a Objetos

## 5.1. Diagrama de Clases — Backend
Entidades y relaciones: `Usuario`, `Cancha`, `Alquiler`, `Cliente`, `Pago`, `BloqueoHorario`, con atributos, métodos y relaciones (asociación, composición) según los bounded contexts definidos.

## 5.2. Diagrama de Clases — Frontend
Componentes/estructuras principales del frontend (según framework elegido): modelos de datos en cliente, servicios de consumo de API, stores/estado global, componentes de página.

---

# Capítulo VI: Diseño de Base de Datos

## 6.1. Modelo Entidad-Relación
Entidades: Usuario, Cancha, Cliente, Alquiler, Pago, BloqueoHorario — con cardinalidades.

## 6.2. Diagrama de Base de Datos
Diagrama físico (tablas, llaves primarias/foráneas, índices necesarios para evitar dobles reservas).

## 6.3. Diccionario de Datos
Tabla por entidad: nombre de campo, tipo de dato, restricciones (NOT NULL, UNIQUE, default), descripción.

---

# Capítulo VII: Gestión del Proyecto (Scrum, 2 semanas)

## 7.1. Plan de Sprints
Dado el plazo real de 2 semanas para todo (documentación, prototipo, desarrollo, pruebas y despliegue), se plantean **2 sprints de 1 semana cada uno**:

| Sprint | Duración | Enfoque principal |
|---|---|---|
| Sprint 1 | Semana 1 (días 1-7) | Documentación, arquitectura, diagramas, prototipo Figma, setup de proyecto, backend base (auth + modelos) |
| Sprint 2 | Semana 2 (días 8-14) | Frontend + integración con backend, pruebas, despliegue en la nube, ajustes con feedback de Carlos |

## 7.2. Sprint 1 — Documentación, Diseño y Base del Sistema
Objetivo del sprint, historias comprometidas (backlog priorizado), entregables: documento de arquitectura, prototipo Figma, backend base desplegado en entorno de desarrollo.

## 7.3. Sprint 2 — Desarrollo, Integración, Pruebas y Despliegue
Objetivo del sprint, historias comprometidas, entregables: frontend conectado al backend, pruebas ejecutadas, sistema desplegado en producción, capacitación breve a Carlos y su trabajador.

## 7.4. Definition of Done
Criterios mínimos para considerar una historia "terminada" (ej. código revisado, probado manualmente, sin bloqueos de doble reserva, desplegado en ambiente de pruebas).

---

# Capítulo VIII: Implementación

## 8.1. Configuración del Entorno de Desarrollo
Stack tecnológico elegido (frontend, backend, base de datos), requisitos para levantar el proyecto localmente.

## 8.2. Gestión de Código Fuente
Repositorio, estrategia de ramas (ej. main + feature branches dado el plazo corto y equipo de 1 persona).

## 8.3. Convenciones de Código
Nomenclatura, estructura de carpetas por bounded context/capa, linters/formatters usados.

## 8.4. Configuración de Despliegue
Proveedor de hosting elegido para frontend/backend/BD, variables de entorno, proceso de build y despliegue (manual o CI/CD simple).

## 8.5. Avance por Sprint
Registro de lo entregado en cada sprint (screenshots, funcionalidades completadas, desviaciones del plan).

---

# Capítulo IX: Pruebas y Validación

## 9.1. Estrategia de Pruebas
Qué se prueba y cómo, dado el plazo: pruebas manuales de flujos críticos (doble reserva, registro de pago) + pruebas unitarias mínimas en lógica de negocio sensible (bloqueo de horarios).

## 9.2. Casos de Prueba Clave
Lista de casos: no permitir doble reserva, cancelar alquiler libera el horario, pago parcial se refleja correctamente, panel del día muestra cifras correctas.

## 9.3. Validación con el Cliente
Sesión de validación con Carlos antes del cierre del Sprint 2: qué se revisó, feedback recibido, ajustes aplicados.

---

# Capítulo X: Despliegue

## 10.1. Ambiente de Producción
Detalle del entorno final: dominio, hosting, base de datos, certificados SSL.

## 10.2. Checklist de Despliegue
Lista de verificación pre-lanzamiento (variables de entorno configuradas, backups habilitados, PWA instalable verificada en celular real, datos de prueba eliminados).

## 10.3. Plan de Rollback
Qué hacer si algo falla en producción: cómo revertir a la última versión estable, respaldo de base de datos previo al despliegue.

---

# Anexos
- Propuesta de Desarrollo original (Propuesta 1 y 2, comparativa y decisión firmada por el cliente).
- Capturas del prototipo Figma.
- Actas de reuniones/validación con el cliente.
