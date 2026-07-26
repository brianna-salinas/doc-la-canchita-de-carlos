<div align="center">

<br>

## Sistema de Gestión de Alquiler de Canchas

<br>

# La Canchita de Carlos

<img src="assets/styles/logo.png" alt="Logo La Canchita de Carlos" width="200"/>

<br>

### Documento de Producto — Propuesta 1 (Uso Interno)

<br>

**Cliente: Carlos Maldonado**
**Desarrollado por: Brianna Salinas**

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
* [2.1. Requisitos Funcionales](#21-requisitos-funcionales)
* [2.2. Requisitos No Funcionales](#22-requisitos-no-funcionales)
* [2.3. Lenguaje Ubicuo](#23-lenguaje-ubicuo)
* [2.4. User Stories](#24-user-stories)
* [2.5. Product Backlog](#25-product-backlog)

[Capítulo III: Diseño de Producto (UX/UI)](#capítulo-iii-diseño-de-producto-uxui)
* [3.1. Arquitectura de Información](#31-arquitectura-de-información)
* [3.2. Style Guideline](#32-style-guideline)
* [3.3. Wireframes y Mockups](#33-wireframes-y-mockups)
* [3.4. Prototipo en Figma](#34-prototipo-en-figma)

[Capítulo IV: Arquitectura de Software (Domain-Driven Design)](#capítulo-iv-arquitectura-de-software-domain-driven-design)
* [4.0. Patrón de Arquitectura](#40-patrón-de-arquitectura)
* [4.1. Event Storming](#41-event-storming)
* [4.2. Bounded Contexts y Context Map](#42-bounded-contexts-y-context-map)
* [4.3. Diagrama de Contexto (C4 - Nivel 1)](#43-diagrama-de-contexto-c4---nivel-1)
* [4.4. Diagrama de Contenedores (C4 - Nivel 2)](#44-diagrama-de-contenedores-c4---nivel-2)
* [4.5. Diagrama de Componentes (C4 - Nivel 3)](#45-diagrama-de-componentes-c4---nivel-3)
* [4.6. Arquitectura en la Nube (PWA)](#46-arquitectura-en-la-nube-pwa)
* [4.7. Análisis Técnico-Económico de la Infraestructura](#47-análisis-técnico-económico-de-la-infraestructura)

[Capítulo V: Diseño Orientado a Objetos](#capítulo-v-diseño-orientado-a-objetos)
* [5.1. Diagrama de Clases - Backend](#51-diagrama-de-clases--backend)
* [5.2. Diagrama de Clases - Frontend](#52-diagrama-de-clases--frontend)

[Capítulo VI: Diseño de Base de Datos](#capítulo-vi-diseño-de-base-de-datos)
* [6.1. Modelo Entidad-Relación](#61-modelo-entidad-relación)
* [6.2. Diagrama de Base de Datos](#62-diagrama-de-base-de-datos)
* [6.3. Diccionario de Datos](#63-diccionario-de-datos)

[Capítulo VII: Gestión del Proyecto](#capítulo-vii-gestión-del-proyecto)
* [7.1. Plan de Sprints](#71-plan-de-sprints)
* [7.2. Sprint 1](#72-sprint-1)
* [7.3. Sprint 2](#73-sprint-2)
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

<br>

---

# Capítulo I: Introducción

## 1.1. Perfil del negocio

"La Canchita de Carlos" opera dentro de la Institución Educativa N.° 1278 Mixto La Molina (Jr. Cusco 416, La Molina, Lima), donde Carlos Maldonado administra el alquiler de las canchas deportivas del plantel (vóley, fútbol y básquet, cinco espacios en total) fuera del horario escolar. Este modelo permite aprovechar la infraestructura deportiva del colegio como fuente de ingreso adicional, alquilando las canchas a equipos, grupos e instituciones externas en las tardes, noches y fines de semana.

Actualmente, la gestión de las reservas se realiza de forma manual: los horarios se coordinan por llamadas o mensajes, los pagos se registran en cuadernos o notas sueltas (efectivo, Yape), y no existe un sistema centralizado que Carlos y su trabajador puedan consultar en tiempo real. Esto genera dos problemas recurrentes: dobles reservas de una misma cancha en el mismo horario (con el consecuente conflicto frente a los clientes) y falta de visibilidad clara sobre cuánto se ha alquilado, cuánto se ha cobrado y qué pagos quedan pendientes en un día determinado.

El sistema busca resolver esto centralizando la gestión de las cinco canchas en una sola herramienta accesible desde el celular o la computadora, exclusiva para Carlos y su trabajador, sin exponer el sistema a los clientes finales (alcance definido en la Propuesta 1).

<br>

## 1.2. Alcance del producto

El presente documento desarrolla la **Propuesta 1 — Uso interno**, aceptada por el cliente sobre la Propuesta 2, en función del plazo real disponible (2 semanas) y el presupuesto acordado. El sistema es de uso exclusivo de Carlos y por trabajadores autorizados por el mismo; los clientes finales no acceden a la aplicación ni realizan reservas ni pagos por este medio.

<br>

**Incluido en el alcance:**

- Gestión de usuarios administradores (inicio de sesión seguro, múltiples administradores, control de acceso a los administradores desde la cuenta principal).

- Gestión de alquileres: calendario de disponibilidad (diario/semanal/mensual), registro/edición/cancelación, bloqueo automático de horarios ocupados, bloqueo manual por mantenimiento con motivo, historial con búsqueda y filtros.

- Gestión de clientes: registro (incluyendo DNI/RUC), edición, eliminación e historial básico.

- Gestión de las cinco canchas: alta y edición, configuración de precios, vista general de disponibilidad, fotos.

- Gestión de pagos: estado (pagado/pendiente), pagos parciales, método de pago — registrados manualmente por el administrador (efectivo, Yape, etc.), sin pasarela de pago integrada.

- Panel principal con alquileres, ingresos y pagos pendientes del día.
- Aplicación PWA instalable, con diseño responsive optimizado para uso desde celular.

<br>

**Explícitamente fuera de alcance en esta fase:**
- Acceso o reservas por parte de clientes finales (celular/tablet/PC de los clientes).

- Pago online con tarjeta o pasarela de pagos.

- Notificaciones automáticas (correo, WhatsApp, recordatorios).

- Reportes exportables en PDF/Excel más allá del panel del día.

Estos puntos corresponden íntegramente a la **Propuesta 2 — Plataforma con clientes**, la cual queda documentada como fase de evolución futura del sistema y no forma parte del desarrollo actual. La arquitectura definida en el Capítulo IV se diseña de modo que esta segunda fase sea una extensión y no un rediseño del sistema.

<br>

## 1.3. Objetivos del proyecto

**Objetivo general**

Diseñar e implementar un sistema PWA de gestión de alquiler de canchas para "La Canchita de Carlos", que centralice la administración de alquileres, clientes, canchas y pagos en una sola herramienta de uso interno, eliminando la doble reserva de horarios y dando visibilidad diaria de la operación del negocio.

## 1.4. Usuarios del sistema

El sistema tiene un único rol funcional, **Administrador**, asignado a dos personas con el mismo nivel de acceso, sin jerarquía entre ellas dentro de la aplicación:

<br>

| Usuario | Rol | Responsabilidades principales |
|---|---|---|
| Carlos Maldonado | Administrador / dueño | Gestión general del negocio: precios de canchas, revisión de ingresos y pendientes, alta de nuevos administradores si fuera necesario. |
| Trabajador autorizado | Administrador secundario | Operación del día a día: registrar y confirmar alquileres, atender llamadas/mensajes de clientes y reflejarlos en el sistema, registrar pagos. |

<br>

No existe un rol de "cliente" dentro del sistema en esta fase los clientes de Carlos no inician sesión ni interactúan directamente con la aplicación, solo son gestionados como registros dentro del módulo de clientes. Este punto es clave para el diseño de la autenticación (RF01–RF03): basta con un control de acceso simple de 2 usuarios, sin necesidad de un sistema de roles complejo en esta etapa.

<br>

---

# Capítulo II: Especificación de Requisitos

## 2.1. Requisitos Funcionales

Requisitos derivados del alcance definido, agrupados por módulo (bounded context), con prioridad asignada según su criticidad para resolver el problema central del negocio: la doble reserva y la falta de visibilidad de ingresos.

<br>

**Módulo: Gestión de usuarios**

| ID | Descripción | Prioridad |
|---|---|---|
| RF01 | El sistema debe permitir el inicio de sesión de un administrador mediante correo/usuario y contraseña, validando credenciales antes de dar acceso. | Alta |
| RF02 | El sistema debe soportar al menos 2 cuentas de administrador (Carlos y su trabajador) operando de forma independiente y simultánea. | Alta |
| RF03 | El sistema debe restringir el acceso a la información únicamente a usuarios autenticados; ninguna ruta de datos debe ser accesible sin sesión válida. | Alta |

<br>

**Módulo: Gestión de alquileres**

| ID | Descripción | Prioridad |
|---|---|---|
| RF04 | El sistema debe mostrar un calendario de disponibilidad de las 5 canchas en vista diaria, semanal y mensual. | Alta |
| RF05 | El sistema debe permitir registrar, editar y cancelar un alquiler, asociándolo a una cancha, un cliente, una fecha y un horario. | Alta |
| RF33 | El sistema debe permitir registrar el tipo de reserva (pichanga, torneo, evento) y un nombre de equipo o grupo, distinto del nombre del cliente registrado, al momento de registrar un alquiler. | Media |
| RF06 | El sistema debe impedir el registro de un nuevo alquiler si la cancha ya tiene un alquiler activo en el mismo horario (regla central del negocio). | Alta — crítica |
| RF07 | El sistema debe permitir bloquear manualmente un horario de una cancha por motivo de mantenimiento, excluyéndolo de la disponibilidad. | Media |
| RF32 | El sistema debe permitir registrar un motivo o nota de texto al bloquear manualmente una franja horaria por mantenimiento, visible al consultar la franja bloqueada. | Media |
| RF08 | El sistema debe mantener un historial de alquileres, con filtros por fecha, cancha, cliente y estado. | Media |
| RF26 | Si el cliente de un alquiler no existe aún en el sistema, el formulario de registro de alquiler debe permitir crearlo ahí mismo (nombre, contacto) sin salir de la pantalla, y usarlo de inmediato para el alquiler. | Media |

<br>

**Módulo: Gestión de clientes**

| ID | Descripción | Prioridad |
|---|---|---|
| RF09 | El sistema debe permitir registrar, editar y eliminar clientes (nombre, DNI o RUC, contacto, correo opcional) — DNI para persona natural, RUC para persona jurídica/institución (equipos, colegios, empresas que alquilan). | Media |
| RF10 | El sistema debe mostrar el historial básico de alquileres asociado a cada cliente. | Baja |
| RF30 | El sistema debe permitir registrar el número de WhatsApp del cliente y ofrecer un acceso directo (abrir chat de WhatsApp) desde su ficha o desde el detalle de un alquiler. | Media |

<br>

**Módulo: Gestión de canchas**

| ID | Descripción | Prioridad |
|---|---|---|
| RF11 | El sistema debe permitir dar de alta, editar y dar de baja canchas (nombre, disciplina: vóley/fútbol/básquet). El catálogo actual tiene 5, pero el sistema no debe asumir ese número como fijo — Carlos puede agregar o retirar canchas sin soporte técnico. | Alta |
| RF12 | El sistema debe permitir configurar el precio por cancha, y opcionalmente por franja horaria. | Media |
| RF13 | El sistema debe mostrar una vista general de disponibilidad consolidada de todas las canchas. | Alta |
| RF31 | El sistema debe permitir adjuntar una o más fotos a cada cancha, para identificarla visualmente al momento de alquilar. | Media |

<br>

**Módulo: Gestión de pagos**

| ID | Descripción | Prioridad |
|---|---|---|
| RF14 | El sistema debe permitir registrar el estado de pago de un alquiler (pagado / pendiente). | Alta |
| RF15 | El sistema debe permitir registrar pagos parciales, indicando el monto abonado y el saldo restante. | Media |
| RF16 | El sistema debe permitir registrar el método de pago utilizado (efectivo, Yape, u otro). | Baja |
| RF25 | El sistema debe permitir adjuntar una imagen de comprobante (captura de Yape, foto de voucher, etc.) al registrar un pago total o parcial. | Media |

<br>

**Módulo: Panel principal**

| ID | Descripción | Prioridad |
|---|---|---|
| RF17 | El sistema debe mostrar en el panel principal los alquileres registrados para el día actual. | Alta |
| RF18 | El sistema debe calcular y mostrar el ingreso total del día en base a los pagos registrados. | Alta |
| RF19 | El sistema debe mostrar el listado de pagos pendientes del día. | Alta |

<br>

**Módulo: Registro y autorización de administradores**

| ID | Descripción | Prioridad |
|---|---|---|
| RF20 | El sistema debe permitir que una persona registre una solicitud de cuenta de administrador (nombre, correo), quedando en estado pendiente sin acceso al sistema. | Media |
| RF21 | El sistema debe permitir que únicamente el administrador dueño visualice, autorice o rechace solicitudes de cuenta pendientes. | Media |
| RF22 | El sistema debe notificar (correo simple) al solicitante si su cuenta fue autorizada o rechazada. | Baja |
| RF27 | El sistema debe permitir que el administrador dueño vea el listado de cuentas de administrador activas (no solo las pendientes de autorizar). | Baja |

<br>

**Módulo: Confirmación por correo**

| ID | Descripción | Prioridad |
|---|---|---|
| RF23 | El sistema debe enviar automáticamente un correo de confirmación al cliente cuando se registra un `Booking`, siempre que el cliente tenga un correo registrado (RF09). | Media |
| RF24 | Si el envío de correo falla, el sistema no debe bloquear ni revertir el registro del `Booking` — el correo es una notificación adicional, no una condición del negocio. | Media |

<br>

**Módulo: Ajustes de cuenta**

| ID | Descripción | Prioridad |
|---|---|---|
| RF28 | El sistema debe permitir que un administrador autenticado actualice su propio correo. | Baja |
| RF29 | El sistema debe permitir que un administrador autenticado cambie su propia contraseña, solicitando la contraseña actual como verificación. | Media |

<br>

## 2.2. Requisitos No Funcionales

Requisitos de calidad del sistema, con criterio medible cuando aplica, alineados a la infraestructura definida en la documentación.

<br>

| ID | Categoría | Descripción | Criterio de aceptación |
|---|---|---|---|
| RNF01 | Seguridad | Autenticación de administradores y protección de rutas de datos. | Contraseñas hasheadas con bcrypt; sesión mediante JWT con expiración; todo el tráfico servido por HTTPS. |
| RNF02 | Disponibilidad | El sistema debe estar operativo durante el horario de alquiler del negocio (tardes, noches y fines de semana). | El backend corre en el plan Starter de Render (de pago, ver 4.7.2), sin "arranque en frío" tras inactividad; no se exige SLA formal en esta fase. |
| RNF03 | Usabilidad | Interfaz optimizada para uso desde celular, principal dispositivo del administrador en campo. | Diseño responsive validado en al menos una resolución móvil real antes del despliegue (ver). |
| RNF04 | Instalabilidad | La app debe poder instalarse como PWA sin pasar por tienda de aplicaciones. | Manifest + service worker configurados; prompt de instalación funcional en Chrome/Android como mínimo. |
| RNF05 | Rendimiento | Tiempos de respuesta aceptables para el volumen de uso real (2 administradores, decenas de alquileres/día). | Registro de un alquiler y carga del panel del día responden en menos de 3 segundos con backend "caliente". |
| RNF06 | Escalabilidad | La arquitectura no debe requerir rediseño al evolucionar hacia la Propuesta 2. | Los subdominios definidos en 4.2 (Payments, Notifications) deben poder extenderse o activarse sin modificar el subdominio núcleo de Bookings. |
| RNF07 | Mantenibilidad | El código debe organizarse por dominio, no por tipo técnico de archivo. | Estructura de carpetas del backend refleja los bounded contexts y la separación hexagonal. |
| RNF08 | Respaldo de datos | La información no debe depender de un único punto de falla. | Backups automáticos habilitados en el proveedor de base de datos (Supabase) desde el primer despliegue en producción. |
| RNF09 | Compatibilidad | La PWA debe funcionar en los navegadores/dispositivos reales que usan Carlos y su trabajador. | Verificada en Chrome (Android) y un navegador de escritorio como mínimo. |

<br>

## 2.3. Lenguaje Ubicuo

Términos consensuados organizados por bounded context, para que el vocabulario del negocio y el vocabulario del código sean el mismo.

<br>

**Subdominio Bookings**

| Término | Significado |
|---|---|
| Cancha | Espacio deportivo alquilable del colegio (vóley, fútbol o básquet). Actualmente son 5, pero el catálogo es administrable por Carlos (RF11), no un número fijo en el sistema. |
| Franja horaria | Bloque de tiempo en el que una cancha puede alquilarse (ej. 6:00 pm – 7:00 pm). |
| Alquiler | Reserva confirmada de una cancha, para un cliente, en una fecha y franja horaria específica. |
| Doble reserva | Situación inválida en la que dos alquileres ocupan la misma cancha en la misma franja horaria. El sistema debe impedirla siempre (RF06). |
| Bloqueo por mantenimiento | Franja horaria marcada como no disponible por el administrador, sin estar asociada a un alquiler. |
| Motivo de bloqueo | Nota de texto opcional que explica la razón de un bloqueo por mantenimiento (ej. "césped en mal estado"), visible al consultar la franja bloqueada (RF32). |
| Tipo de reserva | Clasificación del alquiler según su naturaleza: pichanga (partido informal), torneo o evento. Permite distinguir el tipo de uso de la cancha más allá de quién paga (RF33). |
| Nombre de equipo/grupo | Nombre identificador del equipo o grupo que juega en un alquiler (ej. "Los Tigres"), distinto del nombre del cliente que registra y paga el alquiler (RF33). |
| Foto de cancha | Imagen adjunta a una `Court` para identificarla visualmente al momento de alquilar, especialmente útil cuando hay varias canchas del mismo tipo (RF31). |
| Disponibilidad | Estado de una cancha en una franja horaria: libre, alquilada o bloqueada. |

<br>

**Subdominio Payments**

| Término | Significado |
|---|---|
| Pago | Registro de dinero recibido por un alquiler. Puede ser total o parcial. |
| Pago parcial | Pago que cubre solo una parte del monto total del alquiler; el alquiler queda con saldo pendiente. |
| Pendiente | Estado de un alquiler cuyo monto (total o restante) aún no ha sido cobrado. |
| Método de pago | Forma en la que se recibió el dinero (efectivo, Yape, u otro registrado manualmente). |
| Comprobante de pago | Imagen adjunta a un `Payment` (captura de Yape, foto de voucher) que respalda visualmente que el cobro ocurrió (RF25). |

<br>

**Subdominio Customers**

| Término | Significado |
|---|---|
| Cliente | Persona o grupo externo (equipo, institución) que alquila una o más canchas. No tiene acceso al sistema (ver). |
| DNI / RUC | Documento de identificación del `Customer`: DNI si es persona natural, RUC si es persona jurídica (equipo formalizado, colegio, empresa). Dato adicional al nombre, útil para distinguir clientes con nombres similares y para eventuales fines contables (RF09). |
| WhatsApp de contacto | Número de WhatsApp registrado en la ficha del `Customer`, con acceso directo (enlace `wa.me`) desde su ficha o desde el detalle de un alquiler, para coordinar sin copiar el número manualmente (RF30). |
| Historial de cliente | Listado de alquileres pasados asociados a un cliente. |

<br>

**Subdominio Identity & Access**

| Término | Significado |
|---|---|
| Administrador | Usuario con acceso al sistema: Carlos o su trabajador autorizado. Rol operativo único. |
| Administrador dueño | Administrador con la capacidad adicional de autorizar o rechazar solicitudes de nuevas cuentas (RF21). Solo Carlos tiene este atributo. |
| Sesión | Periodo en el que un administrador permanece autenticado tras iniciar sesión. |
| Solicitud de acceso | Registro creado por alguien que pide una cuenta de administrador, en estado pendiente hasta que el administrador dueño la autoriza o rechaza (RF20–RF21). |

<br>

**Subdominio Notifications**

| Término | Significado |
|---|---|
| Correo de confirmación | Correo transaccional único enviado al cliente cuando se registra su `Booking`, si tiene correo registrado (RF23). No es un recordatorio recurrente. |
| Correo de resultado de solicitud | Correo enviado al solicitante de una cuenta de administrador informando si fue autorizada o rechazada (RF22). |

<br>

*Este glosario es la referencia obligatoria para nombrar clases, tablas y endpoints — evita que en el código aparezcan sinónimos distintos para el mismo concepto (ej. "reserva" vs. "alquiler").*

<br>

## 2.4. User Stories

>*Las User Stories expresan necesidades reales del negocio de Carlos, no funcionalidades de pantalla. Cada historia describe una capacidad operacional con impacto concreto en la gestión de "La Canchita de Carlos". Los criterios de aceptación siguen la estructura Gherkin (Given/When/Then) y validan **comportamiento del dominio**: estados que cambian, **invariantes que se protegen**, y eventos que se emiten — no lo que muestra la pantalla. Los aggregates raíz (`Booking`, `Court`, `Customer`, `Payment`, `User`, `AccessRequest`, `Notification`) y los Domain Events utilizados en estas historias fueron derivados del Event Storming (sección). Los criterios de aceptación se redactan en tiempo presente y tercera persona, sin referencias a detalles de interfaz.*

<br>

### Epics

| **ID** | **Título** | **Descripción** | **Historias Relacionadas** |
|---|---|---|---|
| **EP01** | **Identidad y Acceso** | Capacidad de negocio que garantiza que solo Carlos y su trabajador autorizado accedan al sistema, protegiendo la información operativa y financiera del negocio, incluyendo la recuperación de acceso si olvidan su contraseña y la configuración inicial de la cuenta dueño. | US01, US02, US03, US37, US45 |
| **EP02** | **Gestión de Reservas** | Capacidad de negocio central: administrar la disponibilidad de las canchas (calendario completo día/semana/mes) y garantizar que nunca coexistan dos alquileres para el mismo horario, permitiendo además registrar un cliente nuevo sin salir del flujo, bloquear y desbloquear franjas por mantenimiento con motivo (una o varias fechas a la vez, con su listado propio), y registrar reservas de una sola fecha, multi-día o recurrentes. | US04, US05, US06, US07, US08, US28, US31, US32, US35, US44 |
| **EP03** | **Gestión de Clientes** | Capacidad de negocio que permite mantener un registro de quién alquila, incluyendo su documento de identificación y un canal directo de contacto (WhatsApp), para dar seguimiento comercial básico. | US09, US10, US30 |
| **EP04** | **Gestión de Canchas** | Capacidad de negocio que permite mantener actualizado el inventario de canchas del colegio (catálogo administrable, no un número fijo, incluyendo su baja), sus precios y su identificación visual con fotos, base para calcular y comunicar correctamente cada alquiler. | US11, US12, US13, US29, US43 |
| **EP05** | **Gestión de Pagos** | Capacidad de negocio que permite registrar y trazar el dinero cobrado por cada alquiler, incluyendo pagos parciales, la consulta del historial de pagos de un alquiler y el respaldo visual del comprobante (adjuntarlo y volver a verlo). | US14, US15, US16, US27, US46, US47 |
| **EP06** | **Panel Operativo del Día** | Capacidad de negocio que da a Carlos visibilidad inmediata de la operación diaria: qué se alquiló, cuánto se cobró y qué falta cobrar. | US17, US18, US19 |
| **EP07** | **Registro y Autorización de Administradores** | Capacidad de negocio que permite a Carlos incorporar nuevos administradores de forma controlada, sin crear cada cuenta manualmente ni ceder acceso sin verificación, ver quién tiene acceso activo, compartir el rol de dueño con alguien de confianza y revocar el acceso cuando ya no corresponde. | US20, US21, US26, US34, US39, US40 |
| **EP08** | **Confirmación por Correo** | Capacidad de negocio que da respaldo automático por correo de las acciones clave (reserva registrada, cuenta autorizada/rechazada), sin construir un sistema de notificaciones completo. | US22, US23 |
| **EP09** | **Ajustes de Cuenta** | Capacidad de negocio que permite a cada administrador mantener actualizados sus propios datos de acceso (correo, contraseña, perfil, foto) y darse de baja del sistema, sin depender de soporte técnico externo. | US24, US25, US41, US42 |
| **EP10** | **Notificaciones Internas entre Administradores** | Capacidad de negocio que mantiene a los administradores al tanto de lo que hace el otro (reservas, series y bloqueos de mantenimiento registrados) sin que tengan que preguntarse directamente. | US38 |

<br>

### User Stories
| **ID** | **Título** | **Descripción** | **Criterios de Aceptación** | **Epic ID** |
|---|---|---|---|---|
| **EP01 – Identidad y Acceso** |||||
| **US01** | Iniciar sesión de forma segura | Como administrador, quiero iniciar sesión con mis credenciales para acceder únicamente si soy un usuario autorizado del negocio. | **Escenario 1 – Login exitoso:** <br> **Given:** el administrador ingresa credenciales correctas de una cuenta `User` existente <br> **When:** el sistema valida las credenciales <br> **Then:** se emite el evento `SessionStarted`, se genera un token de sesión y el administrador accede al panel. <br><br> **Escenario 2 – Credenciales inválidas rechazadas:** <br> **Given:** el administrador ingresa una contraseña incorrecta <br> **When:** el sistema valida <br> **Then:** el sistema rechaza el acceso, no se emite `SessionStarted` y ningún dato del negocio queda expuesto. | EP01 |
| **US02** | Operar con múltiples cuentas de administrador | Como administrador, quiero que exista más de una cuenta activa para que Carlos y su trabajador operen en paralelo sin bloquearse mutuamente. | **Escenario 1 – Sesiones simultáneas válidas:** <br> **Given:** existen dos cuentas `User` activas (Carlos y su trabajador) <br> **When:** ambas inician sesión al mismo tiempo <br> **Then:** ambas sesiones permanecen activas de forma independiente y cada una puede registrar alquileres sin invalidar la sesión del otro. <br><br> **Escenario 2 – Acción de un administrador visible para el otro:** <br> **Given:** el trabajador registra un `Booking` <br> **When:** Carlos consulta el calendario desde su propia sesión <br> **Then:** el nuevo `Booking` es visible de inmediato, sin necesidad de que Carlos reinicie sesión. | EP01 |
| **US03** | Proteger la información del negocio sin sesión válida | Como administrador, quiero que ningún dato del negocio sea accesible sin sesión iniciada, para proteger información operativa y financiera. | **Escenario 1 – Acceso sin sesión rechazado:** <br> **Given:** no existe una sesión válida <br> **When:** se intenta consultar cualquier `Booking`, `Customer` o `Payment` <br> **Then:** el sistema deniega el acceso y no retorna ningún dato del dominio. <br><br> **Escenario 2 – Sesión cerrada invalida el acceso:** <br> **Given:** un administrador tenía sesión activa <br> **When:** cierra sesión (`SessionClosed`) <br> **Then:** cualquier intento posterior de consultar datos con ese token es rechazado. | EP01 |
| **US37** | Recuperar el acceso olvidando mi contraseña | Como administrador, quiero poder solicitar un enlace de restablecimiento de contraseña cuando la olvido, para recuperar el acceso a mi cuenta sin depender de que otro administrador me la cambie. | **Escenario 1 – Solicitud de restablecimiento:** <br> **Given:** el administrador ingresa el correo asociado a su cuenta <br> **When:** solicita el restablecimiento <br> **Then:** el sistema genera un token de restablecimiento de un solo uso y envía un correo con el enlace, sin confirmar ni negar si ese correo existe en el sistema. <br><br> **Escenario 2 – Restablecimiento exitoso:** <br> **Given:** el administrador abre un enlace de restablecimiento válido y no expirado <br> **When:** ingresa una nueva contraseña <br> **Then:** la contraseña se actualiza y todas las sesiones activas de esa cuenta se invalidan, obligando a iniciar sesión de nuevo. <br><br> **Escenario 3 – Token inválido o expirado:** <br> **Given:** el token ya fue usado o expiró <br> **When:** el administrador intenta restablecer la contraseña con él <br> **Then:** el sistema rechaza la operación sin modificar la contraseña actual. | EP01 |
| **US45** | Configurar la cuenta inicial del administrador dueño | Como Carlos, quiero poder crear la primera cuenta de administrador dueño al desplegar el sistema, para empezar a operarlo sin depender de un proceso manual sobre la base de datos. | **Escenario 1 – Configuración inicial exitosa:** <br> **Given:** el sistema todavía no tiene ningún administrador dueño registrado <br> **When:** se completa el formulario de configuración inicial con el token de instalación correcto <br> **Then:** se crea el primer `User` con rol dueño, activo desde el inicio. <br><br> **Escenario 2 – Configuración ya realizada:** <br> **Given:** ya existe un administrador dueño en el sistema <br> **When:** alguien intenta repetir la configuración inicial <br> **Then:** el sistema la rechaza, sin importar si el token es correcto — este proceso solo puede ejecutarse una vez. | EP01 |
| **EP02 – Gestión de Reservas** |||||
| **US04** | Visualizar disponibilidad de canchas | Como administrador, quiero ver la disponibilidad de las 5 canchas en vista diaria, semanal y mensual, para planificar rápido los alquileres. | **Escenario 1 – Disponibilidad reflejada correctamente:** <br> **Given:** existen `Booking` activos y `ScheduleBlock` vigentes sobre distintas canchas <br> **When:** el administrador consulta el calendario para una fecha <br> **Then:** el sistema retorna cada franja como libre, alquilada o bloqueada, reflejando el estado real de los aggregates `Booking` y `ScheduleBlock`. <br><br> **Escenario 2 – Cambio de vista sin alterar el dominio:** <br> **Given:** el administrador está viendo la vista diaria <br> **When:** cambia a vista semanal o mensual <br> **Then:** el sistema recalcula la disponibilidad para el nuevo rango sin modificar ningún `Booking` o `ScheduleBlock` existente. | EP02 |
| **US05** | Registrar, editar y cancelar un alquiler | Como administrador, quiero registrar, editar y cancelar un alquiler, para que el sistema refleje exactamente lo acordado con el cliente. | **Escenario 1 – Registro exitoso:** <br> **Given:** la cancha y franja horaria solicitadas están libres <br> **When:** el administrador registra el alquiler con cliente, cancha, fecha y horario <br> **Then:** se crea el aggregate `Booking` en estado `RESERVADO` y se emite el evento `BookingRegistered`. <br><br> **Escenario 2 – Edición reevaluando disponibilidad:** <br> **Given:** un `Booking` existente en estado `RESERVADO` <br> **When:** el administrador cambia su horario a una franja también libre <br> **Then:** el sistema actualiza el `Booking` y emite `BookingEdited`. <br><br> **Escenario 3 – Cancelación libera la franja y reversa pagos:** <br> **Given:** un `Booking` en estado `RESERVADO`, con o sin pagos registrados <br> **When:** el administrador lo cancela <br> **Then:** el `Booking` transita a estado `CANCELADO`, se emite `BookingCancelled`, la franja queda disponible de inmediato para un nuevo registro y, si tenía pagos registrados, estos se reversan automáticamente (`PaymentReversed`). | EP02 |
| **US06** | Impedir la doble reserva de una cancha | Como administrador, quiero que el sistema impida crear un alquiler en un horario ya ocupado, para que nunca ocurra una doble reserva. | **Escenario 1 – Doble reserva rechazada (invariante central):** <br> **Given:** ya existe un `Booking` en estado `RESERVADO` para la cancha X en la franja 6:00–7:00 pm <br> **When:** el administrador intenta registrar otro `Booking` para la misma cancha y franja <br> **Then:** el sistema rechaza la operación, no se crea un nuevo `Booking` y se emite el evento `DoubleBookingRejected` en lugar de `BookingRegistered`. <br><br> **Escenario 2 – Franja liberada permite nueva reserva:** <br> **Given:** el `Booking` que ocupaba la franja X fue cancelado (`BookingCancelled`) <br> **When:** el administrador registra un nuevo alquiler para esa misma cancha y franja <br> **Then:** el sistema lo acepta y emite `BookingRegistered`, porque la invariante de exclusividad ya no se viola. <br><br> **Escenario 3 – Edición que colisiona con otro alquiler:** <br> **Given:** el `Booking` A ocupa la franja X y el `Booking` B ocupa la franja Y de la misma cancha <br> **When:** el administrador intenta editar B para moverlo a la franja X <br> **Then:** el sistema rechaza la edición, `B` conserva su horario original y se emite `DoubleBookingRejected`. | EP02 |
| **US07** | Bloquear y desbloquear una franja por mantenimiento | Como administrador, quiero bloquear manualmente una franja de una cancha por mantenimiento y poder quitar ese bloqueo cuando ya no aplica, para controlar con precisión cuándo una franja no está disponible. | **Escenario 1 – Bloqueo exitoso:** <br> **Given:** la franja de la cancha X está libre <br> **When:** el administrador la marca como bloqueada por mantenimiento <br> **Then:** se crea un `ScheduleBlock` para esa cancha y franja, se emite `ScheduleBlocked`, y la franja deja de estar disponible para alquileres. <br><br> **Escenario 2 – No se puede bloquear una franja con alquiler activo:** <br> **Given:** la franja de la cancha X ya tiene un `Booking` en estado `RESERVADO` <br> **When:** el administrador intenta bloquearla <br> **Then:** el sistema rechaza el bloqueo, no se crea `ScheduleBlock` y el `Booking` existente no se ve afectado. <br><br> **Escenario 3 – Desbloqueo libera la franja:** <br> **Given:** existe un `ScheduleBlock` vigente sobre una franja <br> **When:** el administrador lo quita <br> **Then:** se emite `ScheduleUnblocked`, el `ScheduleBlock` se elimina y la franja vuelve a estar disponible para alquileres de inmediato. | EP02 |
| **US31** | Registrar y ver el motivo de un bloqueo por mantenimiento | Como administrador, quiero registrar un motivo o nota al bloquear una franja por mantenimiento, para que cualquier administrador entienda por qué está bloqueada sin tener que preguntar. | **Escenario 1 – Motivo registrado junto al bloqueo:** <br> **Given:** el administrador bloquea una franja de una cancha (US07) <br> **When:** ingresa un texto de motivo (ej. "césped en mal estado") <br> **Then:** el `ScheduleBlock` se crea con el motivo asociado. <br><br> **Escenario 2 – Motivo visible al consultar la franja bloqueada:** <br> **Given:** existe un `ScheduleBlock` con motivo registrado <br> **When:** cualquier administrador consulta esa franja en el calendario <br> **Then:** el sistema muestra el motivo junto al estado "bloqueado". <br><br> **Escenario 3 – Bloqueo sin motivo permitido:** <br> **Given:** el administrador bloquea una franja sin ingresar texto <br> **When:** confirma el bloqueo <br> **Then:** el sistema permite el registro igual — el motivo es opcional, no bloquea RF07. | EP02 |
| **US08** | Buscar y filtrar el historial de alquileres | Como administrador, quiero buscar y filtrar el historial de alquileres, para resolver dudas o reclamos de clientes rápidamente. | **Escenario 1 – Filtro con resultados:** <br> **Given:** existen `Booking` registrados con distintas fechas, canchas, clientes y estados <br> **When:** el administrador filtra por una combinación de esos criterios <br> **Then:** el sistema retorna únicamente los `Booking` que cumplen todos los criterios, sin modificar su estado. <br><br> **Escenario 2 – Filtro sin coincidencias:** <br> **Given:** los criterios seleccionados no corresponden a ningún `Booking` registrado <br> **When:** el sistema procesa la búsqueda <br> **Then:** retorna un conjunto vacío sin alterar el historial existente. | EP02 |
| **US28** | Registrar un cliente nuevo desde el formulario de alquiler | Como administrador, quiero poder crear un cliente nuevo sin salir del formulario de alquiler, para no interrumpir el registro cuando el cliente no existe todavía en el sistema. | **Escenario 1 – Cliente creado y usado en el mismo flujo:** <br> **Given:** el administrador está registrando un `Booking` (US05) y el cliente buscado no existe <br> **When:** completa nombre y contacto en el mismo formulario y confirma <br> **Then:** el sistema crea el aggregate `Customer` (emite `CustomerRegistered`), lo asocia de inmediato al `Booking` en curso, y el administrador no necesita navegar a la sección de Clientes. <br><br> **Escenario 2 – Cliente creado queda disponible después:** <br> **Given:** se creó un `Customer` desde el formulario de alquiler <br> **When:** el administrador busca ese cliente más tarde desde la sección de Clientes (EP03) <br> **Then:** aparece con su historial actualizado, igual que cualquier cliente creado desde su propia pantalla. | EP02 |
| **US32** | Registrar reservas de varias fechas (multi-día o recurrentes) | Como administrador, quiero registrar en una sola operación un alquiler que se repite en varias fechas (días consecutivos o de forma recurrente semanal), para no tener que registrar cada fecha por separado cuando un cliente reserva una serie. | **Escenario 1 – Serie registrada con todas las fechas libres:** <br> **Given:** el administrador ingresa una cancha, un horario y una lista de fechas (multi-día o recurrente), todas libres para esa cancha y horario <br> **When:** confirma el registro de la serie <br> **Then:** el sistema crea un `Booking` por cada fecha, todos vinculados por un mismo identificador de serie y numerados según su posición dentro de ella. <br><br> **Escenario 2 – Conflicto en una fecha cancela toda la serie:** <br> **Given:** una de las fechas de la serie ya tiene un `Booking` activo o un bloqueo de mantenimiento en esa cancha y horario <br> **When:** el administrador intenta confirmar la serie <br> **Then:** el sistema rechaza el registro completo — ninguna fecha de la serie queda creada — indicando la fecha específica en conflicto. <br><br> **Escenario 3 – Modo de pago de la serie:** <br> **Given:** el administrador registra una serie con modo de pago "acumulado" <br> **When:** confirma la serie <br> **Then:** el monto total se asigna únicamente a la primera fecha y el resto queda en cero; si el modo es "individual", cada fecha de la serie recibe el monto total de forma independiente. | EP02 |
| **US35** | Bloquear varias fechas por mantenimiento en una sola operación | Como administrador, quiero bloquear una misma franja horaria en varias fechas a la vez (ej. mantenimiento semanal), para no repetir el bloqueo manualmente fecha por fecha. | **Escenario 1 – Bloqueo múltiple exitoso:** <br> **Given:** ninguna de las fechas seleccionadas tiene un `Booking` activo en esa cancha y horario <br> **When:** el administrador confirma el bloqueo para varias fechas con un mismo horario y motivo <br> **Then:** el sistema crea un `ScheduleBlock` por cada fecha con el mismo motivo. <br><br> **Escenario 2 – Conflicto en una fecha detiene todo el bloqueo:** <br> **Given:** alguna de las fechas seleccionadas ya tiene un `Booking` activo en esa franja <br> **When:** el administrador intenta confirmar el bloqueo múltiple <br> **Then:** el sistema rechaza la operación completa sin crear ningún `ScheduleBlock`, indicando la fecha en conflicto. | EP02 |
| **US44** | Ver los bloqueos de mantenimiento de una cancha | Como administrador, quiero ver los bloqueos de mantenimiento vigentes y próximos de una cancha, para saber qué franjas ya están reservadas para mantenimiento sin tener que revisar todo el calendario. | **Escenario 1 – Bloqueos de una fecha específica:** <br> **Given:** una `Court` tiene uno o más `ScheduleBlock` en una fecha determinada <br> **When:** el administrador consulta los bloqueos de esa cancha y fecha <br> **Then:** el sistema retorna esos `ScheduleBlock` con su horario y motivo. <br><br> **Escenario 2 – Próximos bloqueos:** <br> **Given:** una `Court` tiene `ScheduleBlock` programados en fechas futuras <br> **When:** el administrador consulta los próximos bloqueos de esa cancha <br> **Then:** el sistema retorna únicamente los bloqueos a partir de hoy, sin incluir los ya pasados. | EP02 |
| **EP03 – Gestión de Clientes** |||||
| **US09** | Registrar, editar y eliminar clientes | Como administrador, quiero registrar, editar y eliminar clientes, para mantener actualizada la información de contacto del negocio. | **Escenario 1 – Registro exitoso:** <br> **Given:** el administrador ingresa nombre y contacto de un nuevo cliente <br> **When:** confirma el registro <br> **Then:** se crea el aggregate `Customer` y se emite `CustomerRegistered`, quedando disponible de inmediato para asociarse a un `Booking`. <br><br> **Escenario 2 – Eliminación de cliente con historial:** <br> **Given:** un `Customer` tiene `Booking` asociados en su historial <br> **When:** el administrador intenta eliminarlo <br> **Then:** el sistema conserva los `Booking` históricos intactos (referenciando al cliente por su identificador), sin romper la trazabilidad del historial existente. | EP03 |
| **US10** | Consultar historial de un cliente | Como administrador, quiero ver el historial de alquileres de un cliente, para conocer su frecuencia de uso. | **Escenario 1 – Historial con alquileres:** <br> **Given:** un `Customer` tiene uno o más `Booking` asociados <br> **When:** el administrador consulta su ficha <br> **Then:** el sistema retorna la lista de `Booking` de ese cliente ordenados por fecha, sin modificar ningún estado. <br><br> **Escenario 2 – Cliente sin alquileres:** <br> **Given:** un `Customer` fue registrado pero aún no tiene `Booking` asociados <br> **When:** el administrador consulta su ficha <br> **Then:** el sistema retorna historial vacío sin fabricar datos. | EP03 |
| **US30** | Registrar WhatsApp del cliente con acceso directo | Como administrador, quiero registrar el WhatsApp del cliente y poder abrir el chat directamente desde el sistema, para coordinar rápido sin copiar el número a mano. | **Escenario 1 – WhatsApp registrado y accesible:** <br> **Given:** el administrador registra o edita un `Customer` con un número de teléfono válido <br> **When:** guarda los cambios <br> **Then:** el `Customer` queda con el número asociado, y tanto su ficha como el detalle de sus `Booking` muestran un acceso directo (enlace `wa.me` sobre ese mismo número) para abrir el chat. <br><br> **Escenario 2 – Cliente sin número registrado:** <br> **Given:** un `Customer` no tiene teléfono registrado <br> **When:** el administrador consulta su ficha o un alquiler asociado <br> **Then:** el sistema no muestra el acceso directo, sin generar errores. | EP03 |
| **EP04 – Gestión de Canchas** |||||
| **US11** | Registrar y editar canchas | Como administrador, quiero dar de alta y editar las canchas del colegio, para mantener el sistema alineado a la infraestructura real. | **Escenario 1 – Alta exitosa:** <br> **Given:** el administrador ingresa nombre y disciplina de una cancha nueva <br> **When:** confirma el registro <br> **Then:** se crea el aggregate `Court` y se emite `CourtRegistered`. <br><br> **Escenario 2 – Nombre de cancha duplicado:** <br> **Given:** ya existe una `Court` con ese nombre <br> **When:** el administrador intenta registrar otra con el mismo nombre <br> **Then:** el sistema rechaza el registro y la `Court` existente no se altera. | EP04 |
| **US12** | Configurar precios por cancha | Como administrador, quiero configurar el precio de cada cancha, para que el sistema calcule montos correctos automáticamente. | **Escenario 1 – Precio actualizado y aplicado:** <br> **Given:** una `Court` existente con un precio configurado <br> **When:** el administrador actualiza el precio a un valor válido (mayor a cero) <br> **Then:** se emite `CourtPriceUpdated` y todo nuevo `Booking` para esa cancha calcula el monto con el precio vigente. <br><br> **Escenario 2 – Precio inválido rechazado:** <br> **Given:** el administrador intenta fijar un precio en cero o negativo <br> **When:** confirma <br> **Then:** el sistema rechaza el cambio y la `Court` conserva su precio anterior. | EP04 |
| **US13** | Ver disponibilidad consolidada de todas las canchas | Como administrador, quiero ver la disponibilidad consolidada de todas las canchas, para decidir rápido qué ofrecer a un cliente que llama. | **Escenario 1 – Vista consolidada correcta:** <br> **Given:** las 5 canchas tienen distintas combinaciones de `Booking` y `ScheduleBlock` para una fecha <br> **When:** el administrador consulta la vista consolidada <br> **Then:** el sistema retorna, en una sola respuesta, el estado de disponibilidad de las 5 canchas para esa fecha. | EP04 |
| **US29** | Adjuntar fotos a una cancha | Como administrador, quiero adjuntar una o más fotos a cada cancha, para que se identifique visualmente al momento de alquilarla. | **Escenario 1 – Foto adjuntada correctamente:** <br> **Given:** el administrador edita una `Court` existente <br> **When:** sube una imagen <br> **Then:** la foto queda asociada a la `Court` y visible en el calendario/ficha de esa cancha; para agregar varias fotos, el administrador repite la operación una vez por imagen. <br><br> **Escenario 2 – Cancha sin fotos:** <br> **Given:** una `Court` no tiene fotos adjuntas <br> **When:** se consulta su ficha <br> **Then:** el sistema muestra un estado vacío/genérico en vez de fallar, y la cancha sigue siendo alquilable con normalidad (las fotos son opcionales, no bloquean RF11). | EP04 |
| **US43** | Eliminar una cancha que ya no está en uso | Como administrador, quiero poder eliminar una cancha que el colegio ya no ofrece, para que el catálogo refleje solo la infraestructura real disponible. | **Escenario 1 – Eliminación exitosa:** <br> **Given:** una `Court` existente <br> **When:** el administrador la elimina <br> **Then:** la `Court` deja de aparecer en el catálogo y en el calendario de disponibilidad. <br><br> **Escenario 2 – Advertencia por historial asociado:** <br> **Given:** la `Court` tiene `Booking` (y sus `Payment`) asociados en su historial <br> **When:** el administrador la elimina <br> **Then:** el sistema elimina también, en cascada, todos los `Booking` y `Payment` asociados a esa cancha — por lo que la aplicación debe advertir claramente esta consecuencia antes de confirmar, ya que no es una baja lógica sino un borrado permanente del historial. | EP04 |
| **EP05 – Gestión de Pagos** |||||
| **US14** | Registrar estado de pago de un alquiler | Como administrador, quiero marcar un alquiler como pagado o pendiente, para saber qué dinero falta cobrar. | **Escenario 1 – Pago total registrado:** <br> **Given:** un `Booking` con estado de pago `PENDIENTE` <br> **When:** el administrador registra un `Payment` por el monto total <br> **Then:** se emite `PaymentRegistered`, el `Booking` transita su estado de pago a `PAGADO` y el saldo pendiente queda en cero. <br><br> **Escenario 2 – Monto excede el total del alquiler:** <br> **Given:** un `Booking` tiene un monto total definido <br> **When:** el administrador intenta registrar un `Payment` mayor a ese total <br> **Then:** el sistema rechaza el registro, protegiendo la invariante de que el pago nunca puede exceder el total adeudado. | EP05 |
| **US15** | Registrar pagos parciales | Como administrador, quiero registrar pagos parciales, para llevar control cuando el cliente abona por partes. | **Escenario 1 – Pago parcial con saldo recalculado:** <br> **Given:** un `Booking` con estado de pago `PENDIENTE` y monto total S/ 100 <br> **When:** el administrador registra un `Payment` parcial de S/ 40 <br> **Then:** se emite `PartialPaymentRegistered`, el `Booking` transita a estado de pago `PARCIAL` y el saldo pendiente queda en S/ 60. <br><br> **Escenario 2 – Suma de parciales completa el pago:** <br> **Given:** un `Booking` en estado `PARCIAL` con saldo pendiente de S/ 60 <br> **When:** el administrador registra un nuevo `Payment` de S/ 60 <br> **Then:** el `Booking` transita automáticamente a estado `PAGADO` y el saldo pendiente queda en cero. | EP05 |
| **US16** | Registrar método de pago | Como administrador, quiero registrar el método de pago usado, para tener trazabilidad de cómo se cobró cada alquiler. | **Escenario 1 – Método de pago asociado al registro:** <br> **Given:** el administrador registra un `Payment` (total o parcial) <br> **When:** selecciona el método (efectivo, Yape u otro) <br> **Then:** el `Payment` queda persistido con el método indicado, disponible en el historial del `Booking`. | EP05 |
| **US27** | Adjuntar comprobante de pago | Como administrador, quiero adjuntar una imagen del comprobante al registrar un pago, para tener respaldo visual de que el cliente pagó. | **Escenario 1 – Comprobante adjuntado correctamente:** <br> **Given:** el administrador está registrando un `Payment` <br> **When:** adjunta una imagen (captura de Yape, foto de voucher) antes de confirmar <br> **Then:** el `Payment` queda persistido con la referencia al comprobante, visible después en el historial del `Booking`. <br><br> **Escenario 2 – Pago sin comprobante permitido:** <br> **Given:** el administrador registra un `Payment` en efectivo sin comprobante físico <br> **When:** confirma sin adjuntar imagen <br> **Then:** el sistema permite el registro igualmente — el comprobante es opcional, no bloquea RF14/RF15. | EP05 |
| **US46** | Ver los pagos registrados de un alquiler | Como administrador, quiero ver todos los pagos que se han registrado para un alquiler, para verificar cuánto y cómo se pagó sin tener que preguntarle al cliente o al otro administrador. | **Escenario 1 – Historial de pagos de un alquiler:** <br> **Given:** un `Booking` tiene uno o más `Payment` registrados (totales, parciales o reversados) <br> **When:** el administrador consulta los pagos de ese alquiler <br> **Then:** el sistema retorna todos esos `Payment` con su monto, método y fecha, incluyendo si alguno fue reversado. | EP05 |
| **US47** | Ver el comprobante ya adjuntado de un pago | Como administrador, quiero poder volver a ver el comprobante que se adjuntó a un pago, para verificar el respaldo sin tener que pedírselo de nuevo al cliente. | **Escenario 1 – Comprobante disponible:** <br> **Given:** un `Booking` tiene un `Payment` con comprobante adjuntado <br> **When:** el administrador solicita verlo <br> **Then:** el sistema retorna un enlace temporal (válido por 5 minutos) para ver la imagen, sin exponer una URL pública permanente. <br><br> **Escenario 2 – Sin comprobante adjuntado:** <br> **Given:** el alquiler no tiene ningún comprobante adjunto <br> **When:** el administrador intenta verlo <br> **Then:** el sistema responde que no existe comprobante, sin generar un enlace. | EP05 |
| **EP06 – Panel Operativo del Día** |||||
| **US17** | Ver alquileres del día | Como administrador, quiero ver los alquileres del día al iniciar sesión, para saber de un vistazo qué toca hoy. | **Escenario 1 – Panel refleja alquileres activos del día:** <br> **Given:** existen `Booking` en estado `RESERVADO` para la fecha actual <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna esos `Booking`, excluyendo los que estén en estado `CANCELADO`. | EP06 |
| **US18** | Ver ingreso total del día | Como administrador, quiero ver el ingreso total del día, para llevar control diario sin sacar cuentas manualmente. | **Escenario 1 – Ingreso calculado desde pagos reales:** <br> **Given:** existen uno o más `Payment` (totales y/o parciales) registrados en la fecha actual <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna la suma exacta de esos `Payment`, sin incluir montos de alquileres aún no pagados. | EP06 |
| **US19** | Ver pagos pendientes del día | Como administrador, quiero ver los pagos pendientes del día, para hacer seguimiento a los clientes que aún deben. | **Escenario 1 – Pendientes correctamente identificados:** <br> **Given:** existen `Booking` del día con estado de pago `PENDIENTE` o `PARCIAL` <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna esos `Booking` junto con su saldo pendiente, excluyendo los que ya están en estado `PAGADO`. | EP06 |
| **EP07 – Registro y Autorización de Administradores** |||||
| **US20** | Solicitar registro de nueva cuenta de administrador | Como persona autorizada por Carlos para operar el negocio (ej. un nuevo trabajador), quiero registrar mi solicitud de cuenta, para que Carlos pueda autorizarme sin que él tenga que crear la cuenta manualmente. | **Escenario 1 – Solicitud creada en estado pendiente:** <br> **Given:** el solicitante completa nombre y correo válidos en el formulario de registro <br> **When:** confirma el envío <br> **Then:** se crea el aggregate `AccessRequest` en estado `PENDING`, se emite `RegistrationRequestCreated`, y el solicitante no obtiene ningún acceso al sistema todavía (no existe `User` hasta que se apruebe). <br><br> **Escenario 2 – Correo ya registrado o con solicitud en curso:** <br> **Given:** el correo ingresado ya pertenece a un `User` existente o a un `AccessRequest` en estado `PENDING` <br> **When:** se intenta enviar la solicitud <br> **Then:** el sistema rechaza la solicitud sin crear un duplicado. | EP07 |
| **US21** | Autorizar o rechazar solicitudes de acceso | Como administrador dueño, quiero revisar y autorizar o rechazar las solicitudes de cuenta pendientes, para controlar quién tiene acceso al negocio. | **Escenario 1 – Autorización exitosa:** <br> **Given:** existe un `AccessRequest` en estado `PENDING` y quien ejecuta la acción es el administrador dueño <br> **When:** autoriza la solicitud <br> **Then:** el `AccessRequest` transita a estado `APPROVED`, se emite `AdminAuthorized`, se crea un nuevo `User` en estado `PENDING_VERIFICATION` y se envía un correo de verificación — el solicitante aún no puede iniciar sesión hasta confirmar su correo (US34). <br><br> **Escenario 2 – Rechazo:** <br> **Given:** existe un `AccessRequest` en estado `PENDING` <br> **When:** el administrador dueño lo rechaza <br> **Then:** el `AccessRequest` transita a estado `REJECTED`, se emite `AdminRejected`, y no se crea ningún `User`. <br><br> **Escenario 3 – Un administrador no dueño intenta autorizar:** <br> **Given:** quien intenta autorizar es un `User` con rol `ADMINISTRADOR` (no dueño) <br> **When:** intenta ejecutar la acción <br> **Then:** el sistema la rechaza y el `AccessRequest` pendiente no cambia de estado. | EP07 |
| **US26** | Ver administradores activos | Como administrador dueño, quiero ver el listado de cuentas de administrador activas, para saber en todo momento quién tiene acceso al negocio. | **Escenario 1 – Listado correcto:** <br> **Given:** existen `User` en distintos estados (`ACTIVO`, `PENDING_VERIFICATION`, `INACTIVO`) y `AccessRequest` en distintos estados (`PENDING`, `APPROVED`, `REJECTED`) <br> **When:** el administrador dueño consulta el listado de activos <br> **Then:** el sistema retorna únicamente los `User` en estado `ACTIVO`, sin exponer las solicitudes pendientes o rechazadas en esa misma vista (esas viven en US21). | EP07 |
| **US34** | Verificar mi correo antes de acceder al sistema | Como solicitante de una cuenta de administrador ya autorizada por el dueño, quiero confirmar la propiedad de mi correo mediante un enlace de verificación, para evitar quedar con una cuenta activa pero inaccesible si escribí mal mi correo al solicitar acceso. | **Escenario 1 – Verificación exitosa:** <br> **Given:** la cuenta fue autorizada (`AdminAuthorized`) y el `User` fue creado en estado `PENDING_VERIFICATION`, con un correo de verificación enviado <br> **When:** el solicitante abre el enlace dentro del plazo de validez <br> **Then:** el `User` pasa a estado `ACTIVO` y puede iniciar sesión (US01). <br><br> **Escenario 2 – Enlace expirado o inválido:** <br> **Given:** el enlace de verificación expiró o ya fue usado <br> **When:** el solicitante intenta abrirlo <br> **Then:** el sistema rechaza la verificación y ofrece reenviar un nuevo enlace, sin activar la cuenta. | EP07 |
| **US39** | Promover a otro administrador a dueño | Como administrador dueño, quiero poder ceder o compartir el rol de dueño con otro administrador de confianza, para no depender de una sola persona para autorizar solicitudes de acceso. | **Escenario 1 – Promoción exitosa:** <br> **Given:** un `User` activo con rol administrador (no dueño) <br> **When:** el administrador dueño lo promueve <br> **Then:** ese `User` pasa a tener permisos de dueño (puede autorizar/rechazar solicitudes, promover y desactivar administradores). <br><br> **Escenario 2 – Solo el dueño puede promover:** <br> **Given:** quien intenta la acción no es el administrador dueño <br> **When:** intenta promover a otro `User` <br> **Then:** el sistema rechaza la operación y ningún rol cambia. | EP07 |
| **US40** | Desactivar la cuenta de un administrador | Como administrador dueño, quiero poder desactivar la cuenta de un administrador que ya no debería tener acceso, para revocar su acceso al negocio de forma inmediata. | **Escenario 1 – Desactivación exitosa:** <br> **Given:** un `User` activo con rol administrador <br> **When:** el administrador dueño lo desactiva <br> **Then:** el `User` pasa a estado inactivo, sus sesiones activas se invalidan y no puede volver a iniciar sesión. <br><br> **Escenario 2 – Un administrador no puede desactivar a otro sin ser dueño:** <br> **Given:** quien intenta la acción no es el administrador dueño <br> **When:** intenta desactivar a otro `User` <br> **Then:** el sistema rechaza la operación. | EP07 |
| **EP08 – Confirmación por Correo** |||||
| **US22** | Recibir correo de confirmación al registrar un alquiler | Como cliente del negocio, quiero recibir un correo de confirmación cuando se registra mi alquiler, para tener un respaldo del acuerdo sin depender solo de la palabra del administrador. | **Escenario 1 – Correo enviado con cliente con correo registrado:** <br> **Given:** un `Booking` se registra (`BookingRegistered`) y el `Customer` asociado tiene correo registrado <br> **When:** el subdominio Notifications procesa el evento <br> **Then:** se envía un correo de confirmación con los datos del alquiler y se emite `ConfirmationEmailSent`. <br><br> **Escenario 2 – Cliente sin correo registrado:** <br> **Given:** el `Customer` asociado al `Booking` no tiene correo registrado <br> **When:** se procesa `BookingRegistered` <br> **Then:** no se intenta ningún envío y el `Booking` se registra con normalidad, sin errores visibles para el administrador. <br><br> **Escenario 3 – Fallo de envío no revierte el alquiler:** <br> **Given:** el proveedor de correo (Resend) no responde o falla <br> **When:** el sistema intenta enviar la confirmación <br> **Then:** el `Booking` permanece registrado sin cambios (RF24); el fallo queda registrado en logs para revisión posterior, no bloquea al administrador. | EP08 |
| **US23** | Recibir correo con el resultado de mi solicitud de acceso | Como solicitante de una cuenta de administrador, quiero recibir un correo cuando mi solicitud sea autorizada o rechazada, para saber si ya puedo ingresar al sistema. | **Escenario 1 – Correo de autorización:** <br> **Given:** se emite `AdminAuthorized` para un `AccessRequest` <br> **When:** el subdominio Notifications procesa el evento <br> **Then:** se envía un correo al solicitante indicando que su cuenta fue autorizada, junto con el enlace de verificación de correo (US34). <br><br> **Escenario 2 – Correo de rechazo:** <br> **Given:** se emite `AdminRejected` <br> **When:** el subdominio Notifications procesa el evento <br> **Then:** se envía un correo indicando que la solicitud fue rechazada, sin exponer el motivo interno de la decisión. | EP08 |
| **EP09 – Ajustes de Cuenta** |||||
| **US24** | Actualizar mi correo | Como administrador autenticado, quiero actualizar mi propio correo, para mantenerlo vigente sin depender de soporte técnico. | **Escenario 1 – Correo actualizado:** <br> **Given:** el administrador está autenticado <br> **When:** ingresa un nuevo correo válido y no usado por otro `User` <br> **Then:** el `User` actualiza su correo y este queda disponible de inmediato para el próximo inicio de sesión. <br><br> **Escenario 2 – Correo ya en uso:** <br> **Given:** el nuevo correo ya pertenece a otro `User` <br> **When:** intenta guardar el cambio <br> **Then:** el sistema rechaza la actualización y el correo original se mantiene sin cambios. | EP09 |
| **US25** | Cambiar mi contraseña | Como administrador autenticado, quiero cambiar mi propia contraseña, para mantener segura mi cuenta. | **Escenario 1 – Cambio exitoso:** <br> **Given:** el administrador ingresa su contraseña actual correctamente y una nueva contraseña válida <br> **When:** confirma el cambio <br> **Then:** la contraseña se actualiza (hasheada con bcrypt) y las sesiones activas en otros dispositivos se invalidan. <br><br> **Escenario 2 – Contraseña actual incorrecta:** <br> **Given:** el administrador ingresa mal su contraseña actual <br> **When:** intenta confirmar el cambio <br> **Then:** el sistema rechaza la operación y la contraseña original no se modifica. | EP09 |
| **US41** | Actualizar mi perfil y foto de administrador | Como administrador autenticado, quiero poder actualizar mis datos de perfil y mi foto, para que mi cuenta refleje información actualizada. | **Escenario 1 – Perfil actualizado:** <br> **Given:** el administrador está autenticado <br> **When:** actualiza sus datos de perfil (ej. nombre) <br> **Then:** el `User` queda actualizado con los nuevos datos. <br><br> **Escenario 2 – Foto de perfil subida y removida:** <br> **Given:** el administrador sube una imagen como foto de perfil <br> **When:** la reemplaza o la elimina más adelante <br> **Then:** el sistema guarda solo la más reciente, eliminando la anterior del almacenamiento (Supabase Storage). | EP09 |
| **US42** | Dar de baja mi propia cuenta de administrador | Como administrador autenticado, quiero poder desactivar mi propia cuenta, para dejar de tener acceso al sistema cuando ya no trabajo en el negocio. | **Escenario 1 – Baja exitosa:** <br> **Given:** el administrador está autenticado <br> **When:** solicita dar de baja su propia cuenta <br> **Then:** el `User` pasa a estado inactivo y sus sesiones activas (incluida la actual) se invalidan. | EP09 |
| **EP10 – Notificaciones Internas entre Administradores** |||||
| **US38** | Ver notificaciones internas de la operación del negocio | Como administrador, quiero ver un listado de notificaciones cuando otro administrador registra un alquiler, una serie de reservas o bloquea una franja por mantenimiento, para estar al tanto de lo que hace el otro sin tener que preguntarle directamente. | **Escenario 1 – Notificación generada por la acción de otro administrador:** <br> **Given:** el trabajador registra un `Booking`, una serie de reservas o un bloqueo de mantenimiento <br> **When:** Carlos consulta su listado de notificaciones <br> **Then:** aparece una notificación describiendo la acción, dirigida únicamente a los administradores distintos de quien la ejecutó. <br><br> **Escenario 2 – Marcar notificación como leída:** <br> **Given:** existe una notificación sin leer <br> **When:** el administrador la marca como leída <br> **Then:** la notificación deja de contarse como pendiente para ese administrador. | EP10 |

<br>

### Technical Stories

| **ID** | **Título** | **Descripción** | **Criterios de Aceptación** | **Epic ID** |
|---|---|---|---|---|
| **TS01** | Endpoint de registro de alquiler con validación de doble reserva | Como Developer, quiero implementar el endpoint de registro de `Booking` en Express validando la invariante de exclusividad de horario a nivel de transacción de base de datos. | **Escenario 1 – Registro exitoso (201):** <br> **Given:** POST `/api/bookings` con cancha y franja libres <br> **When:** el servidor procesa dentro de una transacción <br> **Then:** crea el `Booking`, emite `BookingRegistered` y retorna 201. <br><br> **Escenario 2 – Conflicto de horario (409):** <br> **Given:** la franja solicitada ya está ocupada por otro `Booking` activo <br> **When:** el servidor evalúa los `Booking` activos superpuestos dentro de la misma transacción <br> **Then:** retorna 409, no persiste el nuevo registro y responde con el `Booking` en conflicto. | EP02 |
| **TS02** | Endpoint de login y emisión de JWT | Como Developer, quiero implementar el endpoint de autenticación en Express para emitir un JWT a los administradores válidos. | **Escenario 1 – Login exitoso (200):** <br> **Given:** POST `/api/auth/login` con credenciales válidas de un `User` <br> **When:** el servidor valida el hash de la contraseña <br> **Then:** retorna 200 con JWT y expiración. <br><br> **Escenario 2 – Credenciales inválidas (401):** <br> **Given:** contraseña incorrecta <br> **When:** el servidor valida <br> **Then:** retorna 401 sin emitir token. | EP01 |
| **TS03** | Endpoint de registro de pagos con recálculo de saldo | Como Developer, quiero implementar el endpoint de registro de `Payment` en Express, recalculando el saldo pendiente del `Booking` asociado en una misma transacción. | **Escenario 1 – Pago parcial registrado (201):** <br> **Given:** POST `/api/payments` con monto menor al saldo pendiente del `Booking` <br> **When:** el servidor procesa <br> **Then:** crea el `Payment`, actualiza el estado del `Booking` a `PARCIAL`, emite `PartialPaymentRegistered` y retorna 201 con el nuevo saldo. <br><br> **Escenario 2 – Monto excede saldo pendiente (400):** <br> **Given:** el monto enviado es mayor al saldo pendiente <br> **When:** el servidor valida <br> **Then:** retorna 400 y no persiste el pago. | EP05 |
| **TS04** | Endpoint de health check | Como Developer, quiero implementar un endpoint `/health` en Express para verificar que el backend y la conexión a base de datos estén operativos, dado que Render suspende el servicio por inactividad. | **Escenario 1 – Sistema operativo (200):** <br> **Given:** el backend está corriendo y la conexión a PostgreSQL responde <br> **When:** se consulta GET `/health` <br> **Then:** retorna 200 con estado `ok`. <br><br> **Escenario 2 – Base de datos no disponible (503):** <br> **Given:** la conexión a PostgreSQL falla <br> **When:** se consulta GET `/health` <br> **Then:** retorna 503, permitiendo detectar el problema antes de que Carlos reporte que "la app no funciona". | EP02 |
| **TS05** | Endpoints de solicitud y autorización de cuentas de administrador | Como Developer, quiero implementar los endpoints de registro de solicitud y de autorización/rechazo, restringiendo la autorización al rol de administrador dueño. | **Escenario 1 – Solicitud creada (201):** <br> **Given:** POST `/api/users/solicitudes` con nombre y correo no registrados <br> **When:** el servidor procesa <br> **Then:** crea `AccessRequest` en estado `PENDING`, emite `RegistrationRequestCreated` y retorna 201. <br><br> **Escenario 2 – Autorización restringida al dueño (200/403):** <br> **Given:** PATCH `/api/users/solicitudes/{id}/autorizar` <br> **When:** el token del solicitante no corresponde a un administrador con rol dueño <br> **Then:** retorna 403 y el `AccessRequest` no cambia de estado; si el rol es correcto, retorna 200, crea el `User` en `PENDING_VERIFICATION` y emite `AdminAuthorized`. | EP07 |
| **TS06** | Listener de correo de confirmación sobre `BookingRegistered` | Como Developer, quiero implementar un listener desacoplado del endpoint de alquiler que reaccione a `BookingRegistered` y envíe el correo de confirmación vía Resend, sin bloquear la respuesta HTTP del registro del alquiler. | **Escenario 1 – Envío asíncrono exitoso:** <br> **Given:** se emite `BookingRegistered` para un `Booking` con `Customer` con correo <br> **When:** el listener procesa el evento <br> **Then:** llama a la API de Resend, y en caso de éxito emite `ConfirmationEmailSent`; el endpoint TS01 ya respondió 201 antes de que esto ocurra. <br><br> **Escenario 2 – Fallo del proveedor no afecta el alquiler (RF24):** <br> **Given:** la API de Resend retorna error <br> **When:** el listener lo captura <br> **Then:** registra el error en logs, no reintenta de forma bloqueante y el `Booking` permanece intacto. | EP08 |
| **TS07** | Endpoints de ajustes de cuenta (correo y contraseña) | Como Developer, quiero implementar los endpoints de actualización de correo y cambio de contraseña, validando la identidad del `User` autenticado. | **Escenario 1 – Cambio de correo (200/409):** <br> **Given:** PATCH `/api/users/me/correo` con correo no usado <br> **When:** el servidor procesa <br> **Then:** retorna 200; si el correo ya existe, retorna 409 sin modificar el `User`. <br><br> **Escenario 2 – Cambio de contraseña (200/401):** <br> **Given:** PATCH `/api/users/me/contrasena` con la contraseña actual y una nueva <br> **When:** el servidor valida el hash actual <br> **Then:** retorna 200 y actualiza el hash; si la contraseña actual no coincide, retorna 401 sin cambios. | EP09 |
| **TS08** | Endpoint de carga de comprobante de pago con almacenamiento en la nube | Como Developer, quiero implementar el endpoint que recibe una imagen de comprobante, la sube a un servicio de almacenamiento de archivos y guarda la referencia en el `Payment`. | **Escenario 1 – Comprobante subido (201):** <br> **Given:** POST `/api/payments/{id}/comprobante` con una imagen válida (jpg/png, tamaño razonable) <br> **When:** el servidor sube la imagen al servicio de almacenamiento <br> **Then:** guarda la URL resultante en el `Payment` y retorna 201. <br><br> **Escenario 2 – Archivo inválido (400):** <br> **Given:** el archivo no es una imagen o excede el tamaño máximo permitido <br> **When:** el servidor valida <br> **Then:** retorna 400 y no persiste ninguna referencia en el `Payment`. | EP05 |
| **TS09** | Endpoint de alquiler con creación de cliente embebida | Como Developer, quiero extender el endpoint de registro de `Booking` (TS01) para aceptar opcionalmente los datos de un cliente nuevo y crearlo en la misma transacción antes de asociarlo. | **Escenario 1 – Alquiler y cliente creados en una sola operación (201):** <br> **Given:** POST `/api/bookings` incluye un bloque `clienteNuevo` en vez de un `clienteId` existente <br> **When:** el servidor procesa dentro de una transacción <br> **Then:** crea el `Customer`, emite `CustomerRegistered`, crea el `Booking` asociado, emite `BookingRegistered` y retorna 201 con ambos identificadores. <br><br> **Escenario 2 – Conflicto de horario revierte también al cliente (rollback, 409):** <br> **Given:** la franja solicitada ya está ocupada <br> **When:** el servidor detecta el conflicto dentro de la misma transacción <br> **Then:** revierte la creación del `Customer` también (no debe quedar un cliente huérfano de un alquiler fallido) y retorna 409. | EP02 |
| **TS10** | Endpoint de carga de fotos de cancha | Como Developer, quiero implementar el endpoint que recibe una imagen de una `Court` a la vez, la sube a Supabase Storage (mismo servicio que TS08) y guarda la URL resultante en el arreglo de fotos de la cancha. | **Escenario 1 – Foto subida (201):** <br> **Given:** POST `/api/courts/{id}/fotos` con una imagen válida <br> **When:** el servidor la sube al bucket de Storage <br> **Then:** agrega la URL al arreglo de fotos de la `Court` y retorna 201. <br><br> **Escenario 2 – Archivo inválido (400):** <br> **Given:** el archivo no es imagen o excede el tamaño máximo <br> **When:** el servidor valida <br> **Then:** retorna 400 sin modificar las fotos existentes de la `Court`. | EP04 |
| **TS11** | Endpoint de verificación de correo con token de confirmación | Como Developer, quiero implementar el endpoint que valida el token de verificación enviado por correo y activa la cuenta del `User` solo si el token es válido y no ha expirado. | **Escenario 1 – Verificación exitosa (200):** <br> **Given:** GET `/api/users/verificar?token=...` con un token válido y vigente <br> **When:** el servidor lo valida <br> **Then:** el `User` pasa a estado `ACTIVO`, se invalida el token usado, y retorna 200. <br><br> **Escenario 2 – Token inválido o expirado (400):** <br> **Given:** el token no existe, ya fue usado o expiró <br> **When:** el servidor lo valida <br> **Then:** retorna 400 sin activar ninguna cuenta. | EP07 |
| **TS12** | Endpoint de registro de reservas en serie (multi-día/recurrente) | Como Developer, quiero implementar el endpoint que registra múltiples `Booking` vinculados por un identificador de serie dentro de una sola transacción, revirtiendo la serie completa si cualquier fecha tiene conflicto. | **Escenario 1 – Serie creada (201):** <br> **Given:** POST `/api/bookings/serie` con un arreglo de fechas todas libres <br> **When:** el servidor procesa dentro de una transacción <br> **Then:** crea un `Booking` por fecha con el mismo identificador de serie, emite `BookingRegistered` por cada uno y retorna 201 con el arreglo completo. <br><br> **Escenario 2 – Rollback total ante conflicto (409):** <br> **Given:** una de las fechas del arreglo ya tiene un `Booking` activo o un bloqueo en esa cancha/horario <br> **When:** el servidor la detecta dentro de la misma transacción <br> **Then:** revierte todas las fechas ya creadas en esa transacción, no persiste ningún `Booking` de la serie y retorna 409 indicando la fecha en conflicto. | EP02 |
| **TS13** | Endpoint de bloqueo de mantenimiento en varias fechas | Como Developer, quiero implementar el endpoint que crea múltiples `ScheduleBlock` (uno por fecha) para una misma franja horaria, validando conflictos contra `Booking` activos antes de crear cualquiera de ellos. | **Escenario 1 – Bloqueo múltiple creado (201):** <br> **Given:** POST con cancha, horario, motivo y varias fechas sin conflicto <br> **When:** el servidor valida cada fecha <br> **Then:** crea un `ScheduleBlock` por fecha y retorna 201. <br><br> **Escenario 2 – Conflicto detiene la operación completa (409):** <br> **Given:** alguna fecha tiene un `Booking` activo en esa franja <br> **When:** el servidor la valida <br> **Then:** no crea ningún `ScheduleBlock` y retorna 409 indicando la fecha en conflicto. | EP02 |
| **TS14** | Endpoints de recuperación de contraseña olvidada | Como Developer, quiero implementar los endpoints de solicitud y confirmación de restablecimiento de contraseña, usando un token de un solo uso con expiración. | **Escenario 1 – Solicitud de restablecimiento (200 siempre):** <br> **Given:** POST `/api/auth/olvide-password` con un correo <br> **When:** el servidor procesa <br> **Then:** genera un token hasheado con expiración, envía el correo si el `User` existe, y retorna 200 en ambos casos (exista o no la cuenta), para no revelar si un correo está registrado. <br><br> **Escenario 2 – Restablecimiento (200/400):** <br> **Given:** POST `/api/auth/restablecer-password` con un token y nueva contraseña <br> **When:** el servidor valida el token <br> **Then:** si es válido y no expiró, actualiza la contraseña e invalida las sesiones activas, retornando 200; si es inválido o expiró, retorna 400 sin cambios. | EP01 |
| **TS15** | Endpoints de notificaciones internas entre administradores | Como Developer, quiero implementar los endpoints de listado y marcado de notificaciones internas, generadas automáticamente cuando un administrador registra un alquiler, una serie o un bloqueo de mantenimiento. | **Escenario 1 – Listado (200):** <br> **Given:** GET `/api/notifications` de un administrador autenticado <br> **When:** el servidor consulta <br> **Then:** retorna únicamente las notificaciones dirigidas a ese `User`. <br><br> **Escenario 2 – Marcado como leída (204):** <br> **Given:** PATCH `/api/notifications/{id}/leida` <br> **When:** el servidor procesa <br> **Then:** la notificación queda marcada como leída y retorna 204. | EP10 |
| **TS16** | Endpoints de promoción, desactivación y perfil propio de administradores | Como Developer, quiero implementar los endpoints de promoción a dueño, desactivación de administradores (por el dueño o por sí mismos), y actualización de perfil/foto propia, restringiendo las acciones sobre otras cuentas al rol dueño. | **Escenario 1 – Promoción y desactivación restringidas al dueño (200/403):** <br> **Given:** PATCH `/api/users/{id}/promover-dueno` o DELETE `/api/users/{id}` <br> **When:** quien ejecuta la acción no tiene rol dueño <br> **Then:** retorna 403 y el `User` objetivo no cambia; si el rol es correcto, aplica el cambio y retorna 200/204. <br><br> **Escenario 2 – Perfil y foto propios (200):** <br> **Given:** PATCH `/api/users/me/perfil` o POST/DELETE `/api/users/{id}/foto` ejecutado por el propio dueño de la cuenta <br> **When:** el servidor procesa <br> **Then:** actualiza el perfil o la foto (reemplazando/eliminando el archivo anterior en Supabase Storage) y retorna 200. | EP09 |
| **TS17** | Endpoint de eliminación de cancha con borrado en cascada | Como Developer, quiero implementar el endpoint que elimina una `Court`, documentando explícitamente que la base de datos está configurada con `onDelete: Cascade` desde `Booking` y `Payment` hacia `Court`, por lo que este borrado es permanente y arrastra todo el historial asociado. | **Escenario 1 – Eliminación exitosa (204):** <br> **Given:** DELETE `/api/courts/{id}` sobre una `Court` existente <br> **When:** el servidor procesa <br> **Then:** elimina la `Court` (y en cascada sus `Booking` y `Payment` asociados por la relación de base de datos) y retorna 204. <br><br> **Escenario 2 – Cancha inexistente (404):** <br> **Given:** el `id` no corresponde a ninguna `Court` <br> **When:** el servidor la busca <br> **Then:** retorna 404 sin ejecutar ningún borrado. | EP04 |
| **TS18** | Endpoint de desbloqueo de una franja de mantenimiento | Como Developer, quiero implementar el endpoint que elimina un `ScheduleBlock` por su identificador, liberando la franja de inmediato. | **Escenario 1 – Desbloqueo exitoso (204):** <br> **Given:** DELETE `/api/courts/bloqueos/{blockId}` sobre un `ScheduleBlock` existente <br> **When:** el servidor procesa <br> **Then:** elimina el `ScheduleBlock`, emite `ScheduleUnblocked` y retorna 204. | EP02 |
| **TS19** | Endpoints de listado de bloqueos de mantenimiento (por fecha y próximos) | Como Developer, quiero implementar los endpoints que listan los `ScheduleBlock` de una cancha para una fecha específica y los próximos a partir de hoy. | **Escenario 1 – Bloqueos de una fecha (200):** <br> **Given:** GET `/api/courts/{id}/bloqueos?fecha=...` <br> **When:** el servidor consulta <br> **Then:** retorna los `ScheduleBlock` de esa cancha y fecha. <br><br> **Escenario 2 – Próximos bloqueos (200):** <br> **Given:** GET `/api/courts/{id}/bloqueos/proximos` <br> **When:** el servidor consulta desde el inicio del día actual <br> **Then:** retorna solo los `ScheduleBlock` futuros, excluyendo los ya pasados. | EP02 |
| **TS20** | Endpoint de configuración inicial de la cuenta dueño | Como Developer, quiero implementar el endpoint de bootstrap que crea la primera cuenta dueño, protegido por un `SETUP_TOKEN` de servidor y bloqueado permanentemente después del primer uso. | **Escenario 1 – Bootstrap exitoso (201):** <br> **Given:** POST `/api/auth/bootstrap-dueno` con el `SETUP_TOKEN` correcto y sin ningún dueño existente <br> **When:** el servidor valida <br> **Then:** crea el primer `User` con `isOwner: true` y retorna 201. <br><br> **Escenario 2 – Token inválido o ya configurado (403/409):** <br> **Given:** el token no coincide con `SETUP_TOKEN`, o ya existe al menos un dueño <br> **When:** el servidor valida <br> **Then:** retorna 403 (token inválido) o 409 (ya configurado), sin crear ninguna cuenta. | EP01 |
| **TS21** | Endpoint de listado de pagos de un alquiler | Como Developer, quiero implementar el endpoint que retorna todos los `Payment` asociados a un `Booking`, incluyendo los reversados. | **Escenario 1 – Listado (200):** <br> **Given:** GET `/api/payments/{bookingId}` <br> **When:** el servidor consulta <br> **Then:** retorna el arreglo de `Payment` de ese `Booking`, ordenado por fecha, incluyendo su estado de reversión. | EP05 |
| **TS22** | Endpoint de visualización de comprobante con URL firmada | Como Developer, quiero implementar el endpoint que genera una URL firmada temporal (300 segundos) hacia el comprobante ya almacenado en Supabase Storage, sin exponer una URL pública permanente. | **Escenario 1 – URL firmada generada (200):** <br> **Given:** GET `/api/payments/{bookingId}/comprobante` sobre un `Payment` con comprobante adjunto <br> **When:** el servidor genera la URL firmada <br> **Then:** retorna 200 con la URL y su tiempo de expiración (300 segundos). <br><br> **Escenario 2 – Sin comprobante (404):** <br> **Given:** el `Booking` no tiene ningún `Payment` con comprobante adjunto <br> **When:** se consulta <br> **Then:** retorna 404 sin generar ninguna URL. | EP05 |

<br>

## 2.5. Product Backlog

>*El Product Backlog consolida las funcionalidades priorizadas por valor operacional para el negocio de "La Canchita de Carlos". Las historias están estimadas en Story Points (escala Fibonacci) y ordenadas por impacto operacional y dependencias funcionales: el subdominio núcleo (Bookings) precede a los subdominios de soporte (Customers, Canchas, Payments, Panel), porque ahí se concentra el riesgo de negocio más alto — la doble reserva. Las Technical Stories se listan al final para no contaminar la priorización por valor de negocio. Los aggregates raíz y Domain Events referenciados en las historias fueron derivados del Event Storming: los comandos identificados se tradujeron en comportamientos de dominio encapsulados en `Booking`, `Court`, `Customer`, `Payment`, `AccessRequest`, `User` y `Notification`.*

<br>

**Total de Story Points: 177 | Total de historias: 67 (45 User Stories + 22 Technical Stories)**

<br>

| **N°** | **Story ID** | **Épica** | **Título** | **Descripción** | **Story Points** |
|---|---|---|---|---|---|
| 1 | **US01** | EP01 – Identidad y Acceso | Iniciar sesión de forma segura | Como administrador, quiero iniciar sesión con mis credenciales para acceder únicamente si soy un usuario autorizado del negocio. | 3 |
| 2 | **US02** | EP01 – Identidad y Acceso | Operar con múltiples cuentas de administrador | Como administrador, quiero que exista más de una cuenta activa para que Carlos y su trabajador operen en paralelo sin bloquearse mutuamente. | 2 |
| 3 | **US03** | EP01 – Identidad y Acceso | Proteger la información del negocio sin sesión válida | Como administrador, quiero que ningún dato del negocio sea accesible sin sesión iniciada, para proteger información operativa y financiera. | 2 |
| 4 | **US04** | EP02 – Gestión de Reservas | Visualizar disponibilidad de canchas | Como administrador, quiero ver la disponibilidad de las 5 canchas en vista diaria, semanal y mensual, para planificar rápido los alquileres. | 5 |
| 5 | **US05** | EP02 – Gestión de Reservas | Registrar, editar y cancelar un alquiler | Como administrador, quiero registrar, editar y cancelar un alquiler, para que el sistema refleje exactamente lo acordado con el cliente. | 5 |
| 6 | **US06** | EP02 – Gestión de Reservas | Impedir la doble reserva de una cancha | Como administrador, quiero que el sistema impida crear un alquiler en un horario ya ocupado, para que nunca ocurra una doble reserva. | 5 |
| 7 | **US07** | EP02 – Gestión de Reservas | Bloquear y desbloquear una franja por mantenimiento | Como administrador, quiero bloquear manualmente una franja de una cancha por mantenimiento y poder quitar ese bloqueo cuando ya no aplica. | 3 |
| 8 | **US08** | EP02 – Gestión de Reservas | Buscar y filtrar el historial de alquileres | Como administrador, quiero buscar y filtrar el historial de alquileres, para resolver dudas o reclamos de clientes rápidamente. | 3 |
| 9 | **US09** | EP03 – Gestión de Clientes | Registrar, editar y eliminar clientes | Como administrador, quiero registrar, editar y eliminar clientes, para mantener actualizada la información de contacto del negocio. | 3 |
| 10 | **US10** | EP03 – Gestión de Clientes | Consultar historial de un cliente | Como administrador, quiero ver el historial de alquileres de un cliente, para conocer su frecuencia de uso. | 2 |
| 11 | **US11** | EP04 – Gestión de Canchas | Registrar y editar canchas | Como administrador, quiero dar de alta y editar las canchas del colegio, para mantener el sistema alineado a la infraestructura real. | 3 |
| 12 | **US12** | EP04 – Gestión de Canchas | Configurar precios por cancha | Como administrador, quiero configurar el precio de cada cancha, para que el sistema calcule montos correctos automáticamente. | 2 |
| 13 | **US13** | EP04 – Gestión de Canchas | Ver disponibilidad consolidada de todas las canchas | Como administrador, quiero ver la disponibilidad consolidada de todas las canchas, para decidir rápido qué ofrecer a un cliente que llama. | 3 |
| 14 | **US14** | EP05 – Gestión de Pagos | Registrar estado de pago de un alquiler | Como administrador, quiero marcar un alquiler como pagado o pendiente, para saber qué dinero falta cobrar. | 3 |
| 15 | **US15** | EP05 – Gestión de Pagos | Registrar pagos parciales | Como administrador, quiero registrar pagos parciales, para llevar control cuando el cliente abona por partes. | 5 |
| 16 | **US16** | EP05 – Gestión de Pagos | Registrar método de pago | Como administrador, quiero registrar el método de pago usado, para tener trazabilidad de cómo se cobró cada alquiler. | 1 |
| 17 | **US17** | EP06 – Panel Operativo del Día | Ver alquileres del día | Como administrador, quiero ver los alquileres del día al iniciar sesión, para saber de un vistazo qué toca hoy. | 2 |
| 18 | **US18** | EP06 – Panel Operativo del Día | Ver ingreso total del día | Como administrador, quiero ver el ingreso total del día, para llevar control diario sin sacar cuentas manualmente. | 2 |
| 19 | **US19** | EP06 – Panel Operativo del Día | Ver pagos pendientes del día | Como administrador, quiero ver los pagos pendientes del día, para hacer seguimiento a los clientes que aún deben. | 2 |
| 20 | **TS01** | EP02 – Gestión de Reservas | Endpoint de alquiler con validación de conflicto | Como Developer, quiero implementar el endpoint de registro de `Booking` en Express validando la invariante de exclusividad de horario a nivel de transacción de base de datos. | 3 |
| 21 | **TS02** | EP01 – Identidad y Acceso | Endpoint de login y emisión de JWT | Como Developer, quiero implementar el endpoint de autenticación en Express para emitir un JWT a los administradores válidos. | 2 |
| 22 | **TS03** | EP05 – Gestión de Pagos | Endpoint de pagos con recálculo de saldo | Como Developer, quiero implementar el endpoint de registro de `Payment` en Express, recalculando el saldo pendiente del `Booking` asociado en una misma transacción. | 3 |
| 23 | **TS04** | EP02 – Gestión de Reservas | Endpoint de health check | Como Developer, quiero implementar un endpoint `/health` en Express para verificar que el backend y la base de datos estén operativos, dado que Render suspende el servicio por inactividad. | 1 |
| 24 | **US20** | EP07 – Registro y Autorización de Administradores | Solicitar registro de nueva cuenta de administrador | Como persona autorizada por Carlos para operar el negocio, quiero registrar mi solicitud de cuenta, para que Carlos pueda autorizarme sin crearla él manualmente. | 3 |
| 25 | **US21** | EP07 – Registro y Autorización de Administradores | Autorizar o rechazar solicitudes de acceso | Como administrador dueño, quiero revisar y autorizar o rechazar solicitudes de cuenta pendientes, para controlar quién tiene acceso al negocio. | 3 |
| 26 | **US22** | EP08 – Confirmación por Correo | Recibir correo de confirmación al registrar un alquiler | Como cliente del negocio, quiero recibir un correo de confirmación cuando se registra mi alquiler, para tener un respaldo del acuerdo. | 3 |
| 27 | **US23** | EP08 – Confirmación por Correo | Recibir correo con el resultado de mi solicitud de acceso | Como solicitante de una cuenta de administrador, quiero recibir un correo cuando mi solicitud sea autorizada o rechazada. | 2 |
| 28 | **TS05** | EP07 – Registro y Autorización de Administradores | Endpoints de solicitud y autorización de cuentas | Como Developer, quiero implementar los endpoints de registro de solicitud y de autorización/rechazo, restringiendo la autorización al rol de administrador dueño. | 3 |
| 29 | **TS06** | EP08 – Confirmación por Correo | Listener de correo de confirmación sobre `BookingRegistered` | Como Developer, quiero implementar un listener desacoplado que reaccione a `BookingRegistered` y envíe el correo vía Resend, sin bloquear la respuesta HTTP del registro. | 3 |
| 30 | **US26** | EP07 – Registro y Autorización de Administradores | Ver administradores activos | Como administrador dueño, quiero ver el listado de cuentas de administrador activas, para saber en todo momento quién tiene acceso al negocio. | 2 |
| 31 | **US27** | EP05 – Gestión de Pagos | Adjuntar comprobante de pago | Como administrador, quiero adjuntar una imagen del comprobante al registrar un pago, para tener respaldo visual de que el cliente pagó. | 3 |
| 32 | **US28** | EP02 – Gestión de Reservas | Registrar un cliente nuevo desde el formulario de alquiler | Como administrador, quiero poder crear un cliente nuevo sin salir del formulario de alquiler, para no interrumpir el registro cuando el cliente no existe todavía. | 3 |
| 33 | **US24** | EP09 – Ajustes de Cuenta | Actualizar mi correo | Como administrador autenticado, quiero actualizar mi propio correo, para mantenerlo vigente sin depender de soporte técnico. | 2 |
| 34 | **US25** | EP09 – Ajustes de Cuenta | Cambiar mi contraseña | Como administrador autenticado, quiero cambiar mi propia contraseña, para mantener segura mi cuenta. | 2 |
| 35 | **TS07** | EP09 – Ajustes de Cuenta | Endpoints de ajustes de cuenta (correo y contraseña) | Como Developer, quiero implementar los endpoints de actualización de correo y cambio de contraseña, validando la identidad del `User` autenticado. | 3 |
| 36 | **TS08** | EP05 – Gestión de Pagos | Endpoint de carga de comprobante con almacenamiento en la nube | Como Developer, quiero implementar el endpoint que recibe una imagen de comprobante, la sube a Supabase Storage y guarda la referencia en el `Payment`. | 5 |
| 37 | **TS09** | EP02 – Gestión de Reservas | Endpoint de alquiler con creación de cliente embebida | Como Developer, quiero extender el endpoint de registro de `Booking` para aceptar opcionalmente datos de un cliente nuevo y crearlo en la misma transacción. | 2 |
| 38 | **US29** | EP04 – Gestión de Canchas | Adjuntar fotos a una cancha | Como administrador, quiero adjuntar una o más fotos a cada cancha, para que se identifique visualmente al momento de alquilarla. | 3 |
| 39 | **US30** | EP03 – Gestión de Clientes | Registrar WhatsApp del cliente con acceso directo | Como administrador, quiero registrar el WhatsApp del cliente y poder abrir el chat directamente desde el sistema, para coordinar rápido sin copiar el número a mano. | 2 |
| 40 | **TS10** | EP04 – Gestión de Canchas | Endpoint de carga de fotos de cancha | Como Developer, quiero implementar el endpoint que recibe una imagen de una `Court` a la vez, la sube a Supabase Storage (mismo servicio que TS08) y guarda la URL resultante. | 3 |
| 41 | **US31** | EP02 – Gestión de Reservas | Registrar y ver el motivo de un bloqueo por mantenimiento | Como administrador, quiero registrar un motivo o nota al bloquear una franja por mantenimiento, para que cualquier administrador entienda por qué está bloqueada sin tener que preguntar. | 3 |
| 42 | **US32** | EP02 – Gestión de Reservas | Registrar reservas de varias fechas (multi-día o recurrentes) | Como administrador, quiero registrar en una sola operación un alquiler que se repite en varias fechas, para no tener que registrar cada fecha por separado cuando un cliente reserva una serie. | 5 |
| 43 | **US34** | EP07 – Registro y Autorización de Administradores | Verificar mi correo antes de acceder al sistema | Como solicitante de una cuenta ya autorizada, quiero confirmar la propiedad de mi correo mediante un enlace de verificación, para evitar quedar con una cuenta activa pero inaccesible si escribí mal mi correo. | 3 |
| 44 | **TS11** | EP07 – Registro y Autorización de Administradores | Endpoint de verificación de correo con token de confirmación | Como Developer, quiero implementar el endpoint que valida el token de verificación enviado por correo y activa la cuenta del `User` solo si el token es válido y no ha expirado. | 2 |
| 45 | **US35** | EP02 – Gestión de Reservas | Bloquear varias fechas por mantenimiento en una sola operación | Como administrador, quiero bloquear una misma franja horaria en varias fechas a la vez, para no repetir el bloqueo manualmente fecha por fecha. | 3 |
| 46 | **TS12** | EP02 – Gestión de Reservas | Endpoint de registro de reservas en serie | Como Developer, quiero implementar el endpoint que registra múltiples `Booking` vinculados por un identificador de serie dentro de una sola transacción, revirtiendo la serie completa si cualquier fecha tiene conflicto. | 5 |
| 47 | **TS13** | EP02 – Gestión de Reservas | Endpoint de bloqueo de mantenimiento en varias fechas | Como Developer, quiero implementar el endpoint que crea múltiples `ScheduleBlock` para una misma franja horaria, validando conflictos contra `Booking` activos antes de crear cualquiera de ellos. | 3 |
| 48 | **US37** | EP01 – Identidad y Acceso | Recuperar el acceso olvidando mi contraseña | Como administrador, quiero poder solicitar un enlace de restablecimiento de contraseña cuando la olvido, para recuperar el acceso a mi cuenta. | 3 |
| 49 | **TS14** | EP01 – Identidad y Acceso | Endpoints de recuperación de contraseña olvidada | Como Developer, quiero implementar los endpoints de solicitud y confirmación de restablecimiento de contraseña, usando un token de un solo uso con expiración. | 3 |
| 50 | **US38** | EP10 – Notificaciones Internas entre Administradores | Ver notificaciones internas de la operación del negocio | Como administrador, quiero ver un listado de notificaciones cuando otro administrador registra un alquiler o bloquea una franja, para estar al tanto sin preguntarle directamente. | 3 |
| 51 | **TS15** | EP10 – Notificaciones Internas entre Administradores | Endpoints de notificaciones internas entre administradores | Como Developer, quiero implementar los endpoints de listado y marcado de notificaciones internas, generadas automáticamente por acciones de otros administradores. | 2 |
| 52 | **US39** | EP07 – Registro y Autorización de Administradores | Promover a otro administrador a dueño | Como administrador dueño, quiero poder ceder o compartir el rol de dueño con otro administrador de confianza, para no depender de una sola persona. | 2 |
| 53 | **US40** | EP07 – Registro y Autorización de Administradores | Desactivar la cuenta de un administrador | Como administrador dueño, quiero poder desactivar la cuenta de un administrador que ya no debería tener acceso, para revocar su acceso de forma inmediata. | 2 |
| 54 | **TS16** | EP09 – Ajustes de Cuenta | Endpoints de promoción, desactivación y perfil propio de administradores | Como Developer, quiero implementar los endpoints de promoción a dueño, desactivación de administradores y actualización de perfil/foto propia, restringiendo las acciones sobre otras cuentas al rol dueño. | 3 |
| 55 | **US41** | EP09 – Ajustes de Cuenta | Actualizar mi perfil y foto de administrador | Como administrador autenticado, quiero poder actualizar mis datos de perfil y mi foto, para que mi cuenta refleje información actualizada. | 3 |
| 56 | **US42** | EP09 – Ajustes de Cuenta | Dar de baja mi propia cuenta de administrador | Como administrador autenticado, quiero poder desactivar mi propia cuenta, para dejar de tener acceso al sistema cuando ya no trabajo en el negocio. | 1 |
| 57 | **US43** | EP04 – Gestión de Canchas | Eliminar una cancha que ya no está en uso | Como administrador, quiero poder eliminar una cancha que el colegio ya no ofrece, para que el catálogo refleje solo la infraestructura real disponible. | 2 |
| 58 | **TS17** | EP04 – Gestión de Canchas | Endpoint de eliminación de cancha con borrado en cascada | Como Developer, quiero implementar el endpoint que elimina una `Court`, documentando que el borrado es permanente y arrastra en cascada su historial de `Booking` y `Payment`. | 2 |
| 59 | **US44** | EP02 – Gestión de Reservas | Ver los bloqueos de mantenimiento de una cancha | Como administrador, quiero ver los bloqueos de mantenimiento vigentes y próximos de una cancha, para saber qué franjas ya están reservadas para mantenimiento. | 2 |
| 60 | **TS19** | EP02 – Gestión de Reservas | Endpoints de listado de bloqueos de mantenimiento | Como Developer, quiero implementar los endpoints que listan los `ScheduleBlock` de una cancha por fecha y los próximos a partir de hoy. | 2 |
| 61 | **TS18** | EP02 – Gestión de Reservas | Endpoint de desbloqueo de una franja de mantenimiento | Como Developer, quiero implementar el endpoint que elimina un `ScheduleBlock`, liberando la franja de inmediato y emitiendo `ScheduleUnblocked`. | 1 |
| 62 | **US45** | EP01 – Identidad y Acceso | Configurar la cuenta inicial del administrador dueño | Como Carlos, quiero poder crear la primera cuenta de administrador dueño al desplegar el sistema, sin depender de un proceso manual sobre la base de datos. | 2 |
| 63 | **TS20** | EP01 – Identidad y Acceso | Endpoint de configuración inicial de la cuenta dueño | Como Developer, quiero implementar el endpoint de bootstrap protegido por `SETUP_TOKEN`, bloqueado permanentemente después del primer uso. | 2 |
| 64 | **US46** | EP05 – Gestión de Pagos | Ver los pagos registrados de un alquiler | Como administrador, quiero ver todos los pagos registrados de un alquiler, para verificar cuánto y cómo se pagó. | 1 |
| 65 | **TS21** | EP05 – Gestión de Pagos | Endpoint de listado de pagos de un alquiler | Como Developer, quiero implementar el endpoint que retorna todos los `Payment` de un `Booking`, incluyendo los reversados. | 1 |
| 66 | **US47** | EP05 – Gestión de Pagos | Ver el comprobante ya adjuntado de un pago | Como administrador, quiero poder volver a ver el comprobante adjuntado a un pago, sin pedírselo de nuevo al cliente. | 2 |
| 67 | **TS22** | EP05 – Gestión de Pagos | Endpoint de visualización de comprobante con URL firmada | Como Developer, quiero implementar el endpoint que genera una URL firmada temporal (300s) hacia el comprobante en Supabase Storage. | 2 |

<br>

<div align="center">

**Herramienta de gestión utilizada:** `Jira`

</div>
<br>

---

# Capítulo III: Diseño de Producto (UX/UI)

## 3.1. Arquitectura de Información

Estructura de navegación derivada directamente de los Epics y priorizada según lo que Carlos usa con más frecuencia en el día a día (panel y calendario primero, configuración al final).

**Mapa de navegación:**

**Bienvenida (pública, sin sesión)**
 - Iniciar sesión
 - Registrar solicitud de administrador
 - Formulario: nombre, correo, complejo/negocio
 - Pantalla de espera: "Tu solicitud fue enviada, Carlos debe autorizarla"

**Panel Operativo del Día** *(pantalla de inicio tras autenticarse)*
 - Calendario de Reservas
 - Nuevo alquiler
 - Detalle / editar alquiler
 - Bloquear franja (mantenimiento)
 - Clientes
 - Ficha de cliente (historial)
 - Canchas
 - Editar cancha (precio, disciplina)
 - Pagos
 - Registrar pago (asociado a un alquiler existente)
 - Solicitudes de acceso *(visible solo para el administrador dueño)*
 - Autorizar / rechazar solicitud pendiente
 - Cerrar sesión

<br>

**Criterios de organización:**

- **Panel como home:** siguiendo US17–US19, lo primero que ve un administrador al iniciar sesión es el resumen del día, no un menú vacío, reduce clics para la tarea más frecuente.

- **Registro separado del login:** a diferencia del login, el registro de una nueva cuenta de administrador es un flujo público (sin sesión previa) pero no da acceso inmediato — queda en estado pendiente hasta que el administrador dueño la autorice desde "Solicitudes de acceso", evitando que cualquiera con el link se autoasigne acceso al negocio.

- **"Solicitudes de acceso" es visible solo para el dueño:** es la única sección de la navegación con visibilidad condicionada al tipo de cuenta — el resto de pantallas se ve igual para ambos administradores.

- **Pagos no es una sección aislada:** un pago siempre se registra desde el contexto de un alquiler específico (coherente con el subdominio Payments dependiendo de Bookings), evitando que el administrador tenga que buscar manualmente a qué alquiler corresponde un pago.

- **Clientes y Canchas son configuración de apoyo:** se accede a ellas con menor frecuencia que al calendario, por lo que quedan un nivel más profundo en la navegación en vez de competir por espacio con el calendario en la barra principal.

- **Sin nivel de "cliente final":** no existe ninguna rama de navegación para clientes externos, reforzando el alcance de la Propuesta 1, el correo de confirmación es un efecto secundario del registro de un alquiler, no una pantalla propia del cliente.

<br>

## 3.2. Style Guideline

### 3.2.1. General Style Guidelines

Lineamientos de identidad visual, independientes de la plataforma técnica.

- **Personalidad de marca:** funcional y de confianza, no "startup". "La Canchita de Carlos" es una herramienta de trabajo diario para un administrador, no un producto de consumo masivo — la identidad debe transmitir orden y claridad antes que estética llamativa. El copy de la interfaz (incluyendo las pantallas públicas de login y solicitud de acceso) debe describir lo que el sistema hace, sin lenguaje de venta tipo landing page ("la plataforma definitiva", "excelencia deportiva", "optimiza tus finanzas con un solo click"): no hay nadie a quien convencer, solo Carlos y su trabajador usando una herramienta de trabajo. Subtítulos como "Gestión interna de alquileres" o "Registra tus datos para acceder como administrador" son el tono correcto.

- **Paleta de marca (definida por Carlos):** azul, celeste y blanco — usados en header, navegación, botones principales e identidad visual general de la app.

- **Paleta funcional (independiente de la marca):** verde (acción positiva — disponible, pagado), ámbar (alerta suave — pendiente, bloqueado), rojo (conflicto — ocupado, doble reserva rechazada). Se mantienen estos 3 colores semánticos aunque la marca sea azul, porque el código verde/ámbar/rojo es el que permite leer el estado de una cancha de un vistazo (RF06, RNF03); reemplazarlos por tonos de azul obligaría a leer texto en vez de color, más lento para el uso real del negocio.

- **Tono de contenido:** directo y en español neutro/peruano informal ("Cancha ocupada" en vez de "Lo sentimos, esta cancha no está disponible en este momento"), porque el usuario opera bajo presión (cliente esperando respuesta al teléfono).

- **Logo/marca:** definido — wordmark + isotipo, ver detalle completo abajo.

<br>

## Logo — concepto y estilo

La identidad transmite cercanía, deporte, confianza y dinamismo. No representa un deporte específico, sino un espacio donde cualquier disciplina puede practicarse (coherente con el catálogo de canchas administrable de RF11: vóley, fútbol, básquet u otras).

<img src="assets/styles/logo.png" alt="Logo La Canchita de Carlos" width="300"/>

<br>

**Tipo:** Wordmark + isotipo.
- **Personalidad:** amigable, moderna, deportiva y accesible.
- **Estilo visual:** minimalista con detalles ilustrados; inspirado en canchas deportivas, movimiento y comunidad.

**Tipografía del logo**
- "La Canchita": **Lobster Two Bold** (tipografía Brush Script caligráfica).
- "de Carlos": **Kaushan Script** o **Pacifico**.
- Alternativas de la misma familia visual si se necesita variar: Bukhari Script, Brusher, Milkshake (de pago).

<br>

## Isotipo

Representa una cancha deportiva de forma abstracta: líneas redondeadas, sin balón, sin porterías, sin deporte específico — formas simples, grosor uniforme, escalable desde 32 px.

**Estilo gráfico:** bordes redondeados, trazos suaves, apariencia limpia, sin sombras ni degradados fuertes, colores planos.

**Área de seguridad y tamaño mínimo:** espacio libre alrededor del logo equivalente a la altura de la letra "L"; tamaño mínimo 120 px de ancho en digital, 30 mm en impresión.

**Versiones del logo:** principal (azul + celeste), monocromático azul, blanco para fondos oscuros, isotipo solo (la cancha) — esta última es la que se usa como ícono de la PWA (favicon/app icon).

<br>

### 3.2.2. Web Style Guidelines

Tokens de diseño concretos, implementables directamente en Tailwind CSS.

<br>

## Colors

| Token | Uso | Valor referencial |
|---|---|---|
| `brand-primary` (azul) | Header, navegación, botones principales, identidad de marca | `#2563EB` |
| `brand-secondary` (celeste) | Fondos de sección, estados hover/activos, elementos secundarios de marca | `#7DD3FC` |
| `brand-base` (blanco) | Fondo general de la app, tarjetas | `#FFFFFF` |
| `success` (verde) | Estado funcional "disponible"/"pagado" — independiente de la marca | `#16A34A` |
| `warning` (ámbar) | Estado funcional "pendiente"/"bloqueado" | `#D97706` |
| `danger` (rojo) | Estado funcional "ocupado"/conflicto, acciones destructivas (cancelar) | `#DC2626` |
| `neutral-900` a `neutral-50` | Texto y fondos, escala de grises de Tailwind | `slate` (Tailwind default) |

<br>

<img src="assets/styles/primary-colors.png" alt="Primary Colors" width="250"/>
<img src="assets/styles/functional-colors.png" alt="Functional Colors" width="250"/>
<img src="assets/styles/neutral-colors.png" alt="Neutral Colors" width="250"/>

<br>

## Tipography

Sistema de dos niveles, para que la interfaz se sienta alineada a la marca sin sacrificar legibilidad en una app con mucho texto denso (tablas, badges, montos):

- **`font-display` (Lobster Two, peso Bold — la misma tipografía del logo):** reservada a textos grandes de marca, ≥24px: título de bienvenida en el login ("La Canchita de Carlos"), saludo del panel ("Hoy, sábado 11 de julio"). A ese tamaño el trazo caligráfico se lee bien y refuerza la identidad de marca en cada apertura de la app.

- **`font-sans` (Outfit, pesos 400/500/600/700):** para todo lo demás — formularios, tablas, badges de estado, montos, metadatos, nombres de sección y cualquier texto bajo 24px. Geométrica y redondeada, combina bien con el isotipo del logo (también de líneas redondeadas) y se ve más cuidada que una fuente de sistema genérica, sin perder legibilidad en tamaños chicos. Un script cursivo en un badge de 12px o un monto en soles sí se volvería difícil de leer rápido, y en esta app la lectura rápida del estado de una cancha no es negociable.

- Lobster Two y Outfit están disponibles en Google Fonts (gratuitas). Lobster Two se carga en un solo peso (Bold) y Outfit en 4 pesos — ambas de uso puntual/acotado, así que el impacto en RNF05 sigue siendo mínimo.

- Escala reducida a 4 tamaños: `text-xl` (títulos de sección, en `font-display`), `text-base` (contenido, `font-sans`), `text-sm` (metadatos: fecha, estado), `text-xs` (etiquetas). Suficiente para una app de gestión, sin necesidad de una escala tipográfica extensa.

<br>

<img src="assets/styles/bodytype.png" alt="Styles La Canchita de Carlos" width="400"/>

<br>

## Componentes base (Tailwind + shadcn/ui si se requiere velocidad)

- Botones: `primary` (azul, acción principal — marca), `outline` (celeste/borde, secundaria), `destructive` (rojo, cancelar/eliminar) — 3 variantes son suficientes para el catálogo de acciones del sistema.
- Tarjeta de franja horaria: estado visual mediante color de fondo (libre/ocupada/bloqueada), sin depender solo de texto — accesible también para lectura rápida en pantallas pequeñas.
- Inputs: altura mínima de 44px (estándar táctil), dado que el uso principal es desde celular.
- Layout: mobile-first con breakpoint único a `md:` (768px) para la vista de escritorio — no se justifican breakpoints intermedios para 2 usuarios y un catálogo de pantallas pequeño.

<br>

<img src="assets/styles/typography.png" alt="Styles La Canchita de Carlos" width="600"/>

<br>

## 3.3. Wireframes y Mockups

### Wireframes

>*Los wireframes representan la estructura base del diseño de la aplicación, permitiendo definir la organización de contenidos, la jerarquía visual y el flujo de navegación antes del diseño visual final. Se desarrollaron versiones para escritorio (desktop web browser) y dispositivos móviles (mobile web browser):*

<br>
<div align="center">

**Desktop Web Browser**

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/login.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/register.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/home.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/calendario.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/registrar-alquiler.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/clientes.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/reservas.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/canchas.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/registrar-cancha.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/ajustes.png)

<br>

![Wireframe Web Desktop](assets/wireframes/desktop/solicitudes.png)

<br>

**Mobile Web Browser**

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/login.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/register.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/home.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/calendario.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/registrar-alquiler.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/clientes.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/reservas.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/canchas.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/registrar-cancha.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/ajustes.png)

<br>

![Wireframe Mobile Web](assets/wireframes/mobile/solicitudes.png)

<br>
</div>

### Mockups

> *Los mock-ups representan la versión visual final de la aplicación, incorporando los elementos definidos en el Design System, como la paleta de colores, la tipografía, la iconografía y los estilos de componentes.*

<br>
<div align="center">

**Desktop Web Browser**

![Mockup Desktop](assets/mockups/desktop/login.png)

<br>

![Mockup Desktop](assets/mockups/desktop/register.png)

<br>

![Mockup Desktop](assets/mockups/desktop/home.png)

<br>

![Mockup Desktop](assets/mockups/desktop/calendario.png)

<br>

![Mockup Desktop](assets/mockups/desktop/nuevo-alquiler.png)

<br>

![Mockup Desktop](assets/mockups/desktop/reservas.png)

<br>

![Mockup Desktop](assets/mockups/desktop/clientes.png)

<br>

![Mockup Desktop](assets/mockups/desktop/canchas.png)

<br>

![Mockup Desktop](assets/mockups/desktop/nueva-cancha.png)

<br>

![Mockup Desktop](assets/mockups/desktop/ajustes.png)

<br>

![Mockup Desktop](assets/mockups/desktop/solicitudes.png)

<br>

**Mobile Web Browser**

![Mockup Mobile](assets/mockups/mobile/login.png)

<br>

![Mockup Mobile](assets/mockups/mobile/register.png)

<br>

![Mockup Mobile](assets/mockups/mobile/home.png)

<br>

![Mockup Mobile](assets/mockups/mobile/calendario.png)

<br>

![Mockup Mobile](assets/mockups/mobile/registrar-alquiler.png)

<br>

![Mockup Mobile](assets/mockups/mobile/reservas.png)

<br>

![Mockup Mobile](assets/mockups/mobile/clientes.png)

<br>

![Mockup Mobile](assets/mockups/mobile/canchas.png)

![Mockup Mobile](assets/mockups/mobile/registrar-cancha.png)

<br>

![Mockup Mobile](assets/mockups/mobile/ajustes.png)

<br>

![Mockup Mobile](assets/mockups/mobile/solicitudes.png)

</div>

<br>

### 3.3.1. Web Applications User Flow Diagrams

<br>

![UserFlow](assets/user-flow/flows.png)

<br>

## 3.4. Prototipo en Figma

En esta sección se presenta el prototipo interactivo de la aplicación web de *La Canchita de Carlos*, desarrollado en Figma a partir de los mockups de alta fidelidad definidos previamente. El prototipo permite simular la navegación e interacción entre los distintos módulos y bounded contexts de la plataforma, tanto en versiones Desktop como Mobile Web.

<br>

<div align="center">

**Desktop Prototyping**

![Desktop Video Prototype](assets/prototyping/web-desktop.png)

[Ver video de prototipo Desktop](https://youtu.be/GsqSs8i3ie0?si=EHo-VCSI3bgVMJ9i)

<br>

**Mobile Prototyping**

![Mobile Video Prototype](assets/prototyping/web-mobile.png)

[Ver video de prototipo Mobile](https://youtu.be/-rHLBf5RT-o?si=CWCItbbgryfW5kmE)

</div>

<br>

*Link al prototipo navegable:* https://www.figma.com/site/iprLtSv1JAy2xLH9kklVbt/La-Canchita-de-Carlos?node-id=0-1&t=Z97IFu36y9xYDgxy-1

<br>

---

# Capítulo IV: Arquitectura de Software (Domain-Driven Design)

## 4.0. Patrón de Arquitectura

El sistema combina dos niveles de arquitectura, uno de despliegue y otro de organización interna del código:

## Arquitectura de tres capas:

- **Presentación:** PWA en React (lo que el administrador ve y usa).

- **Aplicación:** API en Node.js/Express (lógica de negocio y reglas del dominio).

- **Datos:** PostgreSQL (persistencia).

<br>

Se eligió tres capas y no una arquitectura monolítica simple ni microservicios: el negocio es pequeño (2 administradores, 5 canchas, sin tráfico masivo), por lo que microservicios agregaría complejidad de despliegue injustificada para el plazo de 2 semanas; y separar en tres capas ya da independencia suficiente entre frontend, backend y base de datos para desplegar y escalar cada una por separado si el negocio crece.

<br>

## Arquitectura Hexagonal dentro de la capa de Aplicación:

El backend no se organiza como un framework Express típico con todo en controladores, sino en 3 anillos, repetidos dentro de cada uno de los 6 bounded contexts (`bookings`, `customers`, `identity`, `notifications`, `panel`, `payments`):

- **Dominio (núcleo):** entidades y reglas de negocio puras de cada bounded context (`Booking`, `Court`, `ScheduleBlock`, `Customer`, `Payment`, `User`, `AccessRequest`, `Notification`), sin dependencias de Express, Prisma ni ninguna librería externa.

- **Aplicación (casos de uso):** orquesta el dominio para cumplir una acción concreta (ej. `registerBooking`, `cancelBooking`, `registerPayment`), define **puertos** (interfaces) que necesita, como `BookingRepository`.

- **Infraestructura (adaptadores):** implementaciones concretas de esos puertos — el adaptador de entrada es Express (controladores/rutas que reciben HTTP y llaman a los casos de uso), el adaptador de salida es Prisma/PostgreSQL (implementa `BookingRepository` contra la base de datos real).

Además de estos 6 contextos de negocio, existe una capa transversal `platform/` (autenticación JWT, hash de contraseñas, manejo centralizado de errores, validación de entrada, adaptador de Supabase Storage, endpoint `/health`) — no es un bounded context con su propio lenguaje de negocio, sino infraestructura técnica compartida que cualquier contexto puede usar.

<br>

**Por qué combinarlas:**

La arquitectura de tres capas resuelve *dónde* corre cada cosa (despliegue); la hexagonal resuelve *cómo* se organiza el código *dentro* de la capa de Aplicación, alineado a los bounded contexts definidos en DDD. La ventaja concreta para este proyecto: la lógica de negocio (ej. "no permitir doble reserva") queda aislada y testeable sin levantar servidor ni base de datos, y si en la Propuesta 2 cambian de Prisma a otro ORM o agregan una pasarela de pagos, solo se reemplaza el adaptador correspondiente sin tocar las reglas de negocio.

<br>

## 4.1. Design-Level Event Storming

Para definir la arquitectura de "La Canchita de Carlos" orientada al dominio (DDD), se realizó un proceso iterativo de Design-Level Event Storming siguiendo la metodología de 10 pasos, tomando como base los flujos operativos reales del negocio (alquiler de canchas, registro de pagos, gestión de clientes y autorización de administradores). A continuación, se detalla la evolución del modelo:

<br>

**Step 1: Unstructured Exploration**

Se identificaron y representaron todos los eventos que modifican el estado del sistema, escritos en tiempo pasado (post-its naranjas): desde `BookingRegistered` y `PaymentRegistered` hasta `RegistrationRequestCreated` y `ConfirmationEmailSent`, entre otros eventos relevantes del dominio.

<br>

![Step 1 - Unstructured Exploration](assets/event-storming/step1.png)

<br>

**Step 2: Timelines**

Se ordenaron los eventos de forma cronológica de izquierda a derecha, estableciendo el flujo de vida del negocio: primero el onboarding de administradores (`RegistrationRequestCreated` → `AdminAuthorized`/`AdminRejected` → `EmailVerified`), luego la configuración inicial de canchas (`CourtRegistered` → `CourtPriceUpdated`), y finalmente el ciclo operativo diario (`BookingRegistered`/`BookingEdited`/`BookingCancelled` → `PaymentRegistered`/`PartialPaymentRegistered` → `ConfirmationEmailSent`).

<br>

![Step 2 - Timelines](assets/event-storming/step2.png)

<br>

**Step 3: Hotspots**

Se identificaron los puntos críticos del sistema y riesgos técnicos del negocio (marcados con rombos rojos):
- Condición de carrera al registrar dos alquileres simultáneos sobre la misma franja horaria (mitigado con constraints a nivel de base de datos, no solo validación en el backend).
- Un fallo en el envío del correo de confirmación (Resend) no debe revertir ni bloquear el `BookingRegistered` ya persistido (RF24).
- El "cold start" del backend en el plan gratuito de Render (elegido para mantener el costo recurrente en US$0) retrasa la primera acción del día tras un período de inactividad — se decidió no eliminarlo con un plan de pago por costo, y en su lugar se implementó el endpoint `/health` para monitorear el estado del servicio en vez de eliminar la latencia.
- Crecimiento del almacenamiento de imágenes (comprobantes de pago, fotos de canchas) en el mediano plazo si el negocio crece a más administradores o mayor volumen diario.

<br>

![Step 3 - Hotspots](assets/event-storming/step3.png)

<br>

**Step 4: Pivotal Events**

Se definieron eventos pivote que segmentan el flujo en fases funcionales: `AdminAuthorized` marca el paso de "solicitud" a "cuenta creada pero pendiente de verificar"; `EmailVerified` marca el paso de "cuenta creada" a "administrador operativo"; `CourtRegistered` marca el paso de "negocio sin configurar" a "negocio operativo"; `BookingRegistered` marca el paso de "franja disponible" a "franja ocupada"; y `PaymentRegistered`/`PartialPaymentRegistered` marca el cierre financiero de un alquiler.

<br>

![Step 4 - Pivotal Events](assets/event-storming/step4.png)

<br>

**Step 5: Commands & Actors**

Se definieron los commands (post-its azules) que disparan los eventos, y los actores (íconos amarillos) responsables de ejecutarlos: el **Administrador** (rol operativo estándar), el **Administrador dueño** (único con permiso para autorizar/rechazar nuevas solicitudes de acceso, RF21), el **Solicitante** (sin sesión, antes de ser autorizado) y el propio **sistema** (para eventos de integración como `ConfirmationEmailSent`).

<br>

![Step 5 - Commands & Actors](assets/event-storming/step5.png)

<br>

**Step 6: Policies**

Se incorporaron las business policies (post-its lilas), reglas reactivas que automatizan el comportamiento del sistema:

- Cuando se intenta `RegisterBooking` sobre una franja ya ocupada o bloqueada → se emite `DoubleBookingRejected` en vez de `BookingRegistered`.
- Cuando ocurre `BookingRegistered` y el `Customer` asociado tiene correo registrado → se dispara `ConfirmationEmailSent`, sin revertir el alquiler si el envío falla.
- Cuando ocurre `AdminAuthorized` → se crea el `User` (en estado `PENDING_VERIFICATION`) y se disparan dos correos: el de resultado de la solicitud y el de verificación de correo.
- Cuando ocurre `AdminRejected` → se notifica por correo al solicitante, sin crear ningún `User`.
- Cuando ocurre `BookingCancelled` y el alquiler tenía pagos registrados → se reversan automáticamente todos sus pagos activos (`PaymentReversed`, soft-reversal: el registro no se borra, solo se marca con `reversedAt` para conservar el rastro de auditoría) y se reinicia el saldo pagado del alquiler a 0 antes de marcarlo como cancelado.

<br>

![Step 6 - Policies](assets/event-storming/step6.png)

<br>

**Step 7: Read Models**

Se mapearon los read models (post-its verdes), las vistas que el administrador necesita consultar antes de ejecutar un comando: el **Calendario de disponibilidad** (antes de `RegisterBooking`), el **Panel principal** con los alquileres, ingresos y pagos pendientes del día (subdominio `panel`, EP06), el **Historial de cliente** (antes de reutilizar un cliente existente en un nuevo alquiler), y el **Panel de solicitudes de acceso** (solo para el administrador dueño, antes de `AuthorizeAdmin`/`RejectAdmin`).

<br>

![Step 7 - Read Models](assets/event-storming/step7.png)

<br>

**Step 8: External Systems**

Se identificaron los sistemas externos (post-its rosados) que interactúan con el sistema: **Resend** (envío de correos de confirmación y de identidad), **Supabase Storage** (almacenamiento de imágenes de comprobantes y fotos de canchas, fuera de la base de datos relacional) y **WhatsApp** (acceso directo vía enlace `wa.me` al contacto del cliente, no es una integración de API, solo un enlace externo).

<br>

![Step 8 - External Systems](assets/event-storming/step8.png)

<br>

**Step 9: Aggregates**

Se incrementó el nivel de abstracción agrupando comandos y eventos alrededor de las entidades principales del dominio (Aggregates, post-its amarillos grandes): `Booking`, `Court`, `ScheduleBlock`, `Customer`, `Payment`, `User`, `AccessRequest` y `Notification`, cada uno encapsulando la consistencia de sus propias reglas de negocio e invariantes.

<br>

![Step 9 - Aggregates](assets/event-storming/step9.png)

<br>

**Step 10: Bounded Contexts**

Finalmente, se delimitaron los límites semánticos y transaccionales del dominio agrupando los aggregates en bloques coherentes e independientes, consolidando la arquitectura en seis subdominios: **Bookings** (núcleo, incluye `Court` y `ScheduleBlock`), **Payments** y **Customers** (soporte), **Identity & Access** (incluye `User` y `AccessRequest`), **Panel** (lectura consolidada del día operativo) y **Notifications**.

<br>

![Step 10 - Bounded Contexts](assets/event-storming/step10.png)

<br>
El proceso de Design-Level Event Storming permitió profundizar en el comportamiento técnico del sistema a partir de los flujos operativos reales del negocio de Carlos. En esta etapa se definieron los límites transaccionales (Bounded Contexts) y se incorporaron elementos de diseño táctico como Comandos, Aggregates y Policies, cuyo detalle tabular se documenta a continuación.

<br>

[Ver tablero interactivo en Miro](https://miro.com/app/board/uXjVH4Z9siM=/?share_link_id=815397269909)

<br>

### 4.1.1. Tabla de Comands, Aggregates y Events

Eventos de dominio identificados por subdominio, con el comando/actor que los dispara. Estos eventos son la base para los aggregates raíz y para los criterios de aceptación Gherkin de las User Stories.

<br>

| Comands (actor: Administrador) | Aggregate | Domain event | Invariante protegida |
|---|---|---|---|
| RegisterBooking | `Booking` | `BookingRegistered` | No puede existir otro `Booking` activo para la misma `Court` + franja horaria. |
| — (rechazo del comando anterior) | `Booking` | `DoubleBookingRejected` | Se emite en vez de `BookingRegistered` cuando la franja ya está ocupada o bloqueada. |
| EditBooking | `Booking` | `BookingEdited` | El nuevo horario/cancha tampoco puede colisionar con otro alquiler activo. |
| CancelBooking | `Booking` | `BookingCancelled` | Libera la franja horaria inmediatamente para nuevas reservas; si el alquiler tenía pagos registrados, se reversan automáticamente antes de marcarlo como `CANCELLED` (ver `PaymentReversed`). |
| BlockSchedule | `ScheduleBlock` | `ScheduleBlocked` | No puede bloquearse una franja con un `Booking` activo. |
| UnblockSchedule | `ScheduleBlock` | `ScheduleUnblocked` | — |
| RegisterCourt | `Court` | `CourtRegistered` | Nombre de cancha único dentro del negocio. |
| UpdateCourtPrice | `Court` | `CourtPriceUpdated` | El precio no puede ser negativo ni cero. |
| RegisterCustomer | `Customer` | `CustomerRegistered` | — |
| UpdateCustomer | `Customer` | `CustomerUpdated` | — |
| RegisterPayment | `Payment` | `PaymentRegistered` | El monto pagado no puede exceder el total del alquiler asociado. |
| RegisterPartialPayment | `Payment` | `PartialPaymentRegistered` | El saldo pendiente se recalcula y nunca puede ser negativo. |
| — (efecto de `BookingCancelled`) | `Payment` | `PaymentReversed` | Se marca cada pago activo del alquiler cancelado con `reversedAt` (soft-reversal, no se borra el registro) y se reinicia `paidAmount` a 0 y `paymentStatus` a `PENDING` en el `Booking` asociado. |
| StartSession | `User` | `SessionStarted` | Credenciales inválidas no generan sesión. |
| CloseSession | `User` | `SessionClosed` | — |
| RequestAdminRegistration (actor: solicitante, sin sesión) | `AccessRequest` | `RegistrationRequestCreated` | El `AccessRequest` se crea en estado `PENDING`; no existe ningún `User` todavía, por lo que el solicitante no tiene acceso al sistema. |
| AuthorizeAdmin (actor: administrador dueño) | `AccessRequest` | `AdminAuthorized` | Solo un `User` con rol dueño puede ejecutar este comando (RF21). El `AccessRequest` pasa a `APPROVED` y, como efecto, se crea un `User` en estado `PENDING_VERIFICATION` (aún sin poder iniciar sesión). |
| RejectAdmin (actor: administrador dueño) | `AccessRequest` | `AdminRejected` | El `AccessRequest` pasa a `REJECTED`; no se crea ningún `User`, y una nueva solicitud del mismo correo requiere un nuevo `AccessRequest`. |
| VerifyEmail (actor: solicitante ya autorizado) | `User` | `EmailVerified` | Solo con un token de verificación válido y no expirado; el `User` pasa de `PENDING_VERIFICATION` a `ACTIVE`, habilitando recién `StartSession`. |
| — (efecto de `BookingRegistered`) | `Payment`/`Customer` (evento de integración) | `ConfirmationEmailSent` | Solo se dispara si el `Customer` asociado tiene correo registrado (RF23); un fallo de envío no revierte el `Booking` (RF24). |

<br>

## 4.2. Bounded Contexts y Context Map

<br>

| Subdominio | Tipo | Alcance / entidades | Justificación |
|---|---|---|---|
| **Bookings** | Núcleo | `Court`, `Booking`, `ScheduleBlock`, disponibilidad, precios | Es donde vive la regla de negocio crítica (no permitir doble reserva) y la razón de ser del sistema. Aquí no cabe una solución genérica: la lógica de disponibilidad es propia de "La Canchita de Carlos". |
| **Payments** | Soporte | `Payment`, estado (pagado/pendiente/parcial), método de pago, asociado a un `Booking` | Necesario para el negocio y con reglas propias (pagos parciales), pero no es el diferenciador del sistema; podría evolucionar de forma relativamente independiente (ej. integrarse con una pasarela en la Propuesta 2) sin afectar la lógica de Bookings. |
| **Customers** | Soporte | `Customer`, historial básico de alquileres | Registro de datos de contacto e historial; simple hoy, pero se mantiene separado porque en la Propuesta 2 evoluciona a un contexto con más peso (cuentas de cliente, reservas propias). |
| **Identity & Access (IAM)** | Genérico | `User` administrador, `AccessRequest`, autenticación, sesión | No aporta valor diferencial al negocio — es un problema resuelto miles de veces (login/JWT). Se trata como subdominio genérico, candidato a simplificarse al máximo o reemplazarse por una solución de terceros si el proyecto creciera. |
| **Panel** | Genérico | Sin aggregate propio — agrega y expone en solo lectura datos de `Booking` y `Payment` del día (EP06: alquileres del día, ingreso total, pagos pendientes) | No introduce reglas de negocio nuevas, solo consolida datos que ya existen en Bookings y Payments para dar visibilidad operativa inmediata; se mantiene como contexto propio porque su read model cruza dos contextos distintos y no pertenece naturalmente a ninguno de los dos. |
| **Notifications** *(alcance mínimo en Propuesta 1)* | Genérico | Correo de confirmación puntual al registrar un `Booking` (RF23–RF24) y correos del ciclo de identidad: resultado de autorización (RF22) y verificación de correo (US34). **No incluye** recordatorios recurrentes, WhatsApp, ni notificaciones dentro de la app — eso permanece en la Propuesta 2. | Se implementa como reacción a `BookingRegistered`, `AdminAuthorized` y `AdminRejected`, sin lógica de negocio propia — solo dispara un envío de correo transaccional. Al ser un subdominio genérico desacoplado (reacciona a eventos, no los modifica), ampliar su alcance en la Propuesta 2 (recordatorios, WhatsApp) no requiere tocar Bookings ni Payments. |

*Nota:* además de estos seis bounded contexts de negocio, el código tiene una capa `platform/` (JWT, hash de contraseñas, manejo de errores, validación, adaptador de Supabase Storage, endpoint `/health`) que es infraestructura técnica compartida, no un subdominio con lenguaje de negocio propio — por eso no aparece como una fila más en esta tabla, a diferencia de una versión anterior de este documento que la listaba como "Infrastructure & Observability".

<br>

**Relaciones entre contextos (Context Map):**

- **Bookings → Customers** (relación *Customer/Supplier*): un alquiler referencia a un cliente existente; Bookings consume datos de Customers pero no los modifica.
- **Bookings → Payments** (relación *Customer/Supplier*, con una escritura puntual en sentido inverso): un pago siempre pertenece a un alquiler, por lo que Payments depende del identificador de Booking generado por Bookings; adicionalmente, al ejecutar `CancelBooking`, Bookings invoca a Payments (`reverseAllForBooking`) para reversar los pagos activos del alquiler antes de marcarlo como cancelado — es la única operación en la que Bookings escribe sobre el modelo de Payments.
- **Panel → Bookings** y **Panel → Payments** (relación *Customer/Supplier*, solo lectura): Panel consulta datos de ambos contextos para construir sus tres read models del día (alquileres, ingreso, pendientes de pago), sin escribir de vuelta en ninguno de los dos.
- **Identity & Access → Bookings / Payments / Customers / Panel** (relación *Shared Kernel* mínimo): los cuatro contextos consumen la identidad del administrador autenticado para saber quién realizó cada acción, sin compartir más modelo que eso.
- **Bookings → Notifications** (relación *Published Language / eventos*): Notifications escucha `BookingRegistered` y reacciona enviando el correo de confirmación (RF23); no tiene forma de escribir de vuelta en Bookings.
- **Identity & Access → Notifications** (relación *Published Language / eventos*): Notifications escucha `AdminAuthorized`/`AdminRejected` para avisar por correo al solicitante (RF22) y disparar el correo de verificación de correo (US34).


<br>

## 4.3. Software Architecture Context Diagram

<br>

![Context Diagram](assets/C4-level/context-diagram.png)

El diagrama de contexto ubica a "La Canchita de Carlos" como una única caja frente a los actores humanos y los sistemas externos con los que se integra, sin entrar todavía en cómo está construido internamente.

Cuatro actores interactúan con el sistema: el **Administrador** (rol operativo estándar, registra alquileres, pagos, clientes y canchas), el **Administrador Dueño** (único con permiso para autorizar o rechazar nuevas solicitudes de acceso, RF21), el **Solicitante** (una persona sin cuenta todavía que pide acceso como administrador) y el **Cliente del negocio** (quien alquila una cancha; no usa el sistema directamente, pero recibe el correo de confirmación y puede ser contactado por WhatsApp).

El sistema se integra con tres sistemas externos: **Resend**, que envía los correos transaccionales (confirmación de alquiler, resultado de una solicitud de acceso, verificación de correo y reseteo de contraseña); **Supabase Storage**, donde se suben y firman las fotos de canchas/perfil y los comprobantes de pago (RF25, RF31); y **WhatsApp**, no como una integración de API sino como un enlace directo (`wa.me`) que el sistema genera para que el administrador abra un chat con el cliente sin copiar el número a mano (RF30).

<br>

## 4.4. Software Architecture Container Diagram

<br>

![Container Diagram](assets/C4-level/container-diagram.png)

El diagrama de contenedores abre la caja del sistema y muestra las tres piezas desplegables de forma independiente, correspondientes a la arquitectura de tres capas definida:

- **Frontend PWA** (React + TypeScript + Vite + `vite-plugin-pwa`): las pantallas de calendario, canchas, clientes, pagos, panel y ajustes, instalable sin tienda de aplicaciones (RNF04). Es lo único con lo que interactúan directamente el Administrador, el Administrador Dueño y el Solicitante.
- **Backend API** (Node.js + Express + TypeScript, empaquetado en una imagen Docker): expone la API REST que consume el frontend y contiene los 6 bounded contexts de negocio en arquitectura hexagonal.
- **Base de Datos** (PostgreSQL 16, gestionado por Supabase sobre AWS): persiste usuarios, solicitudes de acceso, canchas, bloqueos, clientes, alquileres, pagos y notificaciones.

El Frontend PWA llama al Backend API por HTTPS/JSON; el Backend API lee y escribe en la Base de Datos vía Prisma, y es el único contenedor que se comunica con los sistemas externos (Resend y Supabase Storage) — el frontend nunca les habla directamente. Esta separación es la que permite desplegar y escalar cada contenedor por separado (frontend en un Static Site, backend en un Web Service, base de datos en un servicio gestionado aparte).

<br>

## 4.5. Software Architecture Components Diagrams

<br>

Los diagramas de componentes muestran a cada uno de los 6 bounded contexts definidos, sus componentes internos siguiendo los 3 anillos de la arquitectura hexagonal: controladores REST (adaptador de entrada), casos de uso (aplicación) y repositorios + dominio (adaptador de salida y núcleo). Se documenta un diagrama por bounded context, porque cada contexto es un límite transaccional independiente con su propio lenguaje, y mezclarlos en un único diagrama perdería esa separación. Los componentes de `platform/` (autenticación JWT, hash de contraseñas, validación, adaptador de Supabase Storage) no son un bounded context propio, son infraestructura técnica compartida y por eso aparecen repetidos, cuando corresponde, en más de un diagrama de contexto en vez de tener uno propio.

<br>

### 4.5.1. Components — Bookings

<br>

![Components Diagram](assets/C4-level/components-bookings.png)

<br>

Contiene los tres aggregates que concentran la regla de negocio más crítica del sistema: `Booking`, `Court` y `ScheduleBlock`. El **Bookings Controller** expone las rutas de alquileres (crear, editar, cancelar, buscar historial, disponibilidad consolidada) y el **Courts Controller** las de canchas (alta, edición, precio, fotos, bloqueos por mantenimiento); ambos protegidos por el `Auth Middleware` compartido. Los casos de uso (`registerBooking`, `editBooking`, `cancelBooking`, `blockSchedule(Series)`, `registerCourt`, `updateCourtPrice`, entre otros) operan sobre el `Booking Repository`, que implementa el constraint que impide la doble reserva (RF06) directamente contra PostgreSQL, y sobre el `Court Repository`/`ScheduleBlock Repository`. Este contexto es el único que depende de `Customer Repository` (para crear un cliente embebido al registrar un alquiler, TS09) y del `Supabase File Storage` compartido (para subir fotos de cancha), y dispara el `Resend Notification Sender` cuando se registra un alquiler nuevo.

<br>

### 4.5.2. Components — Customers

<br>

![Components Diagram](assets/C4-level/components-customers.png)

<br>

El contexto más simple del sistema: el **Customers Controller** expone alta, edición, historial y desactivación de clientes; los casos de uso (`registerCustomer`, `updateCustomer`, `deactivateCustomer`, `getCustomerHistory`, `listCustomers`) operan sobre el aggregate `Customer` a través de su repositorio. No tiene dependencias salientes hacia otros contextos es consumido por Bookings.

<br>

### 4.5.3. Components — Payments

<br>

![Components Diagram](assets/C4-level/components-payments.png)

<br>

El **Payments Controller** expone el registro de pagos (total o parcial), adjuntar comprobante y listar los pagos de un alquiler. Los casos de uso (`registerPayment`, `attachReceipt`, `getReceiptSignedUrl`, `listPaymentsForBooking`) aplican la invariante del aggregate `Payment` (el monto pagado nunca excede el total adeudado) y dependen de dos elementos fuera de su propio contexto: el `Booking Repository` de Bookings, para recalcular el saldo pendiente del alquiler asociado, y el `Supabase File Storage` compartido, para subir y firmar la URL del comprobante.

<br>

### 4.5.4. Components — Identity & Access

<br>

![Components Diagram](assets/C4-level/components-identity.png)

<br>

El contexto con más componentes del sistema, porque cubre dos aggregates (`User` y `AccessRequest`) y todo el ciclo de identidad: el **Auth Controller** expone login, logout y reseteo de contraseña; el **Users Controller** expone solicitudes de acceso, autorizar/rechazar, verificación de correo y ajustes de cuenta. Los casos de uso se apoyan en cinco repositorios distintos (`User`, `AccessRequest`, `Session`, `EmailVerificationToken`, `PasswordResetToken`) y en cuatro componentes compartidos de `platform/`: `JWT Service` (firma y verifica tokens), `Password Hasher` (bcrypt), `Token Generator` (tokens de un solo uso hasheados) y `Owner-Only Middleware` (restringe autorizar/rechazar solicitudes al administrador dueño, RF21). También sube la foto de perfil vía `Supabase File Storage` y dispara los tres correos del ciclo de identidad (resultado de solicitud, verificación de correo, reseteo de contraseña) a través del `Resend Notification Sender` de Notifications.

<br>

### 4.5.5. Components — Panel

<br>

![Components Diagram](assets/C4-level/components-panel.png)

<br>

El único contexto sin aggregate propio: el **Panel Controller** expone los tres read models del día operativo (alquileres del día, ingreso total, pagos pendientes, EP06). Sus casos de uso (`getBookingsToday`, `getIncomeToday`, `getPendingPaymentsToday`) no contienen reglas de negocio — solo consultan en solo lectura, a través del `Panel Repository`, las tablas de `Booking` y `Payment` que pertenecen a otros contextos.

<br>

### 4.5.6. Components — Notifications

<br>

![Components Diagram](assets/C4-level/components-notifications.png)

<br>

El **Notifications Controller** expone las notificaciones internas del sistema (listar mis notificaciones, marcar como leída) sobre el aggregate `Notification`, a través de sus casos de uso (`listMyNotifications`, `markNotificationRead`) y su repositorio. El componente distinto de este contexto es el **Resend Notification Sender**: un adaptador que implementa el puerto `NotificationSender` y es invocado desde Bookings (confirmación de alquiler) e Identity & Access (resultado de solicitud, verificación de correo, reseteo de contraseña) para enviar los correos vía Resend — es el único punto de salida hacia ese sistema externo, aunque el evento que lo dispara nazca en otro contexto.

<br>

## 4.6. Cloud Architecture (PWA)
 
**Stack definido para este proyecto:**
 
<br>

| Capa | Tecnología | Motivo |
|---|---|---|
| Frontend | React + Vite + TypeScript + `vite-plugin-pwa` + Tailwind CSS | Build rápido en desarrollo (HMR de Vite) y soporte PWA (manifest + service worker) de fábrica, sin configurar herramientas adicionales. TypeScript comparte tipos con el backend (vía Prisma) para detectar errores antes de producción. |
| Estado / datos | React Query (o similar) + React Router | Manejo simple de llamadas a la API y cacheo, sin over-engineering. |
| Backend | Node.js + Express + TypeScript | Framework minimalista sin convenciones forzadas, adecuado para una API con alcance acotado (Capítulo II); reduce la curva de aprendizaje frente a frameworks más opinados como NestJS y evita el vendor lock-in de una plataforma BaaS como Firebase. |
| ORM | Prisma | Migraciones automáticas y modelos tipados, acelera el diseño de BD del Capítulo VI. |
| Base de datos | PostgreSQL gestionado (Supabase, plan gratuito) | Relacional, soporta transacciones/constraints para evitar doble reserva (clave para RF06). |
| Autenticación | JWT + bcrypt implementado en Express | Solo 2 usuarios administradores; no se justifica un proveedor de auth externo todavía. |
| Hosting Frontend | Render (Static Site, plan gratuito) | Build de Vite servido con CDN y HTTPS incluidos, en el mismo proveedor y dashboard que el backend — evita administrar una cuenta/proveedor adicional (Vercel/Netlify) con el plazo de 2 semanas y 1 sola desarrolladora. |
| Hosting Backend | Render (Web Service, plan Starter, de pago, ~US$7/mes) | Despliegue simple de un servicio Node/Express, variables de entorno fáciles de configurar. El plan de pago evita el "cold start" del plan gratuito (que suspende el servicio tras inactividad) — importante porque la app se usa a diario en horario de alquiler. |
| Repositorio | GitHub | Integración directa con Render para despliegue continuo de ambos servicios (Static Site + Web Service). |
| Envío de correo | Resend (plan gratuito) | API simple desde Node/Express, plan gratuito con volumen muy por encima de lo que este negocio necesita (RF23–RF24); evita configurar SMTP manualmente. |
| Almacenamiento de archivos | Supabase Storage (plan gratuito) | Guarda las imágenes de comprobante de pago (RF25) fuera de la base de datos relacional (evita guardar binarios pesados en Postgres); plan gratuito suficiente para el volumen de este negocio. |
 
<br>

**Diagrama de arquitectura de capas**
 
Al ser una PWA desplegada 100% en servicios cloud administrados (PaaS/Serverless), no hay un servidor físico a mantener: el "Sistema Operativo" y el "Hardware" están abstraídos por el proveedor, pero igual se documentan para que quede explícito sobre qué corre cada capa del stack recién definido.
 
<br>

<img src="assets/architecture/diagram.png" alt="Diagrama de Arquitectura de tres capas" width="650"/>

La matriz cruza las tres capas de la arquitectura de despliegue (Presentación, Aplicación, Datos) contra los tres niveles técnicos que las sostienen (Software, Sistema Operativo, Hardware), mostrando qué corre concretamente en cada intersección:
 
- **Presentación:** el software es la PWA (React + TypeScript + Vite); el sistema operativo y el hardware son los del dispositivo del administrador — Android o iOS en un celular, o el sistema operativo del laptop/PC desde donde también puede administrarse. No hay servidor propio en esta capa: el navegador del dispositivo interpreta directamente los archivos de la PWA.

- **Aplicación:** el software es la API (Node.js + Express + TypeScript), con Resend integrado para el envío de correos de confirmación. Corre sobre un contenedor Linux (Ubuntu) administrado por Render, que es también el proveedor de hardware/cómputo de esta capa — sin servidor físico propio ni configuración manual del sistema operativo.

- **Datos:** el software es PostgreSQL junto con Prisma como ORM, y Docker como herramienta para levantar una instancia local de Postgres en desarrollo. En producción, corre sobre Linux (Ubuntu) administrado por Supabase, que también actúa como proveedor de hardware/almacenamiento de esta capa.

<br>

## 4.7. Análisis Técnico-Económico de la Infraestructura

Análisis comparativo de tres alternativas por elemento técnico, organizado por capa de la arquitectura (Presentación, Aplicación, Datos) evaluando en cada una las categorías de Software/Hardware/Sistema Operativo aplicables, con justificación de la opción elegida (retomando y detallando las decisiones ya adelantadas en el stack). Además de la comparativa técnica genérica (framework, lenguaje, motor), cada capa documenta la **configuración real desplegada** y la compara contra alternativas equivalentes de otros proveedores, no solo entre planes del mismo proveedor. Los servicios de integración y el presupuesto de inversión total se documentan de forma transversal al final, por ser decisiones que aplican a todo el proyecto y no a una capa específica.

<br>

### 4.7.1. Capa de Presentación

**Software (framework)**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| React + Vite | Librería de UI más usada del mercado, ecosistema maduro, `vite-plugin-pwa` listo para PWA, ya dominado por la desarrolladora. | ✅ |
| Vue 3 + Vite | Curva de aprendizaje suave, buen soporte PWA, pero requeriría aprenderlo desde cero en un plazo de 2 semanas. | — |
| Angular | Framework completo (incluye routing, forms, DI), pero con mayor curva de aprendizaje y boilerplate — sobredimensionado para 8-11 pantallas. | — |

<br>

*Justificación:* 

**React** se elige por la madurez de su ecosistema (mayor disponibilidad de librerías y soluciones ya probadas para los requisitos del proyecto) y por el soporte de primera clase para PWA vía `vite-plugin-pwa`, factor clave para cumplir RNF04 (instalación sin tienda de aplicaciones) dentro de un plazo de desarrollo de 2 semanas.

<br>

**Lenguaje**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| TypeScript | Tipado estático, comparte tipos con el backend (vía Prisma), detecta errores antes de producción. | ✅ |
| JavaScript | Sin tipado, más rápido de escribir al inicio pero mayor riesgo de errores en tiempo de ejecución. | — |

<br>

*Justificación:* 

**TypeScript** de punta a punta (frontend + backend) permite compartir contratos de datos y atrapar errores de integración en tiempo de compilación, valioso dado que es una sola desarrolladora sin red de code review.

<br>

**Sistema Operativo**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Android / iOS (celular) | Dispositivo principal de uso diario de Carlos y su trabajador en campo. | ✅ |
| Windows / macOS / Linux (laptop) | Uso secundario, para configuración inicial o revisión desde escritorio. | ✅ |

<br>

*Justificación:* 

El sistema debe funcionar en los dispositivos que Carlos y su trabajador ya tienen (RNF09), por eso el diseño es mobile-first y la PWA es instalable sin tienda de aplicaciones (RNF04).

<br>

**Hardware**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Dispositivo propio del administrador | Celular/laptop personal de Carlos y su trabajador, sin costo adicional para el proyecto. | ✅ |
| Hardware dedicado (tablet fija en el local) | Mayor consistencia de experiencia, pero implica un costo de compra no contemplado en Propuesta 1. | — |

<br>

*Justificación:* 

La Propuesta 1 no contempla presupuesto para hardware dedicado; el sistema se diseña para funcionar bien en los dispositivos que ya existen.

<br>

**Hosting (Servidor del Static Site)**

El frontend compilado (`npm run build`) es un conjunto de archivos estáticos (HTML/CSS/TS) sin lógica de servidor, por lo que no requiere cómputo dedicado — solo un servicio de hosting estático con CDN. Se compararon cuatro proveedores bajo el mismo criterio:
 
<br>

| Proveedor | Plan evaluado | Ancho de banda | Otros límites relevantes | Elegido |
|---|---|---|---|---|
| **Render (Static Site)** | Free | Sin límite duro publicado, uso razonable | Despliegue automático desde GitHub, dominio propio con SSL gratuito, sin "cold start" (los sitios estáticos no se suspenden, a diferencia de los Web Services) | ✅ |
| Cloudflare Pages | Free | Sin límite de ancho de banda en GB, pero sí de solicitudes: **100,000 requests/día**, 200,000 eventos de observabilidad/día, 3,000 minutos de build/mes (500 builds/mes) | 20,000 archivos por sitio, ~300 ubicaciones de CDN | — |
| Netlify | Free (modelo de créditos desde sep. 2025) | ~15 GB/mes (300 créditos, 20 créditos/GB) | 15 despliegues a producción/mes aprox., timeout de funciones de 10s | — |
| Vercel | Hobby | 100 GB/mes | **Uso exclusivamente no comercial** — un proyecto que genera ingresos (como un sistema de alquiler de canchas) requeriría el plan Pro (US$20/mes) | — |

<br>

*Justificación:* 

Se eligió **Render (Static Site)** porque ya aloja el backend del proyecto (mismo proveedor, mismo dashboard, mismo flujo de despliegue continuo desde GitHub para frontend y backend), sin límite de solicitudes relevante para el volumen actual (2 administradores, uso interno) y sin costo. Cloudflare Pages y Netlify también cubrirían el volumen actual sin problema, pero desplegar el frontend en un proveedor distinto al del backend sumaría una cuenta y un flujo de configuración adicional sin un beneficio concreto para el tamaño de este proyecto. Vercel se descarta de plano porque su plan gratuito prohíbe el uso comercial, y este es un sistema que gestiona el cobro de un negocio real. El frontend se sirve bajo el dominio propio **`lacanchitadecarlos.moli-voleibol.com`**, con SSL automático y región **Global** (el CDN de Render distribuye el contenido estático sin necesidad de elegir una región específica, a diferencia del Web Service del backend).

<br>

### 4.7.2. Capa de Aplicación

**Software (framework backend)**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Node.js + Express | Framework minimalista, control total sobre la estructura (compatible con arquitectura hexagonal), stack ya dominado. | ✅ |
| NestJS | Framework más opinado, con DI y módulos incorporados que se asemejan a arquitectura hexagonal de fábrica, pero mayor curva de aprendizaje. | — |
| Firebase Functions | Backend serverless gestionado, pero atado al ecosistema Firebase (menor control sobre transacciones SQL, clave para RF06). | — |

<br>

*Justificación:* 

**Express** da la velocidad de desarrollo necesaria en 2 semanas sin sacrificar el control sobre transacciones de base de datos, indispensable para la invariante de no doble reserva (RF06).

<br>

**Lenguaje**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| TypeScript | Mismo lenguaje que el frontend, tipado compartido vía Prisma. | ✅ |
| JavaScript | Sin tipado; descartado | — |

<br>

*Justificación:* 

Consistencia end-to-end con el frontend.

<br>

**Motor de ejecución**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Node.js | Motor de ejecución de JavaScript/TypeScript en servidor, mismo runtime que se usa en desarrollo local. | ✅ |
| Deno | Runtime más moderno con TypeScript nativo, pero ecosistema de librerías más chico y menor compatibilidad con Prisma en 2024-2025. | — |
| Bun | Runtime muy rápido, pero aún menos maduro en producción para proyectos con Prisma/Express. | — |

<br>

*Justificación:* 

**Node.js** tiene la mayor compatibilidad probada con **Express + Prisma + Render**, sin riesgo de incompatibilidades de última hora en un plazo ajustado.

<br>

**Editor / IDE**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| WebStorm | IDE completo de JetBrains, integración nativa con TypeScript, Git y npm scripts, ya usado por la desarrolladora. | ✅ |
| VS Code | Editor gratuito, extensible, muy popular, pero requiere configurar extensiones equivalentes a lo que WebStorm trae de fábrica. | — |

<br>

*Justificación:* 

**WebStorm** ya es la herramienta de trabajo habitual de la desarrolladora — no hay curva de adaptación en un proyecto de 2 semanas.

<br>

**Herramientas de pruebas API**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Postman | Estándar de facto para probar endpoints REST manualmente durante el desarrollo, colecciones reutilizables. | ✅ |
| Insomnia | Alternativa más ligera, similar en funcionalidad, pero sin ventaja concreta sobre Postman para este proyecto. | — |
| Thunder Client (extensión VS Code) | Integrado al editor, pero atado a VS Code (no se usa aquí, ver Editor/IDE). | — |

<br>

*Justificación:* 

**Postman** es suficiente y ya conocido; no se requiere automatización de pruebas de API para el alcance de Propuesta 1.

<br>

**Sistema Operativo (entorno de ejecución)**
 
El backend se despliega en Render como **imagen Docker** (`render.yaml` con `runtime: docker`), construida a partir de un `Dockerfile` propio del repositorio (`FROM node:22-slim`), que instala dependencias, aplica las migraciones de Prisma (`prisma migrate deploy`) y levanta el servidor (`npm start`) en cada despliegue.

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Docker (imagen propia, `node:22-slim`) | El entorno de ejecución queda fijado por el `Dockerfile` (versión exacta de Node, dependencias de sistema como `python3`/`make`/`g++` necesarias para compilar `bcrypt`), garantizando que el contenedor de producción sea idéntico en cualquier entorno donde se construya la imagen. | ✅ |
| Build nativo de Render (sin Docker, Node autodetectado) | Render también puede construir el backend sin Dockerfile, autodetectando Node.js y ejecutando `npm install`/`npm start` directamente — más simple, pero deja el versionado exacto del entorno (versión de Node, librerías nativas del sistema operativo) en manos del buildpack de Render en vez de quedar declarado y versionado en el propio repositorio. | — |

<br>

*Justificación:* 

Se usa Docker porque el backend depende de `bcrypt`, un paquete con un componente nativo en C++ que requiere compilarse contra herramientas de sistema (`python3`, `make`, `g++`) — el `Dockerfile` declara explícitamente esas dependencias, evitando fallos de build silenciosos si el buildpack por defecto de Render cambiara de versión de Node o de imagen base en el futuro. En ambos casos el sistema operativo subyacente es Linux (Ubuntu/Debian, según la imagen base de Render o del propio `Dockerfile`), consistente con el entorno de desarrollo local (RNF07).


<br>

**Hardware (Web Service)**

<br>

| Proveedor | Plan gratuito | RAM / CPU | Particularidad |
|---|---|---|---|
| **Render** | Free | 512 MB / 0.1 CPU | Se suspende tras ~15 min de inactividad; se reactiva automáticamente al recibir tráfico (con latencia de arranque en frío) | ✅ |
| Railway | Free (con créditos de prueba, no permanente) | Variable según créditos consumidos | No ofrece un plan gratuito permanente para producción — los créditos gratuitos se agotan y el proyecto se pausa | — |
| Fly. io | Free (allowance limitado) | ~256 MB por VM compartida | Requiere tarjeta de crédito desde el registro; el excedente se cobra automáticamente, riesgo no deseado para un presupuesto fijo | — |

<br>

*Justificación:* 

Se eligió el plan **Free** de **Render**, no el Starter, para mantener el costo recurrente del backend en $ 0 durante Propuesta 1 — el volumen real (2 administradores, uso interno, sin usuarios finales concurrentes) no justifica pagar por eliminar el cold-start. La contrapartida asumida conscientemente es la latencia de arranque en frío tras inactividad prolongada (ej. la primera consulta de la mañana puede tardar unos segundos más mientras el contenedor se reactiva); por eso se implementó el endpoint `/health` (TS04), esto no elimina el cold-start, pero permite detectar y monitorear el estado del servicio en vez de que Carlos reporte "la app no funciona" sin poder diagnosticar la causa. Si el negocio crece a un punto donde la latencia de arranque afecte la operación diaria, la migración al plan Starter (US$7/mes) es inmediata, sin cambios de código. Frente a Railway y Fly. io, Render Free es la única opción sin riesgo de cobro inesperado y con reactivación automática (no requiere que el administrador la reinicie manualmente).

<br>

El backend corre como un **Render Web Service**, que sí requiere elegir un *Instance Type* (a diferencia del Static Site del frontend). Render ofrece los siguientes planes:

<br>

| Instance Type | Costo | RAM | CPU | Características |
|---|---|---|---|---|
| **Free** | US$ 0/mes | 512 MB | 0.1 CPU | Se suspende ("spin down") tras períodos de inactividad; sin acceso SSH, sin scaling, sin jobs puntuales, sin discos persistentes | ✅ |
| Starter | US$ 7/mes | 512 MB | 0.5 CPU | Sin downtime, SSH, scaling, jobs puntuales, discos persistentes | — |
| Standard | US$ 25/mes | 2 GB | 1 CPU | Igual que Starter, más recursos | — |
| Pro | US$ 85/mes | 4 GB | 2 CPU | Igual que Starter, más recursos | — |


<br>

Región desplegada: **Oregon (US West)**, bajo el dominio propio **`api.moli-voleibol.com`**.

<br>

### 4.7.3. Capa de Datos

**Motor de base de datos**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| PostgreSQL | Relacional, soporta transacciones ACID y constraints únicos a nivel de base de datos — necesario para blindar la invariante de no doble reserva (RF06) más allá de la validación en el backend. | ✅ |
| MySQL | También relacional y viable, pero el soporte de constraints/transacciones complejas de Supabase y el ecosistema de Prisma están más pulidos alrededor de Postgres. | — |
| MongoDB (NoSQL) | Flexible para datos no estructurados, pero un modelo de disponibilidad de canchas con relaciones fuertes (cancha–franja–cliente–pago) encaja naturalmente mejor en un modelo relacional. | — |

*Justificación:* 

La regla de negocio más crítica del sistema (RF06) se apoya en constraints e integridad transaccional — terreno donde una base relacional como **PostgreSQL** es más robusta que una NoSQL.

<br>

**Cliente de base de datos**

<br>

| Alternativa | Descripción | Elegido |
|---|---|---|
| Prisma Studio | Cliente visual incluido con el ORM elegido, sin instalación adicional, refleja el schema tipado directamente. | ✅ |
| pgAdmin | Cliente dedicado de PostgreSQL, más completo para administración avanzada, pero redundante frente a Prisma Studio para las necesidades de este proyecto. | — |

*Justificación:* 

**Prisma Studio** cubre las necesidades de inspección y edición de datos durante el desarrollo sin agregar una herramienta adicional al flujo de trabajo.

<br>

**Hardware (hosting de base de datos gestionada)**

<br>

| Proveedor | Plan gratuito | Almacenamiento BD | Incluye almacenamiento de archivos | Particularidad |
|---|---|---|---|---|
| **Supabase** | Free | 500 MB | Sí (1 GB, mismo proyecto) | Un solo proveedor para BD + Storage + panel de administración; egress 5 GB/mes | ✅ |
| Neon | Free | 0.5 GB (equivalente) | No — requiere contratar un proveedor de Storage aparte | Serverless con "scale-to-zero" (el cómputo se apaga solo, no cobra por inactividad), pero no resuelve RF25/RF31 (fotos y comprobantes) por sí solo | — |
| filess. io | Free | 10 MB | No | Almacenamiento muy por debajo de lo necesario incluso para el volumen actual (27 MB ya en uso); descartado por insuficiente, no por diseño | — |

*Justificación:* 

**Supabase** se mantiene como la elección correcta porque resuelve en un mismo proveedor tanto la base de datos relacional (RF06) como el almacenamiento de archivos (RF25 comprobantes, RF31 fotos de cancha) — Neon obligaría a sumar un tercer servicio de Storage (ej. AWS S3 o Cloudinary) para cubrir la misma necesidad, y filess. io directamente no tiene espacio suficiente ni en su plan pagado más económico para el volumen ya en uso. Consolidar en un proveedor reduce el número de cuentas, dashboards y puntos de facturación a administrar por una sola desarrolladora.

El proyecto está desplegado en **Supabase** con la siguiente configuración real:

<br>

| Parámetro | Valor |
|---|---|
| Proveedor de infraestructura subyacente | AWS |
| Región | `us-west-1` |
| Instancia de cómputo | Nano (CPU compartida, hasta 0.5 GB de memoria en el plan Free) |
| Plan | Free |

<br>

Consumo actual (ciclo de facturación vigente, referencial — crece con el uso):

| Recurso | Uso actual | Límite del plan Free |
|---|---|---|
| Egress | 49 MB | 5 GB |
| Tamaño de base de datos | 27 MB | 500 MB |
| Usuarios activos mensuales (Supabase Auth, no usado en este proyecto) | 0 | 50,000 |
| File Storage | 1 MB | 1 GB |

<br>

El consumo actual está muy por debajo de los límites del plan gratuito, consistente con la proyección de crecimiento estimada en el punto siguiente.

<br>

**Cómo funciona el almacenamiento (Supabase Storage)**

El proyecto usa un único bucket llamado `la-canchita-de-carlos`, organizado en tres carpetas según el tipo de archivo:

| Carpeta | Contenido | Requisito funcional |
|---|---|---|
| `perfiles/` | Fotos de perfil de los administradores (`User`) | — |
| `canchas/` | Fotos de las canchas (`Court`) | RF31 |
| `comprobantes/` | Imágenes de comprobante de pago (`Payment`) | RF25 |

<br>

El flujo de subida es el mismo para los tres casos, implementado en `SupabaseFileStorage` (adaptador de la interfaz `FileStorage` del `platform/`):

1. El backend valida el archivo antes de subirlo: solo `image/jpeg`, `image/png` o `image/webp`, y un tamaño máximo de 5 MB — cualquier otro formato o archivo más pesado se rechaza con un error 400 antes de tocar Supabase.
2. El archivo se sube al bucket con una ruta generada (`carpeta/uuid.extensión`), evitando colisiones de nombres entre distintos administradores o clientes.
3. La base de datos **nunca almacena el archivo en sí**, solo la ruta (`usu_photo_url`, `cou_photo_url`, `boo_receipt_url` en el schema) — el archivo físico vive únicamente en Supabase Storage. Esto mantiene las filas de la base de datos livianas incluso con muchas imágenes asociadas (ver proyección de crecimiento).
4. Para mostrar una imagen, el backend genera una **URL firmada** (`createSignedUrl`) con un tiempo de expiración, en vez de exponer el bucket públicamente — esto controla quién puede ver los comprobantes de pago y fotos, sin depender de que el bucket sea público.
5. Al eliminar una cancha, un usuario o reemplazar una foto, el backend llama explícitamente a `delete()` sobre el archivo anterior en Storage — evita archivos huérfanos que ocupen espacio sin estar referenciados por ninguna fila de la base de datos (corrección aplicada tras detectar este caso durante el desarrollo).

<br>

**Proyección de crecimiento de datos**

Con el motor y el proveedor ya elegidos arriba, cabe verificar si van a alcanzar en el tiempo. Uso diario del sistema no implica los mismos riesgos de escala para la base de datos relacional que para el almacenamiento de imágenes — crecen a ritmos muy distintos:

- **Filas en PostgreSQL (`Booking`, `Payment`, `Customer`):** techo teórico de ~60 alquileres/día si las ~5 canchas estuvieran ocupadas 12 horas diarias sin excepción → ~21,900 filas/año → ~219,000 en 10 años. A unos cientos de bytes por fila, esto representa apenas 40-50 MB acumulados en una década, en el escenario más exagerado posible. PostgreSQL maneja sin esfuerzo tablas de millones de filas — la base relacional no es un cuello de botella ni con uso diario sostenido por años. El consumo real observado (27 MB de 500 MB, ver tabla de consumo actual) es consistente con esta proyección.

- **Imágenes (comprobantes de pago, fotos de canchas):** en el mismo escenario de uso intenso, con una imagen de ~300-800 KB por comprobante, el volumen anual ronda los 10-15 GB. El plan gratuito de Supabase Storage (1 GB) se quedaría corto en meses, no en años — este es el recurso que realmente hay que vigilar, no la base de datos. El uso actual (1 MB de 1 GB) confirma que todavía se está muy al inicio de esa curva.

- **Mitigación preventiva (documentada para no volverse un problema en 1-2 años):** índices en `Booking` sobre `(courtId, fecha, hora)` — ya necesarios para prevenir doble reserva y que de paso aceleran las consultas del calendario aunque la tabla crezca; compresión/resize de imágenes en el cliente antes de subir (ej. máx. 1000px de ancho, suficiente para verificar un comprobante); y una eventual política de retención de comprobantes antiguos a definir con Carlos (decisión de negocio, no técnica) si no necesita conservarlos indefinidamente por temas contables. Si el consumo de Storage se acerca al límite de 1 GB, la migración al plan Pro de Supabase (US$25/mes, incluye 100 GB) es la vía directa sin cambiar de proveedor ni de código.

<br>

### 4.7.4. Servicios de Integración

<br>

| Servicio | Alternativas consideradas | Elegido | Justificación |
|---|---|---|---|
| Envío de correo transaccional | Resend, SendGrid, Amazon SES | **Resend** | Plan gratuito: 3,000 correos/mes (máx. 100/día), 1 dominio verificado — muy por encima de lo que RF23–RF24 necesitan (correo puntual, no masivo); API simple desde Node/Express; evita configurar SMTP manualmente como exigiría SES. El dominio de envío se verifica gratis sobre el subdominio (`moli-voleibol.com`), sin costo adicional de dominio. |
| Repositorio y control de versiones | GitHub, GitLab | **GitHub** | Integración directa con Render para despliegue continuo (CI/CD) de ambos servicios (Static Site + Web Service) sin configuración adicional. |
| Contacto directo con clientes | WhatsApp (enlace `wa.me`), API de WhatsApp Business | **Enlace `wa.me`** | RF30 solo requiere abrir un chat existente, no enviar mensajes automatizados — un enlace directo cubre la necesidad sin el costo/complejidad de la API oficial de WhatsApp Business (reservada para la Propuesta 2). |
| Dominio propio | Registro en Cloudflare, GoDaddy, Namecheap | **Cloudflare Domains** | `moli-voleibol.com` registrado por **US$ 10.46/año** (pago único anual, sin renovación automática obligatoria); Cloudflare no cobra markup sobre el precio mayorista del TLD, a diferencia de la mayoría de registradores. Sobre este dominio raíz se crearon dos subdominios sin costo adicional: `api.moli-voleibol.com` (backend, apuntando al Web Service de Render) y `lacanchitadecarlos.moli-voleibol.com` (frontend, apuntando al Static Site de Render), ambos vía registro CNAME en modo "DNS only" para no interferir con el certificado SSL automático de Render. |

<br>

### 4.7.5. Presupuesto de Inversión Total (transversal)

| Concepto | Costo | Frecuencia |
|---|---|---|
| Desarrollo (Propuesta 1) | S/ 1,700 | Pago único |
| Dominio `moli-voleibol.com` (Cloudflare Registrar) | US$ 10.46 (~S/ 39) | Anual |
| Render Web Service — backend (plan Free) | US$ 0/mes | Recurrente, plan gratuito |
| Render Static Site — frontend (plan Free) | US$ 0/mes | Recurrente, plan gratuito |
| Supabase (base de datos + Storage, plan Free) | US$ 0/mes | Recurrente, plan gratuito |
| Resend (correo transaccional, plan Free) | US$ 0/mes | Recurrente, plan gratuito |
| **TOTAL implementado (pago único + dominio del primer año)** | **≈ S/ 1,739** | — |
| **TOTAL mensual** | **S/ 0/mes** | Mensual |
| **TOTAL anual (renovación de dominio)** | **≈ S/ 39/año** | Anual |

<br>

A diferencia de lo estimado inicialmente, el sistema opera hoy con **costo recurrente mensual de S/ 0**, tanto ambas partes de la aplicación corren en los planes gratuitos de Render, y la base de datos/almacenamiento en el plan gratuito de Supabase. El único costo recurrente real del proyecto es la renovación anual del dominio (~US$10-15/año, según el precio al momento de renovar). 

La contrapartida de no pagar el plan Starter de Render (US$7/mes) es el cold-start del backend tras inactividad, una decisión presupuestaria consciente para Propuesta 1, revertible en cualquier momento sin cambios de código si el crecimiento del negocio lo justifica.

<br>

### 4.7.6. Seguridad

Medidas de seguridad implementadas de forma transversal a las tres capas de la arquitectura, con la ubicación exacta en el código donde se aplica cada una.

<br>

| Medida | Implementación | Motivo |
|---|---|---|
| Autenticación por token | JWT (`jsonwebtoken`), firmado con `JWT_SECRET` (variable de entorno, no versionada), payload mínimo (`userId`, `isOwner`), expiración configurable (`JWT_EXPIRES_IN`, actualmente 1h). | Evita mantener estado de sesión en el servidor para cada request; el propio token demuestra la identidad del administrador sin consultar la base de datos en cada llamada. |
| Registro de sesiones activas | Cada login crea una fila en `sessions` (`ses_token_hash`, IP, user-agent, fecha de expiración) — el token nunca se guarda en texto plano, solo su hash (SHA-256). Al cerrar sesión o cambiar contraseña, la sesión se marca `ses_revoked = true`. | Trazabilidad de accesos (desde qué IP/dispositivo se conectó cada administrador) y base para poder invalidar sesiones activas. |
| Hash de contraseñas | bcrypt con 12 salt rounds (`platform/security/password.ts`). Nunca se guarda ni se registra la contraseña en texto plano, ni siquiera en logs de error. | Estándar de la industria para almacenamiento de credenciales — un volcado de la base de datos no expone las contraseñas reales. |
| Autorización por rol (RBAC de 2 niveles) | Middleware `requireAuth` (exige un JWT válido) + `requireOwner` (exige `isOwner: true` en el payload) aplicado a rutas sensibles (autorizar/rechazar solicitudes de acceso, ver administradores activos). | Separa lo que puede hacer cualquier administrador de lo reservado al dueño (EP07), sin necesitar un sistema de permisos más complejo para solo 2 roles. |
| Tokens de un solo uso, hasheados | Los tokens de verificación de correo (`email_verification_tokens`) y de reseteo de contraseña (`password_reset_tokens`) se generan con `crypto.randomBytes(32)` (aleatoriedad criptográfica) y se guardan en la base de datos **hasheados con SHA-256**, no en texto plano, con fecha de expiración y bandera `used`. | Aunque alguien accediera a un volcado de la base de datos, no podría reconstruir el enlace de verificación/reseteo original a partir del hash — mismo principio que el hash de contraseñas. |
| Registro de administradores controlado | Una cuenta nueva no se crea directamente: pasa por `AccessRequest` (pendiente de aprobación del dueño) y, tras aprobarse, el `User` nace en `PENDING_VERIFICATION` hasta confirmar el correo (US20-21, US34) — evita cuentas activas con un correo mal escrito o no verificado. | Control de acceso de dos pasos (aprobación humana + verificación de correo) sin depender de un proveedor de identidad externo. |
| Bootstrap del primer usuario protegido | La creación del primer administrador dueño (`bootstrapOwner.usecase.ts`) exige un `SETUP_TOKEN` secreto (variable de entorno, sin valor por defecto — si falta, el endpoint responde error 500 en vez de operar sin protección). | Evita que el endpoint de creación del primer dueño quede abierto sin control una vez desplegado en producción. |
| CORS restringido | `cors({ origin: FRONTEND_URL })` — la API solo acepta solicitudes desde el dominio del frontend (`lacanchitadecarlos.moli-voleibol.com` en producción), no desde cualquier origen. | Reduce la superficie de ataque frente a scripts de terceros que intenten llamar a la API desde otro dominio. |
| Validación y saneamiento de entrada | `platform/validation/validators.ts`: normalización de texto/correo/teléfono y validaciones explícitas (formato de correo, longitud mínima/máxima, montos positivos) antes de persistir cualquier dato, en cada caso de uso. | Rechaza datos malformados antes de que lleguen a la base de datos, con mensajes de error específicos por campo. |
| Prevención de inyección SQL | Todo acceso a base de datos pasa por Prisma ORM con consultas parametrizadas — no hay SQL crudo concatenado con datos de entrada en ningún punto del código. | Elimina por diseño la clase de vulnerabilidad más común en APIs con base de datos relacional. |
| Manejo de errores sin fuga de información | `errorMiddleware` centralizado: traduce errores conocidos de Prisma (violación de unicidad P2002, de llave foránea P2003) y de Multer a mensajes claros en español; cualquier error no anticipado responde genéricamente `"Error interno del servidor"` (500) y se registra en el log del servidor (`console.error`), sin exponer el stack trace ni detalles internos al cliente. | Evita que un error inesperado revele detalles de la implementación (nombres de tablas, rutas de archivos, versión de librerías) a quien esté probando la API. |
| Cifrado en tránsito (HTTPS) | Certificados SSL automáticos en las tres capas: Render (frontend y backend) y Supabase (base de datos y Storage) — no hay tráfico sin cifrar entre el navegador del administrador, la API y la base de datos. | Protege credenciales, tokens y datos de clientes/pagos de ser interceptados en la red. |
| Gestión de secretos | `JWT_SECRET`, `SETUP_TOKEN`, `RESEND_API_KEY`, `SUPABASE_SERVICE_ROLE_KEY`, `DATABASE_URL`/`DIRECT_URL` nunca se versionan en el repositorio (`.gitignore` excluye `.env`); en producción se inyectan como variables de entorno en Render (`sync: false` en `render.yaml`, configuradas manualmente en el dashboard, no en el código). | Un acceso al repositorio de GitHub no expone ninguna credencial de producción. |
| Almacenamiento de archivos con acceso controlado | Las imágenes (fotos de cancha, comprobantes de pago, fotos de perfil) no son públicas: se sirven mediante URLs firmadas con expiración (`createSignedUrl`), no por acceso directo al bucket | Un comprobante de pago no queda expuesto indefinidamente por una URL adivinable o indexada. |

<br>

**Limitación conocida:** 

La revocación de sesión (`sessions.revoke` / `revokeAllForUser`, disparada al cerrar sesión o cambiar contraseña) actualiza la base de datos, pero el middleware `requireAuth` valida únicamente la firma y expiración del JWT — no consulta la tabla `sessions` en cada request. En la práctica, un token ya emitido sigue siendo válido hasta su expiración natural (1h) aunque la sesión se haya marcado como revocada. El riesgo está acotado por la corta duración del token, pero no es una invalidación inmediata real todavía.

<br>

---

# Capítulo V: Software Object-Oriented Design

## 5.1. Class Diagrams — Backend

El backend está organizado como un monolito modular con **arquitectura hexagonal (ports & adapters)**, dividido en 6 bounded contexts independientes. Cada uno sigue la misma estructura de 4 capas: `domain/model` (entidades y puertos, sin dependencias de framework), `application` (casos de uso), `infrastructure/persistence/repositories` (adaptadores Prisma) e `interfaces/rest` (routers Express + DTOs). Todos los contextos comparten dos piezas de infraestructura transversal: la conexión a **Supabase Postgres** vía Prisma, y **Supabase Storage** para archivos (fotos, comprobantes).

La conexión a la base de datos usa dos URLs distintas de Supabase: `DATABASE_URL` (conexión con *connection pooling*/PgBouncer, la que usa la app en tiempo de ejecución a través del adaptador `PrismaPg`) y `DIRECT_URL` (conexión directa, usada solo por Prisma CLI para migraciones, en `prisma.config.ts`). Los archivos (fotos de perfil, fotos de cancha, comprobantes de pago) no se guardan en la base de datos: se suben a un bucket de **Supabase Storage** (`la-canchita-de-carlos`) a través del adaptador `SupabaseFileStorage`, organizados en 3 carpetas `perfiles/`, `canchas/` y `comprobantes/` y la base de datos solo guarda la *ruta* del archivo (`usu_photo_url`, `cou_photo_url`, `boo_receipt_url`), no la imagen. Al reemplazar o quitar una foto, el sistema borra el archivo anterior del bucket para no acumular archivos huérfanos.

<br>

### 5.1.1. Bounded context: Bookings (Reservas, Canchas y Mantenimiento)

![Class Backend Diagrams](assets/class-diagrams/backend/bookings-context.png)

Este es el contexto más grande del sistema: agrupa las entidades `Booking`, `Court` y `ScheduleBlock`, con sus reglas de dominio (`overlaps`, `hasConflict`, `assertWithinOperatingHours`, `assertNotInPast`, `assertCourtAvailableForBooking`). Expone **17 endpoints** bajo `/bookings` (5) y `/courts` (12): registrar/editar/cancelar/buscar reservas (incluyendo reservas en serie multidía/recurrente vía `POST /bookings/serie`), y el CRUD completo de canchas más el manejo de bloqueos de horario por mantenimiento (`/courts/:id/bloqueos*`).

**Conexión con Supabase:** 

`PrismaBookingRepository`, `PrismaCourtRepository` y `PrismaScheduleBlockRepository` leen/escriben sobre las tablas `bookings`, `courts` y `schedule_blocks`. Además, `addCourtPhoto.usecase.ts` usa `SupabaseFileStorage` para subir la foto de la cancha a la carpeta `canchas/` del bucket.

**Conexión con Resend:** 

Al registrar una reserva (individual o en serie), este contexto dispara dos correos — `sendBookingConfirmation` al cliente (solo si dejó un correo de contacto opcional en el formulario, ya que `Customer` no guarda correo en la base de datos) y `sendNewBookingAlert` a todos los demás administradores activos. También genera notificaciones internas (campanita) de tipo `NEW_BOOKING` en cada registro, y `COURT_MAINTENANCE` cuando se programa un bloqueo **en serie** (el bloqueo individual de una sola franja no notifica).

<br>

### 5.1.2. Bounded context: Customers (Clientes)

![Class Backend Diagrams](assets/class-diagrams/backend/customers-context.png)

Contexto simple, con una única entidad `Customer` (nombre, teléfono, DNI/RUC opcional, estado). Expone **5 endpoints** bajo `/customers`: listar/buscar, crear, editar, desactivar (borrado lógico, `DELETE` marca `INACTIVE` en vez de eliminar el registro) y consultar el historial de reservas de un cliente (`GET /customers/:id/historial`).

**Conexión con Supabase:** 

`PrismaCustomerRepository` opera sobre la tabla `customers`. Este contexto no sube archivos a Storage (el campo de foto del cliente se eliminó del modelo) ni dispara correos directamente — el correo de confirmación de reserva lo dispara el contexto `bookings`, usando el `customerEmail` que llega en el formulario, no un dato persistido de `Customer`.

<br>

### 5.1.3. Bounded context: Identity (Usuarios, Sesiones y Acceso)

![Class Backend Diagrams](assets/class-diagrams/backend/identity-context.png)

Agrupa `User`, `Session`, `PasswordResetToken`, `EmailVerificationToken` y `AccessRequest`. Expone **20 endpoints**: 5 bajo `/auth` (login, logout, bootstrap del primer owner, y el flujo completo de "olvidé mi contraseña") y 15 bajo `/users` (solicitudes de acceso, gestión de perfil propio, gestión de administradores, subida/borrado de foto de perfil).

**Conexión con Supabase:** 

5 repositorios Prisma (`PrismaUserRepository`, `PrismaSessionRepository`, `PrismaPasswordResetTokenRepository`, `PrismaEmailVerificationTokenRepository`, `PrismaAccessRequestRepository`) sobre sus tablas respectivas. `uploadUserPhoto.usecase.ts`/`removeUserPhoto.usecase.ts` usan `SupabaseFileStorage` con la carpeta `perfiles/`.

**Conexión con Resend:**  

Es el contexto que más tipos de correo dispara — `sendNewAccessRequestAlert` (a todos los owners, cuando alguien pide una cuenta), `sendAdminDecision` (al solicitante, al aprobar/rechazar), `sendEmailVerification` (al nuevo admin, junto con la aprobación) y `sendPasswordReset` (al pedir recuperar contraseña). No genera notificaciones internas (campanita) — las solicitudes de acceso hoy solo notifican por correo, no en la app.

<br>

### 5.1.4. Bounded context: Notifications (Notificaciones y Correos)

![Class Backend Diagrams](assets/class-diagrams/backend/notifications-context.png)

Este contexto tiene doble función: por un lado, la entidad `Notification` y sus **2 endpoints** bajo `/notifications` (`GET /` para listar las propias, `PATCH /:id/leida` para marcarlas leídas) alimentan la campanita del panel — de los 6 tipos definidos en el enum, solo `NEW_BOOKING` y `COURT_MAINTENANCE` están conectados a un disparador real (ver 5.1.1); `ACCESS_REQUEST`, `PAYMENT_PENDING`, `BOOKING_CANCELLED` y `GENERAL` quedan reservados para una fase futura.

Por otro lado, este mismo contexto es dueño del **adaptador de Resend** (`ResendNotificationSender`, que implementa el puerto `NotificationSender`), usado por los otros contextos (`bookings`, `identity`) para enviar sus 6 tipos de correo. Todos comparten una misma plantilla HTML (`emailTemplate.ts`) para mantener consistencia visual. Si la variable `RESEND_API_KEY` no está configurada, el envío se omite silenciosamente (útil en desarrollo local, sin bloquear el flujo principal).

**Conexión con Supabase:** 

`PrismaNotificationRepository` sobre la tabla `notifications`. No sube archivos a Storage.

<br>

### 5.1.5. Bounded context: Panel (Métricas del Dashboard)

![Class Backend Diagrams](assets/class-diagrams/backend/panel-context.png)

Contexto de solo lectura, sin entidad propia: agrega datos de `bookings` y `payments` para alimentar el resumen del día en el Panel. Expone **3 endpoints** bajo `/panel`: reservas del día, ingreso del día y pagos pendientes del día.

**Conexión con Supabase:** 

`PrismaPanelRepository` ejecuta consultas de agregación directamente sobre las tablas `bookings` y `payments` (no tiene su propia tabla). No dispara correos ni notificaciones — es puramente consultivo.

<br>

### 5.1.6. Bounded context: Payments (Pagos)

![Class Backend Diagrams](assets/class-diagrams/backend/payments-context.png)

Contiene la entidad `Payment` (historial de pagos parciales/totales por reserva). Expone **4 endpoints** bajo `/payments`: registrar un pago, listar los pagos de una reserva, subir el comprobante y generar una URL firmada temporal para verlo.

**Conexión con Supabase:** 

`PrismaPaymentRepository` sobre la tabla `payments`, con una operación atómica (`registerPaymentAtomic`) que inserta el pago y actualiza `boo_paid_amount`/`boo_payment_status` en `bookings` en la misma transacción, para que ambas tablas nunca queden desincronizadas. `attachReceipt.usecase.ts` usa `SupabaseFileStorage` con la carpeta `comprobantes/`, y `createSignedUrl` genera enlaces temporales (no públicos) para ver el comprobante. Este contexto no dispara correos ni notificaciones internas propias.

<br>

## 5.2. Class Diagrams — Frontend

El frontend está organizado por **módulo de negocio**, cada uno con su carpeta `hooks/` (llamadas a la API vía TanStack Query, usando `apiClient` de Axios con el token JWT inyectado por interceptor) y `components/` (las pantallas). En total son 18 pantallas repartidas en 20 rutas.

<br>

### 5.2.1. Mapa General de Módulos

![Class Frontend Diagrams](assets/class-diagrams/frontend/overview.png)

Vista general de cómo se relacionan los 7 módulos entre sí antes de entrar al detalle de cada uno. Los módulos `bookings`, `customers`, `dashboard` y `settings` tienen su propia carpeta `hooks/` que llama a `apiClient`/`queryClient` (módulo `shared`); `courts` es el único módulo sin hooks propios, reutiliza directamente los de `bookings` (`useAllCourts`, `useBookings`) y también sus modales de mantenimiento. `dashboard` a su vez depende de los hooks de `bookings` para calcular ocupación y próximo horario libre, y `bookings` depende de `useCustomers` (módulo `customers`) para la búsqueda de cliente al reservar. Todas las pantallas protegidas pasan por `AppShell`/`ProtectedRoute` (módulo `shared`), que a su vez dependen de `AuthProvider`/`useAuth` (módulo `auth`) y de `useNotifications`.

<br>

### 5.2.2. Módulo `auth` — Sesión y Acceso

![Class Frontend Diagrams](assets/class-diagrams/frontend/auth.png)

- **`LoginPage`** (`/login`): formulario de inicio de sesión con usuario/correo y contraseña; llama a `POST /auth/login` y guarda el token vía `useAuth`.
- **`RequestAccessPage`** (`/solicitar-acceso`): formulario para pedir una cuenta de administrador nueva; llama a `POST /users/solicitudes`.
- **`SolicitudEnviadaPage`** (`/solicitud-enviada`): pantalla de confirmación tras enviar la solicitud, sin llamadas a la API.
- **`ForgotPasswordPage`** (`/olvide-password`): pide el correo para iniciar la recuperación; llama a `POST /auth/olvide-password`.
- **`ResetPasswordPage`** (`/restablecer-password`): toma el token de la URL y define la nueva contraseña; llama a `POST /auth/restablecer-password`.
- **`VerificarCorreoPage`** (`/verificar-correo`): confirma el correo de un administrador recién aprobado usando el token del enlace del correo; llama a `GET /users/verificar`.

Todas comparten el layout `AuthLayout` y se apoyan en `AuthProvider`/`useAuth` (contexto de React que guarda el usuario y el token, y expone `login`/`logout`/`updateUser`).

<br>

### 5.2.3. Módulo `dashboard` — Panel Principal

![Class Frontend Diagrams](assets/class-diagrams/frontend/dashboard.png)

- **`PanelPage`** (`/panel`): pantalla de inicio tras loguearse. Combina 3 fuentes de datos (`useTodayBookings` contra `/panel/alquileres-del-dia`, `useCourts`, `useScheduleBlocks`) para mostrar el resumen del día, el próximo horario libre calculado en el cliente (`calculateNextFreeSlot`), el gráfico de ocupación semanal (`calculateWeeklyOccupancy`), avisos de mantenimiento del día y el botón flotante (FAB) de acceso directo a "Nueva reserva".

<br>

### 5.2.4. Módulo `bookings` — Calendario, Reservas y Mantenimiento

![Class Frontend Diagrams](assets/class-diagrams/frontend/bookings.png)

- **`CalendarioPage`** (`/calendario`): calendario de disponibilidad por cancha en 3 vistas (día/semana/mes), construido a partir de `useCourts`, `useBookings`, `useScheduleBlocks`/`useScheduleBlocksRange`; permite reservar o programar mantenimiento directo desde una celda libre.
- **`NuevaReservaPage`** (`/calendario/nueva-reserva` y `/calendario/nueva-reserva/:id/editar`): formulario para registrar o editar una reserva (individual, multidía o recurrente vía `POST /bookings` o `POST /bookings/serie`), elegir cliente, método de pago y adjuntar comprobante.
- **`ReservasPage`** (`/reservas`): listado/búsqueda de todas las reservas con filtros, gestión de pagos pendientes y cancelaciones (`POST /bookings/:id/cancelar`).
- **`ProgramarMantenimientoModal`** (modal, sin ruta propia): formulario para bloquear una o varias franjas horarias por mantenimiento, usado tanto desde `CalendarioPage` como desde `CanchasPage`.
- **`MantenimientosProgramadosModal`** (modal, sin ruta propia): lista los próximos mantenimientos programados de una cancha y permite cancelarlos.

<br>

### 5.2.5. Módulo `courts` — Canchas

Este módulo no tiene diagrama de clases propio (sus componentes `CanchasPage` y `NuevaCanchaPage` consumen directamente los hooks de `bookings`):

- **`CanchasPage`** (`/canchas`): catálogo de canchas — ver, activar/desactivar, eliminar, y acceso a mantenimientos programados.
- **`NuevaCanchaPage`** (`/canchas/nueva` y `/canchas/:id/editar`): formulario para registrar o editar una cancha (nombre, deporte, tarifa, horario de atención, foto).

<br>

### 5.2.6. Módulo `customers` — Clientes

![Class Frontend Diagrams](assets/class-diagrams/frontend/customers.png)

- **`ClientesPage`** (`/clientes`): ficha de clientes registrados — buscar, crear, editar, ver historial de reservas, contactar por WhatsApp y eliminar (con modal de confirmación propio). Usa `useCustomers` contra `GET /customers`.

<br>

### 5.2.7. Módulo `settings` — Ajustes y Administración

![Class Frontend Diagrams](assets/class-diagrams/frontend/settings.png)

- **`AjustesPage`** (`/ajustes`): perfil propio (foto, nombre, usuario, correo, contraseña vía `PATCH /users/me/*`), vista previa de solicitudes de acceso pendientes y de usuarios activos (ambas solo visibles para el owner), y eliminar cuenta propia.
- **`SolicitudesAccesoPage`** (`/ajustes/solicitudes`): gestión completa de solicitudes de acceso (aprobar/rechazar vía `useApproveAccessRequest`/`useRejectAccessRequest`) y de administradores con acceso (quitar acceso/eliminar vía `useDeactivateAdminUser`) — protegida para que solo el owner pueda entrar (redirige a `/ajustes` si no lo es).

<br>

### 5.2.8. Módulo `shared` — Componentes Base

![Class Frontend Diagrams](assets/class-diagrams/frontend/shared.png)

- **`AppShell`**: layout compartido por todas las pantallas protegidas — barra de navegación, buscador, campanita de notificaciones (`useNotifications`/`useMarkNotificationRead` contra `/notifications`), botón de ayuda/WhatsApp, avatar y menú inferior en móvil.
- **`ProtectedRoute`**: envuelve las rutas que requieren sesión activa; redirige a `/login` si no hay usuario autenticado.
- **`NotFoundPage`** (`*`, cualquier ruta no reconocida): página 404 con enlace de regreso al Panel o al Login según si hay sesión activa.
- **`apiClient`/`queryClient`**: instancia de Axios con interceptor de `Authorization: Bearer <token>`, y el `QueryClient` de TanStack Query que cachea y sincroniza todas las llamadas anteriores.

<br>

---

# Capítulo VI: Database Design

## 6.1. Modelo Entidad-Relación

**Nomenclatura.**

Tablas y columnas se nombran en inglés, en snake_case, con un prefijo fijo de 3 letras por tabla en cada columna (ej. tabla `users` tiene las columnas `usu_id`, `usu_name`). En el script SQL ejecutable (`schema.sql`, Anexos) el prefijo se escribe en minúscula (`usu_id`) porque PostgreSQL vuelve case-sensitive cualquier identificador en mayúscula si no se lo entrecomilla siempre; en este capítulo se muestra en mayúscula (`USU_id`) solo por legibilidad. Los nombres de tabla siguen el mismo aggregate en inglés del Lenguaje Ubicuo y el diseño de clases: `User`, `Court`, `Customer`, `Booking`, `ScheduleBlock`, `AccessRequest`, `Payment`. El sufijo `_id` se usa de forma consistente para toda PK y FK del modelo.

<br>

### 6.1.1. Entidades

El modelo tiene 11 entidades, agrupadas en 4 categorías según el módulo del sistema al que pertenecen.

**a) Entidades Base**

- **Court** (`courts`, prefijo `COU_`): catálogo administrable de canchas del colegio — nombre, deporte, superficie, tarifa por hora, horario de atención y estado operativo (RF11-RF12).

- **ScheduleBlock** (`schedule_blocks`, prefijo `BLO_`): franjas horarias bloqueadas manualmente por mantenimiento u otro motivo, asociadas a una cancha (RF07, RF32).

**b) Entidades de Identidad y Acceso**

- **User** (`users`, prefijo `USU_`): administradores con acceso al sistema — Carlos (dueño) y su trabajador.

- **Session** (`sessions`, prefijo `SES_`): historial de inicios de sesión y control de sesiones activas por administrador (US01, US03).

- **PasswordResetToken** (`password_reset_tokens`, prefijo `PRT_`): tokens de un solo uso para el flujo de "Olvidé mi contraseña".

- **EmailVerificationToken** (`email_verification_tokens`, prefijo `EVT_`): tokens de un solo uso enviados por correo para confirmar la cuenta de un administrador recién aprobado, antes de que pueda iniciar sesión.

- **AccessRequest** (`access_requests`, prefijo `REQ_`): solicitudes de cuenta nueva, pendientes de aprobación por el administrador dueño (RF20-RF22).

**c) Entidades de Reservas**

- **Customer** (`customers`, prefijo `CUS_`): personas o grupos externos que alquilan canchas de forma recurrente y quedan registrados con ficha propia (RF09, RF30).

- **Booking** (`bookings`, prefijo `BOO_`): reservas de cancha — fecha, horario, cliente, estado de pago (ver nota abajo) y las reservas en serie (multidía/recurrente).

- **Payment** (`payments`, prefijo `PAY_`): historial de pagos parciales o totales registrados sobre una reserva — monto, método (efectivo/Yape/otro) y fecha (US14-US16).

*Nota de diseño — `Payment` sí tiene tabla propia:* a diferencia del planteamiento inicial del Event Storming (donde se evaluó no separarlo), la implementación final sí extrajo `Payment` como aggregate con tabla propia, porque el negocio necesitaba conservar el historial de cada pago parcial (monto, método, fecha), no solo el acumulado. Para no penalizar cada lectura de `bookings` con un JOIN/SUM sobre `payments`, `Booking` mantiene columnas denormalizadas (`BOO_total_amount`, `BOO_paid_amount`, `BOO_payment_status`, `BOO_receipt_url`) que se actualizan de forma atómica cada vez que se registra un nuevo `Payment` (RNF06).


**d) Entidades de Soporte y Notificaciones**

- **Notification** (`notifications`, prefijo `NTF_`): avisos internos mostrados en la campanita del panel — nueva reserva, pago pendiente, solicitud de acceso, mantenimiento, etc.

<br>

### 6.1.2. Enfoque relacional

**Relaciones del módulo Identidad y Acceso**

- `User` ➔ `Session`: un administrador inicia muchas sesiones a lo largo del tiempo (US01). Tipo de relación: 1 a N. Clave foránea: `SES_user_id` en la tabla `sessions`.
- `User` ➔ `PasswordResetToken`: un administrador puede pedir varios tokens de recuperación (uno por intento de "Olvidé mi contraseña"). Tipo de relación: 1 a N. Clave foránea: `PRT_user_id` en la tabla `password_reset_tokens`.
- `User` ➔ `EmailVerificationToken`: un administrador nuevo recibe un token para confirmar su correo antes de poder iniciar sesión. Tipo de relación: 1 a N. Clave foránea: `EVT_user_id` en la tabla `email_verification_tokens`.
- `User` ➔ `AccessRequest`: el administrador dueño aprueba o rechaza solicitudes de acceso; cada solicitud aprobada queda enlazada al `User` que se creó a partir de ella (RF21). Tipo de relación: 1 a N (opcional). Clave foránea: `REQ_created_user_id` en la tabla `access_requests`.

**Relaciones del módulo Canchas**

- `Court` ➔ `ScheduleBlock`: una cancha puede tener varios bloqueos por mantenimiento; un bloqueo pertenece a una sola cancha. Tipo de relación: 1 a N. Clave foránea: `BLO_court_id` en la tabla `schedule_blocks`.
- `Court` ➔ `Booking`: una cancha puede tener muchos alquileres; un alquiler es de una sola cancha (RF06). Tipo de relación: 1 a N. Clave foránea: `BOO_court_id` en la tabla `bookings`.

**Relaciones del módulo Reservas**

- `Customer` ➔ `Booking`: un cliente registrado puede tener muchas reservas; la relación es opcional porque las reservas grupales/walk-in (ej. "Torneo Vóley Mix") no requieren un `Customer` con ficha propia, solo guardan el nombre en `BOO_customer_name`. Tipo de relación: 1 a N (opcional). Clave foránea: `BOO_customer_id` en la tabla `bookings`.
- `Booking` ➔ `Payment`: un alquiler puede recibir varios pagos parciales a lo largo del tiempo (US14-US16); cada pago pertenece a una sola reserva. Tipo de relación: 1 a N. Clave foránea: `PAY_booking_id` en la tabla `payments`. Al eliminarse la reserva, sus pagos se eliminan en cascada.

**Relaciones del módulo Notificaciones**

- `User` ➔ `Notification`: un administrador puede recibir muchas notificaciones; la relación es opcional porque una notificación puede ser general (dirigida a todos, `NTF_user_id` = NULL) en vez de individual. Tipo de relación: 1 a N (opcional). Clave foránea: `NTF_user_id` en la tabla `notifications`.

<br>

## 6.2. Database Diagrams

Diagrama de Base de Datos entidad-relación físico de La Canchita de Carlos, con llaves primarias (PK), foráneas (FK) y únicas (UK):

<br>

![Database Diagram](assets/database-diagram/diagrama-db.png)

<br>

### Diagrama de la base de datos en Prisma

![Supabase Database Diagram](assets/database-diagram/supabase-db.png)

<br>

## 6.3. Diccionario de Datos

Detalle completo campo por campo, agrupado por entidad, con tipo SQL exacto, restricciones y descripción funcional cruzada con los RF/US correspondientes.

<br>

**Tabla: `users`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| USU_id | SERIAL | PK | Identificador único del administrador. |
| USU_name | VARCHAR(150) | NOT NULL | Nombre completo. |
| USU_username | VARCHAR(60) | NOT NULL, UNIQUE | Usuario para iniciar sesión (alternativo al correo). |
| USU_email | VARCHAR(150) | NOT NULL, UNIQUE | Correo del administrador, usado para login y recuperación de contraseña. |
| USU_password_hash | VARCHAR(255) | NOT NULL | Hash bcrypt/argon2 de la contraseña. Nunca texto plano (RNF01). |
| USU_is_owner | BOOLEAN | NOT NULL, DEFAULT false | `true` solo para Carlos; habilita aprobar/rechazar solicitudes de acceso (RF21). |
| USU_status | ENUM (`user_status_enum`) | NOT NULL, DEFAULT 'ACTIVE' | `ACTIVE` / `INACTIVE` / `PENDING_VERIFICATION`. Los administradores nuevos quedan en `PENDING_VERIFICATION` hasta confirmar su correo; revocar acceso marca `INACTIVE` en vez de borrar el registro. |
| USU_photo_url | TEXT | — | URL de la foto de perfil. |
| USU_last_access | TIMESTAMPTZ | — | Último inicio de sesión exitoso (redundante con `sessions`, para lectura rápida). |
| USU_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha de alta. |
| USU_updated_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Se actualiza automáticamente en cada UPDATE (trigger). |

<br>

**Tabla: `sessions`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| SES_id | SERIAL | PK | Identificador de la sesión. |
| SES_user_id | INTEGER | NOT NULL, FK → users.USU_id | Administrador dueño de la sesión. |
| SES_token_hash | VARCHAR(255) | NOT NULL, UNIQUE | Hash del refresh token / session id (US01, `SessionStarted`). |
| SES_ip_address | VARCHAR(45) | — | IP de origen del login (soporta IPv4 e IPv6). |
| SES_user_agent | TEXT | — | Navegador/dispositivo usado. |
| SES_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Momento del inicio de sesión. |
| SES_expires_at | TIMESTAMPTZ | NOT NULL | Momento en que la sesión deja de ser válida. |
| SES_revoked | BOOLEAN | NOT NULL, DEFAULT false | `true` si se cerró sesión manualmente antes de expirar (`SessionClosed`, US03). |

<br>

**Tabla: `password_reset_tokens`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| PRT_id | SERIAL | PK | Identificador del token. |
| PRT_user_id | INTEGER | NOT NULL, FK → users.USU_id | Administrador que solicitó recuperar su contraseña. |
| PRT_token_hash | VARCHAR(255) | NOT NULL, UNIQUE | Hash del token enviado por correo (nunca el token en texto plano). |
| PRT_expires_at | TIMESTAMPTZ | NOT NULL | Vencimiento del token (recomendado: 1 hora desde su creación). |
| PRT_used | BOOLEAN | NOT NULL, DEFAULT false | `true` una vez consumido; impide reutilizar el mismo enlace. |
| PRT_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Momento de la solicitud. |

<br>

**Tabla: `email_verification_tokens`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| EVT_id | SERIAL | PK | Identificador del token. |
| EVT_user_id | INTEGER | NOT NULL, FK → users.USU_id | Administrador que debe confirmar su correo. |
| EVT_token_hash | VARCHAR(255) | NOT NULL, UNIQUE | Hash del token enviado por correo (nunca el token en texto plano). |
| EVT_expires_at | TIMESTAMPTZ | NOT NULL | Vencimiento del token. |
| EVT_used | BOOLEAN | NOT NULL, DEFAULT false | `true` una vez consumido; impide reutilizar el mismo enlace. |
| EVT_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Momento en que se generó. |

<br>

**Tabla: `access_requests`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| REQ_id | SERIAL | PK | Identificador de la solicitud. |
| REQ_name | VARCHAR(150) | NOT NULL | Nombre de quien solicita acceso. |
| REQ_email | VARCHAR(150) | NOT NULL | Correo de contacto. |
| REQ_phone | VARCHAR(30) | — | Teléfono de contacto. |
| REQ_password_hash | VARCHAR(255) | NOT NULL | Contraseña propuesta, hasheada; se copia a `users` solo si se aprueba. |
| REQ_status | ENUM (`request_status_enum`) | NOT NULL, DEFAULT 'PENDING' | `PENDING` / `APPROVED` / `REJECTED` (RF20-RF22). |
| REQ_created_user_id | INTEGER | FK → users.USU_id, NULL | Se llena al aprobar; enlaza la solicitud con el `User` creado. |
| REQ_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha de la solicitud. |
| REQ_resolved_at | TIMESTAMPTZ | — | Fecha en que se aprobó o rechazó. |

<br>

**Tabla: `courts`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| COU_id | SERIAL | PK | Identificador de la cancha. |
| COU_name | VARCHAR(100) | NOT NULL | Nombre visible (ej. "Cancha 1", "Vóley 2"). |
| COU_sport | VARCHAR(50) | NOT NULL | Disciplina (Fútbol 5, Vóley, Básquet, etc.). |
| COU_surface | VARCHAR(80) | — | Tipo de superficie (ej. "Sintético 5"). |
| COU_price_per_hour | NUMERIC(10,2) | NOT NULL, CHECK ≥ 0 | Tarifa por hora (RF12). |
| COU_status | ENUM (`court_status_enum`) | NOT NULL, DEFAULT 'ACTIVE' | `ACTIVE` / `MAINTENANCE`. |
| COU_enabled | BOOLEAN | NOT NULL, DEFAULT true | Si acepta nuevas reservas (independiente del estado operativo). |
| COU_photo_url | TEXT | — | Foto de la cancha (RF31). |
| COU_description | TEXT | — | Notas u observaciones adicionales. |
| COU_open_time | VARCHAR(5) | — | Hora de apertura de la cancha (formato HH:mm), usada para calcular disponibilidad y bloquear franjas fuera de horario. |
| COU_close_time | VARCHAR(5) | — | Hora de cierre de la cancha (formato HH:mm). |
| COU_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha de alta (RF11). |
| COU_updated_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Última edición. |

<br>

**Tabla: `schedule_blocks`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| BLO_id | SERIAL | PK | Identificador del bloqueo. |
| BLO_court_id | INTEGER | NOT NULL, FK → courts.COU_id | Cancha bloqueada. |
| BLO_date | DATE | NOT NULL | Fecha bloqueada. |
| BLO_time | TIME | NOT NULL | Franja horaria bloqueada. |
| BLO_reason | VARCHAR(200) | — | Nota del motivo del bloqueo (RF32), opcional (US31, escenario 3). |
| BLO_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha en que se registró el bloqueo. |

<br>

**Tabla: `customers`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| CUS_id | SERIAL | PK | Identificador del cliente. |
| CUS_name | VARCHAR(150) | NOT NULL | Nombre o razón social. |
| CUS_phone | VARCHAR(30) | NOT NULL | Número de contacto / WhatsApp (RF30). |
| CUS_document_number | VARCHAR(20) | UNIQUE (si no es NULL) | DNI (persona natural) o RUC (persona jurídica) (RF09). |
| CUS_status | ENUM (`customer_status_enum`) | NOT NULL, DEFAULT 'ACTIVE' | `ACTIVE` / `INACTIVE`. |
| CUS_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha de registro. |
| CUS_updated_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Última edición. |

<br>

**Tabla: `bookings`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| BOO_id | SERIAL | PK | Identificador del alquiler. |
| BOO_court_id | INTEGER | NOT NULL, FK → courts.COU_id | Cancha reservada. |
| BOO_customer_id | INTEGER | FK → customers.CUS_id, NULL | Cliente registrado; NULL en reservas grupales/walk-in (US28). |
| BOO_customer_name | VARCHAR(150) | NOT NULL | Nombre a mostrar, aun si BOO_customer_id es NULL (ver 6.2.1, excepción de normalización). |
| BOO_type | VARCHAR(80) | — | Tipo de reserva libre (pichanga/torneo/evento) o equipo/grupo (RF33). |
| BOO_date | DATE | NOT NULL | Fecha del alquiler. |
| BOO_start_time | TIME | NOT NULL | Hora de inicio. |
| BOO_end_time | TIME | NOT NULL, CHECK > BOO_start_time | Hora de fin (duración libre, no limitada a bloques fijos). |
| BOO_status | ENUM (`booking_status_enum`) | NOT NULL, DEFAULT 'BOOKED' | `BOOKED` / `CANCELLED` / `COMPLETED` (US05). |
| BOO_payment_status | ENUM (`payment_status_enum`) | NOT NULL, DEFAULT 'PENDING' | `PENDING` / `PARTIAL` / `PAID` (US14-US15). |
| BOO_total_amount | NUMERIC(10,2) | NOT NULL, DEFAULT 0, CHECK ≥ 0 | Monto total del alquiler. |
| BOO_paid_amount | NUMERIC(10,2) | NOT NULL, DEFAULT 0, CHECK ≥ 0, CHECK ≤ BOO_total_amount | Monto abonado hasta el momento (se actualiza al registrar cada `Payment`). |
| BOO_booking_type | ENUM (`booking_type_enum`) | NOT NULL, DEFAULT 'SINGLE' | `SINGLE` / `MULTIDAY` / `RECURRING`. |
| BOO_series_id | UUID | NULL | Agrupa las fechas generadas por una misma reserva multidía/recurrente. |
| BOO_series_payment_mode | ENUM (`series_payment_mode_enum`) | NULL | `INDIVIDUAL` (se cobra fecha por fecha) o `LUMP_SUM` (se cobra en bloque). |
| BOO_series_label | VARCHAR(200) | NULL | Descripción legible de la serie (ej. "Reserva recurrente semanal (8 fechas)"). |
| BOO_series_total_dates | INTEGER | NULL | Cantidad total de fechas de la serie. |
| BOO_series_index | INTEGER | NULL | Posición de este alquiler dentro de la serie (1, 2, 3…). |
| BOO_receipt_url | TEXT | NULL | Imagen/PDF del comprobante de pago (RF25). |
| BOO_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Fecha de registro. |
| BOO_updated_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Última edición (US05, escenario 2). |

<br>

**Tabla: `payments`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| PAY_id | SERIAL | PK | Identificador del pago. |
| PAY_booking_id | INTEGER | NOT NULL, FK → bookings.BOO_id (ON DELETE CASCADE) | Reserva a la que corresponde el pago. |
| PAY_amount | NUMERIC(10,2) | NOT NULL, CHECK ≥ 0 | Monto de este pago (parcial o total). |
| PAY_method | VARCHAR(30) | NOT NULL | Método de pago: `EFECTIVO` / `YAPE` / `OTRO`. |
| PAY_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Momento en que se registró el pago (US14-US16). |

<br>

**Tabla: `notifications`**

| Campo | Tipo | Restricciones | Descripción |
|---|---|---|---|
| NTF_id | SERIAL | PK | Identificador de la notificación. |
| NTF_user_id | INTEGER | FK → users.USU_id, NULL | Destinatario; NULL = notificación general para todos los administradores. |
| NTF_type | ENUM (`notification_type_enum`) | NOT NULL, DEFAULT 'GENERAL' | `ACCESS_REQUEST` / `PAYMENT_PENDING` / `NEW_BOOKING` / `BOOKING_CANCELLED` / `COURT_MAINTENANCE` / `GENERAL`. |
| NTF_title | VARCHAR(150) | NOT NULL | Título corto mostrado en el panel de notificaciones. |
| NTF_message | TEXT | — | Detalle del aviso. |
| NTF_link_url | VARCHAR(200) | — | Ruta interna del frontend a la que navega al hacer clic (ej. `/reservas`). |
| NTF_read | BOOLEAN | NOT NULL, DEFAULT false | Si el administrador ya la marcó como leída. |
| NTF_created_at | TIMESTAMPTZ | NOT NULL, DEFAULT now() | Momento en que se generó. |

<br>

---
# Capítulo VII: Gestión del Proyecto

La gestión del proyecto sigue **Scrum**, adaptado a un equipo de una sola desarrolladora y a un plazo comprimido de 2 semanas. Se mantienen los artefactos esenciales del marco pero conservando su propósito: trabajar en incrementos cortos, entregables y verificables, con retroalimentación del cliente al cierre de cada sprint.
 
El proyecto se divide en **2 sprints de 1 semana cada uno**. El Sprint 1 prioriza el subdominio núcleo (Bookings) y el riesgo de negocio más alto (la doble reserva) antes que los subdominios de soporte, siguiendo el orden de prioridad establecido en el Product Backlog. El Sprint 2 completa la construcción del backend, conecta el sistema de punta a punta y lo despliega en producción.
 
**Herramienta de gestión:** el seguimiento de sprints, historias y tareas se realiza en **Jira**, donde el Product Backlog se modela como el backlog del proyecto, cada sprint corresponde a un Sprint de Jira con su propio tablero, y cada Work-Item se registra como una tarea vinculada a su historia de usuario o historia técnica correspondiente. Esto permite trazar el avance real de cada sprint directamente desde el tablero, además de lo documentado en este capítulo.
 
<br>

## 7.1. Plan de Sprints
 
El proyecto se organiza en 2 sprints de 1 semana cada uno (días 1-7 y días 8-14), con una sola desarrolladora como equipo, siguiendo el orden real de construcción: primero la documentación y el diseño, luego el frontend contra un fake API (para no bloquearse esperando el backend), en paralelo/después el backend con su base de datos, y al final la conexión real entre ambos junto con la preparación del despliegue.
 
<br>

| Fase | Contenido | Story Points | Cuándo |
|---|---|---|---|
| 1. Documentación y diseño | Capítulos I-IV completos, wireframes, mockups, prototipo Figma. | — | Días 1-2 |
| 2. Frontend (fake API) | Todas las pantallas construidas en React contra un fake JSON API (`json-server`), sin depender del backend real. | 63 SP | Días 3-7 (Sprint 1) |
| 3. Backend + Base de datos | API en Express + Prisma, schema de base de datos, lógica de dominio y endpoints, contra Supabase. | 54 SP | Días 8-11 (Sprint 2) |
| 4. Conexión frontend-backend + despliegue | Reemplazo del fake API por la API real, pruebas de integración, despliegue en Render/Supabase. | — | Días 12-14 (Sprint 2) |
 
<br>

**Herramienta de seguimiento:** Jira
 
<br>

## 7.2. Sprint 1
 
### 7.2.1. Sprint Planning 1
 
<br>

| Campo | Detalle |
|---|---|
| **Sprint #** | Sprint 1 |
| **Sprint Planning Background** | En este sprint se cierra la documentación y el diseño (Capítulos I-IV) y se construyen todas las pantallas del frontend en React contra un fake API (`json-server`), sin depender del backend real. El objetivo es tener una interfaz funcional de punta a punta que Carlos pueda revisar tempranamente, sin bloquear el desarrollo esperando que el backend esté listo. |
| **Date** | 12/07/2026 |
| **Location** | Trabajo individual|
| **Prepared By** | Salinas Guzmán, Brianna |
| **Sprint 1 Goal** | Nuestro enfoque está en cerrar la documentación base y construir todas las pantallas de la interfaz de usuario contra un fake API. Creemos que esto permitirá validar tempranamente los flujos de uso con Carlos sin esperar al backend real. Esto se confirmará cuando las pantallas de Identidad y Acceso, Gestión de Reservas, Gestión de Canchas y Gestión de Clientes estén completamente navegables contra `json-server`. |
| **Sprint 1 Velocity** | 63 |
| **Sum of Story Points** | 63 |
 
<br>

### 7.2.2. Sprint Backlog 1
 
**Objetivo del Sprint:** cerrar la documentación y el diseño, y construir todas las pantallas de la interfaz en React funcionando de punta a punta contra un fake API (`json-server`) — así el desarrollo de la parte gráfica no queda bloqueado esperando que el backend real esté listo, y sirve además como validación temprana de los flujos con Carlos.
 
**Sprint Goal:** *Carlos puede navegar el flujo completo de reservas, canchas y clientes sobre datos de prueba, y validar que la interfaz cubre lo que necesita antes de que exista backend real.*
 
**Story Points comprometidos: 63 SP | Duración: 1 semana | Stack: React / Vite / TypeScript / Tailwind / json-server**
 
<br>

**Work-Items del Sprint 1:**
 
<br>

| Sprint # | | | | | | | |
|:---|:---|:---|:---|:---|:---|:---|:---|
| **Sprint 1** | **User Story** | | **Work-Item / Task** | | | | |
| **ID** | **Título** | **SP** | **ID** | **Título** | **Descripción** | **Estimación** | **Status** |
| — | Setup del proyecto | — | T-01 | Wireframes, mockups y prototipo Figma | Diseño de baja y alta fidelidad de las 8-11 pantallas, más prototipo navegable (3.3-3.4) — base visual de todo lo que sigue. | 6h | Done |
| — | Setup del proyecto | — | T-02 | Configuración inicial del frontend | React + Vite + TypeScript + Tailwind + `vite-plugin-pwa`, estructura de carpetas por bounded context. | 2h | Done |
| — | Setup del proyecto | — | T-03 | Fake API con `json-server` | `db.json` de prueba con canchas, alquileres y clientes de ejemplo. | 2h | Done |
| — | Setup del proyecto | — | T-04 | Schema de base de datos en Prisma | Diseño completo del schema y los índices del Capítulo VI, listo para migrarse en el Sprint 2. | 4h | Done |
| US01 | Iniciar sesión de forma segura | 3 | T-05 | Pantalla de Login | Formulario de usuario/contraseña conectado a `json-server`; valida credenciales y redirige al panel. | 3h | Done |
| US02 | Operar con múltiples cuentas de administrador | 2 | T-06 | Independencia de sesión por dispositivo | Sesión persistida en `localStorage` por navegador/dispositivo, sin invalidar la sesión de otro administrador. | 1h | Done |
| US03 | Proteger la información del negocio sin sesión válida | 2 | T-07 | `ProtectedRoute` | Componente de ruta protegida que redirige a Login si no hay sesión activa; aplicado a todas las rutas del panel. | 2h | Done |
| US04 | Visualizar disponibilidad de canchas | 5 | T-08 | Vista de Calendario (día/semana/mes) | `CalendarioPage` mostrando franjas libres, alquiladas y bloqueadas por cancha, con cambio de vista sin perder el estado. | 5h | Done |
| US05 | Registrar, editar y cancelar un alquiler | 5 | T-09 | Formulario "Nueva Reserva" (registrar/editar) | `NuevaReservaPage` con cliente, cancha, fecha y horario; reutilizado para edición. | 4h | Done |
| | | | T-10 | Cancelar alquiler | Acción de cancelar desde `ReservasPage`, libera la franja de inmediato en el calendario. | 2h | Done |
| US06 | Impedir la doble reserva de una cancha | 5 | T-11 | Validación de conflicto de horario (frontend) | Verificación contra `json-server` antes de confirmar una reserva; bloquea el envío si la franja ya está ocupada. | 3h | Done |
| TS01 | Endpoint de alquiler con validación de conflicto | 3 | T-12 | Diseño del constraint anti-doble-reserva | Índice único (`courtId` + fecha + hora, filtrado por estado) diseñado en el schema Prisma (Capítulo VI), listo para el Sprint 2. | 2h | Done |
| US07 | Bloquear una franja por mantenimiento | 3 | T-13 | Modal de bloqueo de franja | Bloqueo manual de una franja libre desde el calendario; rechaza el bloqueo si ya hay un alquiler activo. | 2h | Done |
| US31 | Registrar y ver el motivo de un bloqueo por mantenimiento | 3 | T-14 | Motivo de bloqueo | Campo de texto opcional en el modal de bloqueo (T-13) y su visualización en el calendario. | 2h | Done |
| US32 | Registrar tipo de reserva y nombre de equipo | 2 | T-15 | Tipo de reserva y equipo | Campos "tipo de reserva" y "nombre de equipo/grupo" en Nueva Reserva, opcionales. | 2h | Done |
| US08 | Buscar y filtrar el historial de alquileres | 3 | T-16 | Filtros de Reservas | Filtros por fecha, cancha, estado y cliente en `ReservasPage`. | 3h | Done |
| US28 | Registrar un cliente nuevo desde el formulario de alquiler | 3 | T-17 | Cliente embebido en Nueva Reserva | Formulario de alta de cliente dentro del mismo flujo de reserva, sin salir a la sección de Clientes. | 3h | Done |
| TS09 | Endpoint de alquiler con creación de cliente embebida | 2 | T-18 | Contrato de `POST /bookings` con cliente embebido | Diseño del payload que acepta `clienteNuevo` o `clienteId`, base para T-17 en el backend real. | 1h | Done |
| US11 | Registrar y editar canchas | 3 | T-19 | Pantalla de Cancha (crear/editar) | `NuevaCanchaPage` con nombre y disciplina; rechaza nombres duplicados. | 3h | Done |
| US12 | Configurar precios por cancha | 2 | T-20 | Precio por hora | Campo de precio en `NuevaCanchaPage` con validación de monto mayor a cero. | 1h | Done |
| US13 | Ver disponibilidad consolidada de todas las canchas | 3 | T-21 | Vista consolidada de canchas | `CanchasPage` mostrando el estado de disponibilidad de las 5 canchas para una fecha en una sola vista. | 3h | Done |
| US29 | Adjuntar fotos a una cancha | 3 | T-22 | Carga de fotos de cancha | Selector de imágenes en `NuevaCanchaPage`, con estado vacío si la cancha no tiene fotos. | 2h | Done |
| TS10 | Endpoint de carga de fotos de cancha | 3 | T-23 | Contrato de `POST /courts/{id}/fotos` | Diseño del endpoint y del bucket de Supabase Storage a usar en el Sprint 2. | 1h | Done |
| US09 | Registrar, editar y eliminar clientes | 3 | T-24 | Pantalla de Clientes (CRUD) | `ClientesPage` con alta, edición y eliminación, conservando el historial de alquileres al eliminar. | 3h | Done |
| US10 | Consultar historial de un cliente | 2 | T-25 | Ficha de cliente | Detalle de cliente con lista de alquileres asociados ordenados por fecha. | 2h | Done |
| TS04 | Endpoint de health check | 1 | T-26 | Contrato de `/health` | Definición de la respuesta esperada (`200 ok` / `503`) para verificar backend y base de datos en Sprint 2. | 1h | Done |
 
<br>

**Trabajo no funcional del sprint:**

- Documentación completa de Capítulos I-IV (perfil de negocio, requisitos, glosario, User Stories, backlog, diseño UX/UI, DDD y arquitectura).

- Wireframes, mockups de alta fidelidad y prototipo navegable en Figma.

- Repositorio de frontend con React + Vite + TypeScript + Tailwind, `json-server` sirviendo un `db.json` de prueba con canchas, alquileres y clientes de ejemplo.

- Diseño del schema de base de datos en Prisma (Capítulo VI) e índices necesarios para blindar RF06 a nivel de base de datos, listo para cuando arranque el backend real en el Sprint 2.

<br>

### 7.2.3. Development Evidence for Sprint Review
 
Durante el Sprint 1 el trabajo se realizó directamente sobre la rama `main` del repositorio de frontend, consistente con el flujo descrito. El desarrollo avanzó en el orden real de construcción: primero la configuración base del proyecto y el fake API, luego las pantallas de autenticación, después el Panel con datos reales del `db.json`, y por último la gestión de Canchas, Clientes y Ajustes — cerrando con modo oscuro y reservas recurrentes/multidía.
 
<br>

| Repository | Branch | Commit ID | Commit Message | Committed on (Date) |
|---|---|---|---|---|
| la-canchita-de-carlos-frontend | main | `b4b5e0e` | chore: configuración de Tailwind, PWA, routing, fake API y estructura de carpetas | 2026-07-16 |
| la-canchita-de-carlos-frontend | main | `96b72a4` | feat: pantallas de Login y Solicitar Acceso con estilos de marca | 2026-07-17 |
| la-canchita-de-carlos-frontend | main | `5649ecd` | Responsive de Login, Solicitar Acceso y Panel; datos del Panel desde db.json | 2026-07-17 |
| la-canchita-de-carlos-frontend | main | `48ee0cf` | Responsive de Login, Solicitar Acceso y Panel; datos del Panel desde db.json | 2026-07-17 |
| la-canchita-de-carlos-frontend | main | `5429d5a` | Agrega gestión de Canchas, Clientes y Ajustes/Solicitudes de acceso con responsive mobile | 2026-07-18 |
| la-canchita-de-carlos-frontend | main | `b299c0f` | feat: modo oscuro completo + reservas recurrentes/multidía + fixes de UI | 2026-07-18 |
 
<br>

### 7.2.4. Execution Evidence for Sprint Review
 

<br>

![Execution Evidence - Login/Panel](assets/sprints/sprint-1/execution-1.png)
 
![Execution Evidence](assets/sprints/sprint-1/execution-2.png)
 
![Execution Evidence](assets/sprints/sprint-1/execution-3.png)

![Execution Evidence](assets/sprints/sprint-1/execution-4.png)

![Execution Evidence](assets/sprints/sprint-1/execution-5.png)

![Execution Evidence](assets/sprints/sprint-1/execution-6.png)

![Execution Evidence](assets/sprints/sprint-1/execution-7.png)

![Execution Evidence](assets/sprints/sprint-1/execution-8.png)

![Execution Evidence](assets/sprints/sprint-1/execution-9.png)

![Execution Evidence](assets/sprints/sprint-1/execution-10.png)
 
<br>

### 7.2.5. Services Documentation Evidence for Sprint Review
 
Durante el Sprint 1 el alcance estuvo centrado en el frontend contra un fake API; no hubo servicios de backend reales que documentar todavía. Como preparación técnica (TS01, TS04, TS09, TS10) y se diseñó el schema de base de datos, que sirve de base para los endpoints reales del Sprint 2.
 
<br>

![JSON Fake API](assets/sprints/sprint-1/services01.png)

![JSON Fake API](assets/sprints/sprint-1/services02.png)

![JSON Fake API](assets/sprints/sprint-1/services03.png)

![JSON Fake API](assets/sprints/sprint-1/services04.png)

![JSON Fake API](assets/sprints/sprint-1/services05.png)

![JSON Fake API](assets/sprints/sprint-1/services06.png)
 
<br>

## 7.3. Sprint 2
 
### 7.3.1. Sprint Planning 2
 
<br>

| Campo | Detalle |
|---|---|
| **Sprint #** | Sprint 2 |
| **Sprint Planning Background** | En este sprint se construye el backend real (Express + Prisma + Supabase) con toda la lógica de dominio, se reemplaza el fake API del frontend por la conexión real, y se deja el sistema desplegado en producción. |
| **Date** | 20/07/2026 |
| **Location** | Trabajo individual |
| **Prepared By** | Salinas Guzmán, Brianna |
| **Sprint 1 Review Summary** | Se completó la documentación de Capítulos I-IV y todas las pantallas del frontend quedaron funcionando contra `json-server`, validadas navegacionalmente. Queda pendiente para este sprint construir el backend real y reemplazar los datos de prueba. |
| **Sprint 1 Retrospective Summary** | Trabajar contra un fake API permitió avanzar el frontend sin bloquearse esperando el backend, y adelantar el diseño del schema de base de datos (Capítulo VI) para que el Sprint 2 empiece con el modelo de datos ya validado contra las pantallas reales. |
| **Sprint 2 Goal** | Nuestro enfoque está en construir el backend real completo — reservas, canchas, clientes, pagos, panel, identidad y notificaciones — y conectar el frontend ya construido en el Sprint 1, reemplazando el fake API. Creemos que esto permitirá tener el sistema completo, desplegado y usable por Carlos. Esto se confirmará cuando todas las pantallas consuman la API real contra Supabase y el sistema esté accesible públicamente desde un celular real (PWA instalable). |
| **Sprint 2 Velocity** | 169 |
| **Sum of Story Points** | 172 |
 
<br>

### 7.3.2. Sprint Backlog 2
 
**Objetivo del Sprint:** construir el backend real (Express + Prisma + Supabase) con toda la lógica de dominio, reemplazar el fake API del frontend por la conexión real, y dejar el sistema desplegado en producción.
 
**Sprint Goal:** *Carlos puede usar el sistema completo — reservas (incluyendo series multi-día/recurrentes), canchas, clientes, pagos, panel, autorización de administradores, notificaciones internas y por correo — desde su celular, con datos reales persistidos en Supabase, sin ningún dato de prueba expuesto.*
 
**Story Points comprometidos: 172 SP | Duración: 1 semana (con trabajo continuo hasta el cierre) | Stack: Express / TypeScript / Prisma / Supabase / Render**

> *Nota: el Sprint Backlog original solo planificaba 59 SP (pagos, panel, identidad, correos y ajustes). Al reconciliar contra el Product Backlog vigente y el historial real de commits, se confirmó que durante esta misma ventana (20–25 jul) también se construyó el núcleo completo de Reservas/Canchas/Clientes (EP02–EP04) y las historias agregadas en la última revisión del backlog (series de reservas, notificaciones internas, recuperación de contraseña, gestión de administradores, eliminar cancha, ver pagos/comprobante, bootstrap del dueño). Se agregan aquí como Work-Items T-28 en adelante, con su respaldo de commit.*
 
<br>

**Work-Items del Sprint 2:**
 
<br>

| Sprint # | | | | | | | |
|:---|:---|:---|:---|:---|:---|:---|:---|
| **Sprint 2** | **User Story** | | **Work-Item / Task** | | | | |
| **ID** | **Título** | **SP** | **ID** | **Título** | **Descripción** | **Estimación** | **Status** |
| — | Setup del proyecto | — | T-01 | Configuración inicial del backend | Express + TypeScript + Prisma, migraciones aplicadas contra Supabase — base para todos los endpoints que siguen. | 3h | Done |
| — | Setup del proyecto | — | T-02 | Endpoint de login (TS02) + JWT | Autenticación real y `AuthService` en el frontend, reemplazando el login contra `json-server`. | 4h | Done |
| — | Setup del proyecto | — | T-03 | Endpoint `/health` (TS04) | Verificación de backend y base de datos operativos, según el contrato diseñado en el Sprint 1 (T-26). | 1h | Done |
| TS03 | Endpoint de pagos con recálculo de saldo | 3 | T-04 | `POST /payments` (total y parcial) | Registra el pago, recalcula el saldo pendiente del `Booking` en una misma transacción y actualiza su estado de pago. | 4h | Done |
| US14 | Registrar estado de pago de un alquiler | 3 | T-05 | Conectar UI de pago total/pendiente | `ReservasPage`/`NuevaReservaPage` conectadas al endpoint real; rechaza montos que excedan el total. | 2h | Done |
| US15 | Registrar pagos parciales | 5 | T-06 | Conectar UI de pago parcial | Formulario de pago parcial mostrando el saldo pendiente recalculado en tiempo real. | 3h | Done |
| US16 | Registrar método de pago | 1 | T-07 | Selector de método de pago | Campo efectivo/Yape/otro persistido junto al `Payment`. | 1h | Done |
| TS08 | Endpoint de carga de comprobante con almacenamiento en la nube | 5 | T-08 | `POST /payments/{id}/comprobante` | Sube la imagen a Supabase Storage y guarda la URL en el `Payment`; rechaza archivos inválidos. | 4h | Done |
| US27 | Adjuntar comprobante de pago | 3 | T-09 | Conectar carga de comprobante | Selector de imagen en el formulario de pago conectado al endpoint real, envío opcional. | 2h | Done |
| US17 | Ver alquileres del día | 2 | T-10 | `GET /panel/alquileres-del-dia` + `PanelPage` | Endpoint y conexión de la tarjeta de alquileres del día, excluyendo cancelados. | 2h | Done |
| US18 | Ver ingreso total del día | 2 | T-11 | `GET /panel/ingreso-del-dia` + tarjeta de ingreso | Suma de pagos reales del día, sin incluir montos aún no pagados. | 2h | Done |
| US19 | Ver pagos pendientes del día | 2 | T-12 | `GET /panel/pendientes-del-dia` + lista de pendientes | Alquileres `PENDIENTE`/`PARCIAL` del día con su saldo, excluyendo los ya pagados. | 2h | Done |
| US20 | Solicitar registro de nueva cuenta de administrador | 3 | T-13 | `POST /users/solicitudes` + pantalla conectada | `RequestAccessPage`/`SolicitudEnviadaPage` conectada; rechaza correos ya registrados sin crear duplicado. | 3h | Done |
| US21 | Autorizar o rechazar solicitudes de acceso | 3 | T-14 | `PATCH /users/solicitudes/{id}/autorizar` y `/rechazar` | Restringido al administrador dueño (`requireOwner`, TS05); rechaza con 403 si quien lo intenta no es el dueño. | 3h | Done |
| TS05 | Endpoints de solicitud y autorización de cuentas | 3 | T-15 | Conectar `SolicitudesAccesoPage` | Listado de solicitudes pendientes (`useSolicitudes`) conectado a los endpoints reales de T-13/T-14. | 2h | Done |
| US26 | Ver administradores activos | 2 | T-16 | `GET /users` (activos) + listado | Listado de administradores activos en `AjustesPage`, sin exponer pendientes ni rechazados. | 2h | Done |
| US34 | Verificar mi correo antes de acceder al sistema | 3 | T-27 | `GET /users/verificar` (TS11) + envío del enlace tras autorización | Genera un token de verificación al autorizar la solicitud (T-14), lo envía por correo, y activa la cuenta solo si el token es válido y vigente. | 3h | Done |
| US22 | Recibir correo de confirmación al registrar un alquiler | 3 | T-17 | Listener de `BookingRegistered` → Resend | Envío de correo de confirmación sin bloquear la respuesta HTTP del registro; no revierte el alquiler si falla (RF24). | 3h | Done |
| TS06 | Listener de correo de confirmación sobre `BookingRegistered` | 3 | T-18 | Prueba end-to-end del correo | Verificación del caso feliz y del caso de fallo del proveedor de correo. | 2h | Pendiente |
| US23 | Recibir correo con el resultado de mi solicitud de acceso | 2 | T-19 | Listener de `AdminAuthorized`/`AdminRejected` → Resend | Correo de autorización o rechazo al solicitante, sin exponer el motivo interno. | 2h | Done |
| US24 | Actualizar mi correo | 2 | T-20 | `PATCH /users/me/correo` | Valida que el nuevo correo no esté en uso; rechaza con 409 si ya existe. | 2h | Done |
| TS07 | Endpoints de ajustes de cuenta (correo y contraseña) | 3 | T-21 | `PATCH /users/me/contrasena` | Valida la contraseña actual antes de aplicar el cambio; invalida sesiones activas en otros dispositivos. | 3h | Done |
| US25 | Cambiar mi contraseña | 2 | T-22 | Conectar `AjustesPage` a correo y contraseña | Formularios de ajustes conectados a T-20/T-21 con manejo de errores (409/401). | 2h | Done |
| US30 | Registrar WhatsApp del cliente con acceso directo | 2 | T-23 | WhatsApp en ficha de cliente | Enlace `wa.me` sobre el campo `phone` ya existente del `Customer`, en `ClientesPage` y `PanelPage`. | 2h | Done |
| — | Conexión frontend-backend | — | T-24 | Apagar `json-server` y conectar la API real | `VITE_API_URL` apunta a la API real (`https://api.moli-voleibol.com`) en `.env.local`; `db.json`/`json-server` quedan solo como fallback de desarrollo local. | 4h | Done |
| — | Pruebas de integración | — | T-25 | QA end-to-end sobre el sistema conectado | Suite BDD (Cucumber) cubre bookings, payments, access requests, maintenance blocks y password reset; quedan escenarios pendientes de estabilizar (fechas hardcodeadas en `bookings.feature` que hoy caen en el pasado). | 4h | En progreso |
| — | Preparación de despliegue | — | T-26 | Despliegue en Render + Supabase | `Dockerfile` y `render.yaml` (`plan: free`) configurados en el backend; variables de entorno de producción apuntando a Supabase; frontend desplegado como Static Site con `VITE_API_URL` real. | 3h | Done |
| TS01 | Endpoint de alquiler con validación de doble reserva | 3 | T-28 | `POST /bookings` con transacción y rechazo por conflicto | Valida solapamiento dentro de una transacción Prisma antes de crear el `Booking`; retorna 409 en conflicto. | 4h | Done |
| US05 | Registrar, editar y cancelar un alquiler | 5 | T-29 | Conectar `ReservasPage`/`NuevaReservaPage` a registro/edición/cancelación | Incluye la reversión automática de pagos al cancelar (`PaymentReversed`). | 4h | Done |
| US06 | Impedir la doble reserva de una cancha | 5 | T-30 | Verificación end-to-end de la invariante de no-doble-reserva | Casos de conflicto en registro y en edición, validados contra TS01. | 3h | Done |
| TS09 | Endpoint de alquiler con creación de cliente embebida | 2 | T-31 | `clienteNuevo` embebido en `POST /bookings` | Crea el `Customer` en la misma transacción si no existe `clienteId`; revierte ambos ante conflicto de horario. | 2h | Done |
| US28 | Registrar un cliente nuevo desde el formulario de alquiler | 3 | T-32 | Conectar creación de cliente embebida en el formulario | Cliente creado queda disponible también en la sección de Clientes. | 2h | Done |
| US04 | Visualizar disponibilidad de canchas | 5 | T-33 | Calendario día/semana/mes conectado | Refleja `Booking` y `ScheduleBlock` reales por franja. | 4h | Done |
| US13 | Ver disponibilidad consolidada de todas las canchas | 3 | T-34 | `GET /courts/disponibilidad` + vista consolidada | Estado de las 5 canchas en una sola respuesta. | 2h | Done |
| US08 | Buscar y filtrar el historial de alquileres | 3 | T-35 | `GET /bookings` con filtros + UI de búsqueda | Filtro por fecha, cancha, cliente y estado. | 2h | Done |
| US11 | Registrar y editar canchas | 3 | T-36 | `POST`/`PATCH /courts` + UI de canchas | Alta y edición con validación de nombre duplicado. | 2h | Done |
| US12 | Configurar precios por cancha | 2 | T-37 | `PATCH /courts/{id}/precio` | Rechaza precio en cero o negativo. | 1h | Done |
| TS10 | Endpoint de carga de fotos de cancha | 3 | T-38 | `POST /courts/{id}/fotos` | Una imagen por llamada, sube a Supabase Storage. | 2h | Done |
| US29 | Adjuntar fotos a una cancha | 3 | T-39 | Conectar carga de fotos en la ficha de cancha | Repite la operación una vez por imagen. | 2h | Done |
| US31 | Registrar y ver el motivo de un bloqueo por mantenimiento | 3 | T-40 | Campo de motivo en `POST /courts/{id}/bloqueos` | Motivo opcional, visible en el calendario. | 2h | Done |
| US09 | Registrar, editar y eliminar clientes | 3 | T-41 | `POST`/`PATCH`/`DELETE /customers` + `ClientesPage` | Conserva `Booking` históricos al eliminar un cliente. | 2h | Done |
| US10 | Consultar historial de un cliente | 2 | T-42 | `GET /customers/{id}/historial` | Lista de `Booking` del cliente, ordenada por fecha. | 1h | Done |
| US32 | Registrar reservas de varias fechas (multi-día o recurrentes) | 5 | T-43 | `POST /bookings/serie` + selector Única/Multidía/Recurrente | Transacción atómica; rollback total si una fecha tiene conflicto. | 5h | Done |
| TS12 | Endpoint de registro de reservas en serie | 5 | T-44 | Modo de pago de la serie (individual/acumulado) | `seriesPaymentMode` distribuye el monto entre las fechas de la serie. | 3h | Done |
| US35 | Bloquear varias fechas por mantenimiento en una sola operación | 3 | T-45 | `POST /courts/{id}/bloqueos/serie` | Rechaza toda la operación si alguna fecha tiene conflicto. | 2h | Done |
| TS13 | Endpoint de bloqueo de mantenimiento en varias fechas | 3 | T-46 | Validación de conflicto por fecha antes de crear cualquier bloqueo | Ninguna fecha se persiste si una sola falla. | 2h | Done |
| US44 | Ver los bloqueos de mantenimiento de una cancha | 2 | T-47 | `GET /courts/{id}/bloqueos` y `/bloqueos/proximos` | Vigentes por fecha y próximos desde hoy. | 1h | Done |
| TS19 | Endpoints de listado de bloqueos de mantenimiento | 2 | T-48 | (incluido en T-47) | — | — | Done |
| US07 | Bloquear y desbloquear una franja por mantenimiento | 3 | T-49 | `DELETE /courts/bloqueos/{blockId}` | Libera la franja de inmediato, emite `ScheduleUnblocked`. | 1h | Done |
| US38 | Ver notificaciones internas de la operación del negocio | 3 | T-50 | `GET /notifications` + `PATCH /:id/leida` + campana de notificaciones | Alertas al registrar `Booking`/serie/bloqueo por otro administrador. | 3h | Done |
| TS15 | Endpoints de notificaciones internas entre administradores | 2 | T-51 | Filtrado por destinatario | Solo notifica a administradores distintos de quien ejecuta la acción. | 1h | Done |
| US37 | Recuperar el acceso olvidando mi contraseña | 3 | T-52 | `POST /auth/olvide-password` + `/restablecer-password` + `ResetPasswordPage` | Token de un solo uso con expiración; no revela si el correo existe. | 3h | Done |
| TS14 | Endpoints de recuperación de contraseña olvidada | 3 | T-53 | Invalidación de sesiones activas tras restablecer | Cobertura BDD (`password_reset.feature`). | 2h | Done |
| US39 | Promover a otro administrador a dueño | 2 | T-54 | `PATCH /users/{id}/promover-dueno` | Restringido al dueño (`requireOwner`). | 1h | Done |
| US40 | Desactivar la cuenta de un administrador | 2 | T-55 | `DELETE /users/{id}` | Invalida sesiones activas del administrador desactivado. | 1h | Done |
| US41 | Actualizar mi perfil y foto de administrador | 3 | T-56 | `PATCH /users/me/perfil` + `POST`/`DELETE /users/{id}/foto` | Elimina la foto anterior de Supabase Storage al reemplazarla. | 2h | Done |
| US42 | Dar de baja mi propia cuenta de administrador | 1 | T-57 | `DELETE /users/me` | Invalida la sesión actual y las demás sesiones activas. | 1h | Done |
| TS16 | Endpoints de promoción, desactivación y perfil propio de administradores | 3 | T-58 | (agrupa T-54 a T-57) | Todas las acciones sobre otras cuentas restringidas al dueño. | — | Done |
| US43 | Eliminar una cancha que ya no está en uso | 2 | T-59 | `DELETE /courts/{id}` | Borrado en cascada de `Booking`/`Payment` asociados (relación de BD). | 1h | Done |
| TS17 | Endpoint de eliminación de cancha con borrado en cascada | 2 | T-60 | Advertencia de consecuencia irreversible en la UI | Pendiente confirmar copy exacto en pantalla. | 1h | Done |
| US46 | Ver los pagos registrados de un alquiler | 1 | T-61 | `GET /payments/{bookingId}` | Incluye pagos reversados. | 1h | Done |
| TS21 | Endpoint de listado de pagos de un alquiler | 1 | T-62 | (mismo endpoint que T-61) | — | — | Done |
| US47 | Ver el comprobante ya adjuntado de un pago | 2 | T-63 | `GET /payments/{bookingId}/comprobante` | URL firmada de 300s; 404 si no hay comprobante. | 1h | Done |
| TS22 | Endpoint de visualización de comprobante con URL firmada | 2 | T-64 | (mismo endpoint que T-63) | — | — | Done |
| US45 | Configurar la cuenta inicial del administrador dueño | 2 | T-65 | `POST /auth/bootstrap-dueno` | Protegido por `SETUP_TOKEN`; bloqueado tras el primer uso (409). | 2h | Done |
| TS20 | Endpoint de configuración inicial de la cuenta dueño | 2 | T-66 | (mismo endpoint que T-65) | — | — | Done |
| US01 | Iniciar sesión de forma segura | 3 | T-67 | (cubierto por T-02) | Login rechaza credenciales inválidas sin exponer datos. | — | Done |
| US02 | Operar con múltiples cuentas de administrador | 2 | T-68 | Verificación de sesiones concurrentes | Dos administradores logueados en paralelo sin invalidarse. | 1h | Done |
| US03 | Proteger la información del negocio sin sesión válida | 2 | T-69 | `requireAuth` aplicado a todos los routers | Verificado en los 8 routers del backend. | 1h | Done |

<br>

**Trabajo del sprint, en el orden real de construcción:**
 
1. **Backend + base de datos:** repositorio de backend con Express + TypeScript + Prisma, migraciones aplicadas contra Supabase, implementación de todos los endpoints y la lógica de dominio: núcleo de reservas y doble reserva, canchas, clientes, pagos (incluyendo comprobantes y reversión al cancelar), reservas y bloqueos en serie, panel, identidad y autorización de administradores (incluyendo recuperación de contraseña, promoción/desactivación y perfil propio), notificaciones internas y por correo.

2. **Conexión frontend-backend:** se apaga `json-server` y el frontend pasa a consumir la API real (cambio de `VITE_API_URL`), ajustando lo que sea necesario para que las pantallas ya construidas funcionen con datos reales en vez de datos de prueba.

3. **Pruebas de integración:** ejecución de los casos de prueba clave sobre el sistema ya conectado de punta a punta, y validación con Carlos.

4. **Preparación de despliegue:** configuración de Render (Static Site + Web Service, plan Free) y Supabase en producción, variables de entorno, y verificación final de PWA instalable en un celular real antes del cierre del sprint.

<br>

### 7.3.3. Development Evidence for Sprint Review

<br>

| Repository | Branch | Commit ID | Commit Message | Committed on (Date) |
|---|---|---|---|---|
| la-canchita-de-carlos-backend | main | `fa81ab5` | feat: setup inicial de Express, Prisma y conexión a Supabase + endpoint de login | 2026-07-20 |
| la-canchita-de-carlos-backend | main | `abcdc9d` | refactor: arquitectura hexagonal por bounded context (domain/model, application, infrastructure, interfaces/rest) | 2026-07-21 |
| la-canchita-de-carlos-backend | main | `09bb442` | fix: agregando entidad payments | 2026-07-21 |
| la-canchita-de-carlos-backend | main | `98224b3` | feat: metodos de pago, bloqueos de mantenimiento, reservas en serie, notificaciones a admins, storage con bucket privado para comprobantes y fotos de perfil/cliente | 2026-07-21 |
| la-canchita-de-carlos-backend | main | `62f8dc7` | Agrega validaciones y normalizacion de datos, tests Cucumber para access requests/mantenimiento/notificaciones, corrige tipos Decimal, elimina seed de Prisma y agrega .env.example | 2026-07-22 |
| la-canchita-de-carlos-backend | main | `03f3f5c` | Completar endpoints backend: editar/desactivar cancha, desactivar admin/cuenta propia, actualizar perfil | 2026-07-22 |
| la-canchita-de-carlos-backend | main | `9e86db7` | feat: horarios operativos, mantenimientos programados, notificaciones y fixes varios | 2026-07-23 |
| la-canchita-de-carlos-backend | main | `415289f` | Agrega flujo de olvide-contraseña, corrige tildes y regenera diagramas de clase | 2026-07-24 |
| la-canchita-de-carlos-backend | main | `22de76a` | Reorganizacion hexagonal por bounded context, limpieza de comentarios, elimina foto de cliente, agrega flujo olvide-contrasena con cobertura BDD, y prepara despliegue en Render (Dockerfile, render.yaml) | 2026-07-24 |
| la-canchita-de-carlos-backend | main | `725864a` | Preparacion para deploy | 2026-07-24 |
| la-canchita-de-carlos-backend | main | `2fd662c` | Elimina el archivo anterior del bucket de Supabase al reemplazar/quitar foto de perfil, foto de cancha o comprobante de pago | 2026-07-24 |
| la-canchita-de-carlos-backend | main | `729e673` | Reduce duracion de sesion (JWT) de 8h a 1h | 2026-07-25 |
| la-canchita-de-carlos-frontend | main | `b4b5e0e` | chore: configuración de Tailwind, PWA, routing, fake API y estructura de carpetas | 2026-07-16 |
| la-canchita-de-carlos-frontend | main | `5429d5a` | Agrega gestión de Canchas, Clientes y Ajustes/Solicitudes de acceso con responsive mobile | 2026-07-18 |
| la-canchita-de-carlos-frontend | main | `b299c0f` | feat: modo oscuro completo + reservas recurrentes/multidía + fixes de UI | 2026-07-18 |
| la-canchita-de-carlos-frontend | main | `4fd37eb` | feat: mantenimientos programados, notificaciones, metodo de pago y fixes de UI | 2026-07-23 |
| la-canchita-de-carlos-frontend | main | `74033b8` | Conecta flujo de olvide-contraseña con el backend y agrega ResetPasswordPage | 2026-07-24 |
| la-canchita-de-carlos-frontend | main | `fd45970` | Muestra usuarios activos en Ajustes de Cuenta (solo owner) | 2026-07-25 |
| la-canchita-de-carlos-frontend | main | `7068251` | Mejoras responsive movil: notificaciones, calendario mes y cards, iconos de clientes, animacion FAB | 2026-07-25 |
| la-canchita-de-carlos-frontend | main | `605bcc6` | Corrige alineacion de ocupacion semanal y espaciado de dias en vista semana del calendario | 2026-07-25 |

<br>

### 7.3.4. Execution Evidence for Sprint Review
 
<br>

![Execution Evidence](assets/sprints/sprint-2/execution/login.png)

![Execution Evidence](assets/sprints/sprint-2/execution/register.png)

![Execution Evidence](assets/sprints/sprint-2/execution/restablecer.png)

![Execution Evidence](assets/sprints/sprint-2/execution/panel.png)

![Execution Evidence](assets/sprints/sprint-2/execution/calendario.png)

![Execution Evidence](assets/sprints/sprint-2/execution/reservas.png)

![Execution Evidence](assets/sprints/sprint-2/execution/reserva.png)

![Execution Evidence](assets/sprints/sprint-2/execution/clientes.png)

![Execution Evidence](assets/sprints/sprint-2/execution/cliente.png)

![Execution Evidence](assets/sprints/sprint-2/execution/canchas.png)

![Execution Evidence](assets/sprints/sprint-2/execution/cancha.png)

![Execution Evidence](assets/sprints/sprint-2/execution/info.png)

![Execution Evidence](assets/sprints/sprint-2/execution/ajustes.png)

![Execution Evidence](assets/sprints/sprint-2/execution/correo1.png)

![Execution Evidence](assets/sprints/sprint-2/execution/correo2.png)

<br>

### 7.3.5. Services Documentation Evidence for Sprint Review
 
Durante el Sprint 2 se implementaron los endpoints reales de la API (Express + Prisma), reemplazando por completo el fake API del Sprint 1. La API quedó organizada en ocho routers por bounded context: `bookings`, `courts`, `customers`, `auth`, `users`, `notifications`, `panel` y `payments`, todos protegidos por `requireAuth` (y `requireOwner` en las rutas exclusivas del administrador dueño).
 
<br>

![Execution Evidence](assets/sprints/sprint-2/execution/correo2.png)
 
<br>

### 7.3.6. Software Deployment Evidence for Sprint Review
 
Despliegue del sistema completo (frontend + backend + base de datos) según el stack definido en 4.6: Render (Static Site) para el frontend, Render (Web Service, **plan Free**) para el backend — con arranque en frío tras inactividad, mitigado con el endpoint `/health` para monitoreo (ver 4.1, Step 3 Hotspots) — y Supabase para base de datos + Storage.
 
<br>

**Deployment Process:**

1. Configurar el repositorio de backend en Render como Web Service (`Dockerfile` + `render.yaml`, `plan: free`, ya en el repo), con variables de entorno (`DATABASE_URL`, `JWT_SECRET`, `SETUP_TOKEN`, `RESEND_API_KEY`, `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, etc.) apuntando a Supabase.

2. Ejecutar las migraciones de Prisma contra la base de datos de producción en Supabase.

3. Configurar el repositorio de frontend en Render como Static Site, con `VITE_API_URL` apuntando al backend ya desplegado (`https://api.moli-voleibol.com`).

4. Verificar que la PWA sea instalable desde un celular real (RNF04) y que el flujo completo funcione de punta a punta contra producción.

<br>

**URL pública:** lacanchitadecarlos.moli-voleibol.com
 
<br>

![Deployment Evidence](assets/sprints/sprint-2/deploy/supabase.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/resend.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/domain.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/backend.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/cloudflare.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/deploy1.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/frontend.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/custom.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/dns.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/final.png)

![Deployment Evidence](assets/sprints/sprint-2/deploy/project.png)

<br>

## 7.4. Definition of Done
 
Una historia se considera terminada (`Done`) cuando cumple todo lo siguiente:
 
- El código implementa todos los escenarios Gherkin definidos en sus criterios de aceptación.

- Pasa revisión manual de la desarrolladora contra el escenario feliz y al menos un escenario de error/borde.

- No rompe ninguna invariante de dominio ya probada (en particular RF06, no doble reserva).

- Está integrada en la rama principal del repositorio correspondiente (frontend o backend) sin errores de build.

- Si expone un endpoint nuevo, fue probado manualmente en Postman con al menos el caso exitoso y un caso de error.

- Si afecta una pantalla, fue verificada visualmente en al menos una resolución móvil real (RNF03).

- No introduce datos de prueba o mocks que queden expuestos en producción.
Un sprint se considera terminado cuando todas sus historias comprometidas cumplen la Definition of Done, o las que no se completaron quedan explícitamente movidas al backlog del sprint siguiente (no se cierran a medias).
 
<br>

---
# Capítulo VIII: Implementación

## 8.1. Configuración del Entorno de Desarrollo

### 8.1.1. Herramientas del Ciclo de Vida del Producto

<br>

**Gestión de Requisitos**

<br>

| Herramienta | Uso |
|---|---|
| ![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white) | Documentación de requisitos funcionales y no funcionales, historias de usuario y backlog. |
| ![Miro](https://img.shields.io/badge/Miro-050038?style=for-the-badge&logo=miro&logoColor=white) | Event Storming y mapeo de bounded contexts. |

<br>

**Diseño de Experiencia y UI/UX**

<br>

| Herramienta | Uso |
|---|---|
| ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white) | Wireframes, mockups y prototipo navegable. |

<br>

**Desarrollo de Software**

<br>

| Herramienta | Uso |
|---|---|
| ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) | Librería de UI del frontend. |
| ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white) | Tipado estático en frontend y backend. |
| ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white) | Bundler y servidor de desarrollo del frontend. |
| ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white) | Estilos utilitarios del frontend. |
| ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) | Runtime del backend. |
| ![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white) | Framework HTTP del backend. |
| ![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white) | ORM y migraciones sobre PostgreSQL. |

<br>

**Pruebas de Software**

<br>

| Herramienta | Uso |
|---|---|
| ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white) | Pruebas manuales de endpoints del backend. |

<br>

**Diseño de Arquitectura y Base de Datos**

<br>

| Herramienta | Uso |
|---|---|
| ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white) | Motor de base de datos relacional. |
| ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white) | Hosting de base de datos y almacenamiento de archivos. |

<br>

**Control de Versiones y Colaboración**

<br>

| Herramienta | Uso |
|---|---|
| ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white) | Control de versiones. |
| ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white) | Repositorios remotos del frontend y backend. |

<br>

**Despliegue de Software**

<br>

| Herramienta | Uso |
|---|---|
| ![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=white) | Hosting del frontend (Static Site) y backend (Web Service, plan Free). |

<br>

**Documentación de Software**

<br>

| Herramienta | Uso |
|---|---|
| ![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white) | Redacción de este documento. |

<br>

### 8.1.2. Configuración del Entorno de Desarrollo Local

<br>

**Sistema operativo:** Windows 11 (desarrollo local)
 
**Prerrequisitos:**
- Node.js (v18 o superior)
- npm
- Git
- Cuenta de Supabase (base de datos + storage)
- Cuenta de Render (despliegue)

<br>

**Pasos de configuración (backend):**

```bash
git clone https://github.com/brianna-salinas/la-canchita-de-carlos-backend.git
cd la-canchita-de-carlos-backend
npm install
cp .env.example .env
# completar DATABASE_URL, DIRECT_URL, JWT_SECRET, RESEND_API_KEY
npx prisma migrate dev
npm run dev
```

<br>

**Pasos de configuración (frontend):**

```bash
git clone https://github.com/brianna-salinas/la-canchita-de-carlos-frontend.git
cd la-canchita-de-carlos-frontend
npm install
cp .env.example .env
# completar VITE_API_URL
npm run dev
```

<br>

## 8.2. Gestión de Código Fuente

<br>

| Repositorio | URL | Descripción |
|---|---|---|
| Frontend | https://github.com/brianna-salinas/la-canchita-de-carlos-frontend.git | React + Vite + TypeScript + Tailwind CSS. |
| Backend | https://github.com/brianna-salinas/la-canchita-de-carlos-backend.git | Express + TypeScript + Prisma + Supabase. |

<br>

**Modelo de ramas (GitFlow simplificado para desarrollo individual):**

<br>

| Rama | Propósito |
|---|---|
| `main` | Código estable, desplegable en cualquier momento. |
| `feature/*` | Una rama por funcionalidad o módulo, integrada a `main` una vez verificada. |

<br>

**Convención de commits (inspirada en Conventional Commits, en español):**

<br>

| Prefijo | Uso |
|---|---|
| `feat:` | Nueva funcionalidad. |
| `fix:` | Corrección de un error. |
| `docs:` | Cambios de documentación. |
| `refactor:` | Cambios internos sin alterar comportamiento. |
| `chore:` | Tareas de mantenimiento (dependencias, configuración). |

<br>

## 8.3. Convenciones de Código

<br>

**General:**
- Nombres de variables y funciones en inglés; textos visibles al usuario en español.
- Indentación de 2 espacios.
- Punto y coma obligatorio en TypeScript.

<br>

**Estructura de carpetas (backend):**

```
src/
  routes/
  services/
  middlewares/
  db.ts
  index.ts
prisma/
  schema.prisma
  prisma.config.ts
```

<br>

**Estructura de carpetas (frontend):**

```
src/
  pages/
  components/
  services/
  hooks/
  types/
```

<br>

**TypeScript:**
- Tipado explícito en las firmas de funciones públicas.
- Se evita `any`; se prefieren tipos generados por Prisma en el backend.

<br>

**React:**
- Componentes funcionales con Hooks.
- Un componente por archivo.

<br>

**Linting:** ESLint + Prettier en ambos repositorios, ejecutado antes de cada commit relevante.

<br>

## 8.4. Configuración de Despliegue

<br>

**Frontend (Render — Static Site):**
- Build Command: `npm run build`
- Publish Directory: `dist`
- Variable de entorno: `VITE_API_URL`

<br>

**Backend (Render — Web Service, plan Free):**
- Build Command: `npm install && npx prisma generate`
- Start Command: `npm run start`
- Health Check Path: `/health` (usado para monitorear el arranque en frío del plan gratuito, no para eliminarlo — ver 4.1, Step 3 Hotspots)
- Variables de entorno: `DATABASE_URL`, `DIRECT_URL`, `JWT_SECRET`, `JWT_EXPIRES_IN`, `SETUP_TOKEN`, `RESEND_API_KEY`, `RESEND_FROM_EMAIL`, `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `SUPABASE_STORAGE_BUCKET`, `FRONTEND_URL`

<br>

**Base de datos (Supabase):**
- PostgreSQL gestionado, con conexión pooled (`DATABASE_URL`) para la aplicación y conexión directa (`DIRECT_URL`) para migraciones.
- Supabase Storage para comprobantes de pago.

<br>

## 8.5. Avance por Sprint

<br>

| Sprint | Estado real de avance |
|---|---|
| Sprint 1 | Completado. Documentación de Capítulos I-IV, diseño (wireframes, mockups, prototipo Figma) y frontend completo en React contra `json-server`, validado navegacionalmente. |
| Sprint 2 | Completado. Backend real construido de punta a punta (reservas y doble reserva, canchas, clientes, pagos, panel, identidad y autorización de administradores, notificaciones internas y por correo, recuperación de contraseña) y frontend conectado a la API real, con el sistema desplegado en Render + Supabase. Quedan dos Work-Items abiertos antes del cierre formal: T-18 (prueba end-to-end del correo de confirmación) y T-25 (estabilizar los escenarios BDD con fechas hardcodeadas que hoy caen en el pasado). |

<br>

---

# Capítulo IX: Pruebas y Validación

## 9.1. Estrategia de Pruebas

Dado que se trata de un desarrollo individual, la estrategia de pruebas se centra en:

- **Pruebas manuales guiadas por Postman** sobre cada endpoint del backend, cubriendo el caso exitoso y al menos un caso de error por endpoint.
- **Pruebas de integración de punta a punta**, verificando el flujo completo desde la interfaz hasta la base de datos, una vez el frontend se conecta a la API real (Sprint 2).
- **Validación con el cliente (Carlos)**, mostrando el sistema desplegado y confirmando que los flujos cubren su operación real.
- **Revisión de invariantes de dominio** identificadas en el Event Storming (4.1), en particular el rechazo de doble reserva (RF06).

<br>

## 9.2. Casos de Prueba Clave

<br>

| # | Caso de Prueba | Precondición | Pasos | Resultado Esperado |
|---|---|---|---|---|
| 1 | Registrar un alquiler sin solapamiento | Cancha y horario disponibles | Completar formulario de reserva y confirmar | Se crea el `Booking`, se emite `BookingRegistered` |
| 2 | Rechazar doble reserva | Ya existe un `Booking` activo en ese horario y cancha | Intentar registrar otro alquiler en el mismo horario | Sistema rechaza con mensaje claro, se emite `DoubleBookingRejected` |
| 3 | Bloquear horario con motivo | Horario disponible | Registrar bloqueo con motivo obligatorio | Se crea `ScheduleBlock`, se emite `ScheduleBlocked` |
| 4 | Registrar pago total | Alquiler con saldo pendiente | Registrar pago por el monto total | Estado de pago pasa a `PAGADO`, saldo en 0 |
| 5 | Registrar pago parcial | Alquiler con saldo pendiente | Registrar pago menor al total | Estado pasa a `PARCIAL`, saldo recalculado |
| 6 | Rechazar pago que excede el saldo | Alquiler con saldo pendiente | Intentar pagar un monto mayor al saldo | Sistema rechaza la operación |
| 7 | Solicitar acceso de administrador | Correo no registrado previamente | Completar formulario de solicitud | Se crea `RegistrationRequestCreated`, solicitud queda pendiente |
| 8 | Rechazar solicitud con correo duplicado | Correo ya registrado | Intentar solicitar acceso con ese correo | Sistema rechaza sin crear duplicado |
| 9 | Autorizar solicitud de acceso | Solicitud pendiente, usuario autenticado es el dueño | Autorizar la solicitud | Se emite `AdminAuthorized`, se envía correo al solicitante |
| 10 | Rechazar autorización por usuario no dueño | Solicitud pendiente, usuario autenticado no es el dueño | Intentar autorizar | Sistema responde 403 |
| 11 | Enviar correo de confirmación sin bloquear el registro | Proveedor de correo (Resend) caído | Registrar un alquiler | El alquiler se registra igual; el envío de correo falla de forma aislada (RF24) |
| 12 | Detectar arranque en frío mediante `/health` | Backend desplegado en Render, plan Free, tras un período de inactividad | Consultar `/health` inmediatamente después de la inactividad | El endpoint permite detectar el estado del servicio; no elimina la latencia del arranque en frío. |

<br>

## 9.3. Validación con el Cliente

La validación con Carlos Maldonado se realiza al cierre de cada sprint, mostrando el sistema en funcionamiento (Sprint 1: navegación y pantallas contra datos de prueba; Sprint 2: sistema completo desplegado con datos reales) y recogiendo su conformidad o los ajustes solicitados antes de continuar.

<br>

---

# Capítulo X: Despliegue

## 10.1. Ambiente de Producción

<br>

| Componente | Proveedor | Detalle |
|---|---|---|
| Frontend | Render (Static Site) | React + Vite, servido como sitio estático. |
| Backend | Render (Web Service, plan Free) | Express + TypeScript, con arranque en frío tras inactividad; mitigado (no eliminado) mediante el endpoint `/health`. |
| Base de datos | Supabase | PostgreSQL gestionado. |
| Almacenamiento | Supabase Storage | Comprobantes de pago y fotos de cancha. |
| Correo transaccional | Resend | Confirmaciones y notificaciones de autorización. |

<br>

## 10.2. Checklist de Despliegue

- [✓] Migraciones de Prisma aplicadas contra la base de datos de producción.
- [✓] Variables de entorno configuradas en Render (frontend y backend).
- [✓] `VITE_API_URL` del frontend apuntando al backend de producción.
- [✓] Endpoint `/health` respondiendo correctamente en producción.
- [✓] PWA instalable verificada en un celular real.
- [✓] Flujo completo (reserva → pago → confirmación por correo) probado de punta a punta en producción.
- [✓] Validación final con Carlos.

<br>

## 10.3. Plan de Rollback

- Mantener la versión anterior desplegada identificada por su commit en `main` antes de cada despliegue nuevo.
- Ante un fallo crítico detectado después del despliegue, revertir el Web Service y el Static Site en Render al commit anterior conocido como estable.
- Si el fallo involucra una migración de base de datos, evaluar si requiere una migración de reversa antes de volver a un commit anterior del backend.
- Comunicar a Carlos cualquier interrupción del servicio y el tiempo estimado de resolución.

<br>

---

# Anexos

<br>

- Repositorio del frontend: https://github.com/brianna-salinas/la-canchita-de-carlos-frontend.git
- Repositorio del backend: https://github.com/brianna-salinas/la-canchita-de-carlos-backend.git
- Prototipo navegable en Figma: https://www.figma.com/site/iprLtSv1JAy2xLH9kklVbt/La-Canchita-de-Carlos?node-id=0-1&t=xrfrClNrYt8S0jPV-1