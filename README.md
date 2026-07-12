<div align="center">

<br>

## Sistema de Gestión de Alquiler de Canchas 

<br>

# La Canchita de Carlos

<br>

### Documento de Producto — Propuesta 1 (Uso Interno)

<br>

**Cliente: Carlos Maldonado**

**Desarrolladora: Brianna Salinas**

<br>

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
* [4.7. Análisis Técnico-Económico de la Infraestructura](#47-análisis-técnico-económico-de-la-infraestructura)
  
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
 
## 4.0. Patrón de Arquitectura
El sistema combina dos niveles de arquitectura, uno de despliegue y otro de organización interna del código:
 
**Nivel de despliegue — Arquitectura de tres capas:**
- **Presentación:** PWA en React (lo que el administrador ve y usa).
- **Aplicación:** API en Node.js/Express (lógica de negocio y reglas del dominio).
- **Datos:** PostgreSQL (persistencia).
Se eligió tres capas y no monolito simple ni microservicios: el negocio es pequeño (2 administradores, 5 canchas, sin tráfico masivo), por lo que microservicios agregaría complejidad de despliegue injustificada para el plazo de 2 semanas; y separar en tres capas ya da independencia suficiente entre frontend, backend y base de datos para desplegar y escalar cada una por separado si el negocio crece (ver Propuesta 2).
 
**Nivel de código — Arquitectura Hexagonal (Puertos y Adaptadores) dentro de la capa de Aplicación:**
El backend no se organiza como un Express típico con todo en controladores, sino en 3 anillos:
- **Dominio (núcleo):** entidades y reglas de negocio puras de cada bounded context (`Alquiler`, `Cancha`, `Cliente`, `Pago`), sin dependencias de Express, Prisma ni ninguna librería externa.
- **Aplicación (casos de uso):** orquesta el dominio para cumplir una acción concreta (ej. `RegistrarAlquiler`, `CancelarAlquiler`, `RegistrarPago`), define **puertos** (interfaces) que necesita, como `AlquilerRepository`.
- **Infraestructura (adaptadores):** implementaciones concretas de esos puertos — el adaptador de entrada es Express (controladores/rutas que reciben HTTP y llaman a los casos de uso), el adaptador de salida es Prisma/PostgreSQL (implementa `AlquilerRepository` contra la base de datos real).
**Por qué combinarlas:** la arquitectura de tres capas resuelve *dónde* corre cada cosa (despliegue); la hexagonal resuelve *cómo* se organiza el código *dentro* de la capa de Aplicación, alineado a los bounded contexts definidos en DDD (sección 4.2). La ventaja concreta para este proyecto: la lógica de negocio (ej. "no permitir doble reserva") queda aislada y testeable sin levantar servidor ni base de datos, y si en la Propuesta 2 cambian de Prisma a otro ORM o agregan una pasarela de pagos, solo se reemplaza el adaptador correspondiente sin tocar las reglas de negocio.
 
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
**Stack definido para este proyecto:**
 
| Capa | Tecnología | Motivo |
|---|---|---|
| Frontend | React + Vite + `vite-plugin-pwa` + Tailwind CSS | Ya dominado, build rápido, soporte PWA (manifest + service worker) de fábrica. |
| Estado / datos | React Query (o similar) + React Router | Manejo simple de llamadas a la API y cacheo, sin over-engineering. |
| Backend | Node.js + Express + TypeScript | Stack que ya manejas: mayor velocidad de desarrollo en 2 semanas frente a aprender NestJS o Firebase desde cero. |
| ORM | Prisma | Migraciones automáticas y modelos tipados, acelera el diseño de BD del Capítulo VI. |
| Base de datos | PostgreSQL gestionado (Neon o Supabase, plan gratuito) | Relacional, soporta transacciones/constraints para evitar doble reserva (clave para RF06). |
| Autenticación | JWT + bcrypt implementado en Express | Solo 2 usuarios administradores; no se justifica un proveedor de auth externo todavía. |
| Hosting Frontend | Vercel (plan gratuito) | Despliegue automático desde GitHub, HTTPS y CDN incluidos, soporta PWA sin configuración extra. |
| Hosting Backend | Render o Railway (plan gratuito/bajo costo) | Despliegue simple de un servicio Node/Express, variables de entorno fáciles de configurar. |
| Repositorio | GitHub | Integración directa con Vercel/Render para despliegue continuo. |
 
Diagrama de despliegue: Administrador (celular/PC) → PWA en Vercel → API Express en Render/Railway → PostgreSQL en Neon/Supabase. Todo con capas gratuitas o de bajo costo, alineado al presupuesto de S/ 1,700 y al plazo de 2 semanas. Esta base también deja el camino abierto para escalar a la Propuesta 2 (agregar pasarela de pagos y notificaciones) sin rehacer la arquitectura.
 
## 4.7. Análisis Técnico-Económico de la Infraestructura
Para cada componente de infraestructura se evaluaron alternativas bajo criterios técnicos (rendimiento, disponibilidad, facilidad de configuración) y económicos (costo bajo el volumen esperado: 2 administradores, sin tráfico masivo), siguiendo el mismo enfoque comparativo usado en proyectos anteriores (evaluación de alternativas + justificación de la opción elegida).
 
**Base de datos (capa de datos)**
 
| Alternativa | Tipo | Costo (plan inicial) | Ventaja principal | Limitación |
|---|---|---|---|---|
| **Neon (elegido)** | PostgreSQL gestionado, serverless | Gratuito para este volumen | Auto-suspende cuando no hay uso (ideal para negocio con horario definido), ramas de BD para pruebas | Cold start leve tras inactividad |
| Supabase | PostgreSQL gestionado + extras (auth, storage) | Gratuito para este volumen | Incluye panel de administración visual, útil si más adelante se necesita backend adicional | Más funcionalidades de las que este alcance requiere (riesgo de sobre-ingeniería) |
| Instancia propia (VPS + Docker) | PostgreSQL autoadministrado | Bajo pero no gratuito, + tiempo de mantenimiento | Control total de configuración | Requiere administrar parches de seguridad, backups y disponibilidad manualmente — inviable en 2 semanas con 1 desarrolladora |
 
*Justificación:* se eligió Neon por ser gratuito bajo este volumen de uso, no requerir administración de servidor y soportar transacciones/constraints necesarios para evitar la doble reserva. Supabase queda como alternativa válida si en la Propuesta 2 se necesitara autenticación o storage integrados.
 
**Backend (capa de aplicación)**
 
| Alternativa | Costo (plan inicial) | Ventaja principal | Limitación |
|---|---|---|---|
| **Render (elegido)** | Gratuito (con suspensión por inactividad) o plan bajo costo sin suspensión | Despliegue directo desde GitHub, configuración simple de variables de entorno | Plan gratuito "duerme" el servicio tras inactividad (primer request lento) |
| Railway | Gratuito con créditos limitados, luego de pago | Muy buena experiencia de desarrollador, despliegue rápido | Créditos gratuitos se agotan más rápido que el plan free de Render |
| VPS propio (DigitalOcean, etc.) | Bajo costo mensual fijo | Control total | Requiere configurar servidor, proxy, SSL y monitoreo manualmente — no viable en el plazo |
 
*Justificación:* Render por el balance entre costo (compatible con el presupuesto de S/ 1,700) y simplicidad de despliegue continuo, priorizando velocidad de entrega sobre control total de infraestructura.
 
**Frontend / PWA (capa de presentación)**
 
| Alternativa | Costo | Ventaja principal | Limitación |
|---|---|---|---|
| **Vercel (elegido)** | Gratuito para este uso | CDN global, HTTPS y despliegue automático desde GitHub, soporte nativo para PWA | Límites de uso no relevantes para este volumen |
| Netlify | Gratuito para este uso | Equivalente a Vercel en funcionalidad | Sin ventaja diferencial sobre Vercel para este caso |
 
*Justificación:* Vercel y Netlify son equivalentes para este proyecto; se eligió Vercel por mayor familiaridad y su excelente integración con proyectos Vite.
 
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
**Stack:** React + Vite (frontend PWA) · Node.js + Express + TypeScript (backend) · Prisma ORM · PostgreSQL (ver detalle y justificación en 4.6).
 
Requisitos locales: Node.js LTS, npm, cuenta de GitHub, cliente de PostgreSQL (o acceso a la instancia de Neon/Supabase), variables de entorno (`.env`) para conexión a BD y secreto JWT.
 
## 8.2. Gestión de Código Fuente
Repositorio, estrategia de ramas (ej. main + feature branches dado el plazo corto y equipo de 1 persona).
 
## 8.3. Convenciones de Código
Nomenclatura, estructura de carpetas por bounded context/capa, linters/formatters usados.
 
## 8.4. Configuración de Despliegue
- **Frontend:** despliegue automático en Vercel al hacer push a `main` (build de Vite).
- **Backend:** despliegue automático en Render/Railway conectado al repo de GitHub.
- **Base de datos:** instancia gestionada en Neon o Supabase (plan gratuito), string de conexión como variable de entorno en el backend.
- **Variables de entorno:** `DATABASE_URL`, `JWT_SECRET`, `PORT`, URL del backend expuesta al frontend como `VITE_API_URL`.
- Sin pipeline de CI complejo dado el plazo: el despliegue continuo de Vercel/Render (deploy on push) cumple el rol de CI/CD básico para este proyecto.
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
 
