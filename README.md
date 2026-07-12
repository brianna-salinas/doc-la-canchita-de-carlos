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

<br>

---
 
# Capítulo I: Introducción
 
## 1.1. Perfil del negocio

"La Canchita de Carlos" opera dentro de la Institución Educativa N.° 1278 Mixto La Molina (Jr. Cusco 416, La Molina, Lima), donde Carlos Maldonado administra el alquiler de las canchas deportivas del plantel — vóley, fútbol y básquet, cinco espacios en total — fuera del horario escolar. Este modelo permite aprovechar la infraestructura deportiva del colegio como fuente de ingreso adicional, alquilando las canchas a equipos, grupos e instituciones externas en las tardes, noches y fines de semana.
 
Actualmente, la gestión de las reservas se realiza de forma manual: los horarios se coordinan por llamadas o mensajes, los pagos se registran en cuadernos o notas sueltas (efectivo, Yape), y no existe un sistema centralizado que Carlos y su trabajador puedan consultar en tiempo real. Esto genera dos problemas recurrentes: dobles reservas de una misma cancha en el mismo horario (con el consecuente conflicto frente a los clientes) y falta de visibilidad clara sobre cuánto se ha alquilado, cuánto se ha cobrado y qué pagos quedan pendientes en un día determinado.
 
El sistema busca resolver esto centralizando la gestión de las cinco canchas en una sola herramienta accesible desde el celular o la computadora, exclusiva para Carlos y su trabajador, sin exponer el sistema a los clientes finales (alcance definido en la Propuesta 1).

<br>

## 1.2. Alcance del producto

El presente documento desarrolla la **Propuesta 1 — Uso interno**, aceptada por el cliente sobre la Propuesta 2, en función del plazo real disponible (2 semanas) y el presupuesto acordado. El sistema es de uso exclusivo de Carlos y su trabajador; los clientes finales no acceden a la aplicación ni realizan reservas ni pagos por este medio.

<br>

**Incluido en el alcance:**

- Gestión de usuarios administradores (inicio de sesión seguro, múltiples administradores, control de acceso).

- Gestión de alquileres: calendario de disponibilidad (diario/semanal/mensual), registro/edición/cancelación, bloqueo automático de horarios ocupados, bloqueo manual por mantenimiento, historial con búsqueda y filtros.

- Gestión de clientes: registro, edición, eliminación e historial básico.

- Gestión de las cinco canchas: alta y edición, configuración de precios, vista general de disponibilidad.

- Gestión de pagos: estado (pagado/pendiente), pagos parciales, método de pago — registrados manualmente por el administrador (efectivo, Yape, etc.), sin pasarela de pago integrada.

- Panel principal con alquileres, ingresos y pagos pendientes del día.

- Aplicación PWA instalable, con diseño responsive optimizado para uso desde celular.

<br>

**Explícitamente fuera de alcance en esta fase:**
- Acceso o reservas por parte de clientes finales (celular/tablet/PC de los clientes).

- Pago online con tarjeta o pasarela de pagos.

- Notificaciones automáticas (correo, WhatsApp, recordatorios).

- Reportes exportables en PDF/Excel más allá del panel del día.

Estos puntos corresponden íntegramente a la **Propuesta 2 — Plataforma con clientes** (S/ 2,800 – 3,000, 2 a 3.5 meses), la cual queda documentada como fase de evolución futura del sistema y no forma parte del desarrollo actual. La arquitectura definida en el Capítulo IV se diseña de modo que esta segunda fase sea una extensión y no un rediseño del sistema.

<br>

## 1.3. Objetivos del proyecto

**Objetivo general**

Diseñar e implementar un sistema PWA de gestión de alquiler de canchas para "La Canchita de Carlos", que centralice la administración de alquileres, clientes, canchas y pagos en una sola herramienta de uso interno, eliminando la doble reserva de horarios y dando visibilidad diaria de la operación del negocio.


## 1.4. Usuarios del sistema
 
El sistema tiene un único rol funcional — **Administrador** — asignado a dos personas con el mismo nivel de acceso, sin jerarquía entre ellas dentro de la aplicación:

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
 
## 2.1. Requisitos Funcionales (RF)

Requisitos derivados del alcance definido en 1.2, agrupados por módulo (bounded context), con prioridad asignada según su criticidad para resolver el problema central del negocio: la doble reserva y la falta de visibilidad de ingresos.

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
| RF06 | El sistema debe impedir el registro de un nuevo alquiler si la cancha ya tiene un alquiler activo en el mismo horario (regla central del negocio). | Alta — crítica |
| RF07 | El sistema debe permitir bloquear manualmente un horario de una cancha por motivo de mantenimiento, excluyéndolo de la disponibilidad. | Media |
| RF08 | El sistema debe mantener un historial de alquileres, con filtros por fecha, cancha, cliente y estado. | Media |

<br>

**Módulo: Gestión de clientes**
 
| ID | Descripción | Prioridad |
|---|---|---|
| RF09 | El sistema debe permitir registrar, editar y eliminar clientes (nombre, contacto). | Media |
| RF10 | El sistema debe mostrar el historial básico de alquileres asociado a cada cliente. | Baja |

<br>

**Módulo: Gestión de canchas**
 
| ID | Descripción | Prioridad |
|---|---|---|
| RF11 | El sistema debe permitir dar de alta y editar las 5 canchas (nombre, disciplina: vóley/fútbol/básquet). | Alta |
| RF12 | El sistema debe permitir configurar el precio por cancha, y opcionalmente por franja horaria. | Media |
| RF13 | El sistema debe mostrar una vista general de disponibilidad consolidada de todas las canchas. | Alta |

<br>

**Módulo: Gestión de pagos**
 
| ID | Descripción | Prioridad |
|---|---|---|
| RF14 | El sistema debe permitir registrar el estado de pago de un alquiler (pagado / pendiente). | Alta |
| RF15 | El sistema debe permitir registrar pagos parciales, indicando el monto abonado y el saldo restante. | Media |
| RF16 | El sistema debe permitir registrar el método de pago utilizado (efectivo, Yape, u otro). | Baja |

<br>

**Módulo: Panel principal**
 
| ID | Descripción | Prioridad |
|---|---|---|
| RF17 | El sistema debe mostrar en el panel principal los alquileres registrados para el día actual. | Alta |
| RF18 | El sistema debe calcular y mostrar el ingreso total del día en base a los pagos registrados. | Alta |
| RF19 | El sistema debe mostrar el listado de pagos pendientes del día. | Alta |

<br>

## 2.2. Requisitos No Funcionales (RNF)

Requisitos de calidad del sistema, con criterio medible cuando aplica, alineados a la infraestructura definida en 4.6/4.7 (Vercel, Render, Neon).

<br>

| ID | Categoría | Descripción | Criterio de aceptación |
|---|---|---|---|
| RNF01 | Seguridad | Autenticación de administradores y protección de rutas de datos. | Contraseñas hasheadas con bcrypt; sesión mediante JWT con expiración; todo el tráfico servido por HTTPS. |
| RNF02 | Disponibilidad | El sistema debe estar operativo durante el horario de alquiler del negocio (tardes, noches y fines de semana). | Se acepta latencia de "arranque en frío" del backend (Render free tier) tras inactividad prolongada; no se exige SLA formal en esta fase. |
| RNF03 | Usabilidad | Interfaz optimizada para uso desde celular, principal dispositivo del administrador en campo. | Diseño responsive validado en al menos una resolución móvil real antes del despliegue (ver 9.2). |
| RNF04 | Instalabilidad | La app debe poder instalarse como PWA sin pasar por tienda de aplicaciones. | Manifest + service worker configurados; prompt de instalación funcional en Chrome/Android como mínimo. |
| RNF05 | Rendimiento | Tiempos de respuesta aceptables para el volumen de uso real (2 administradores, decenas de alquileres/día). | Registro de un alquiler y carga del panel del día responden en menos de 3 segundos con backend "caliente". |
| RNF06 | Escalabilidad | La arquitectura no debe requerir rediseño al evolucionar hacia la Propuesta 2. | Los subdominios definidos en 4.2 (Pagos, Notificaciones) deben poder extenderse o activarse sin modificar el subdominio núcleo de Reservas. |
| RNF07 | Mantenibilidad | El código debe organizarse por dominio, no por tipo técnico de archivo. | Estructura de carpetas del backend refleja los bounded contexts (4.2) y la separación hexagonal (4.0). |
| RNF08 | Respaldo de datos | La información no debe depender de un único punto de falla. | Backups automáticos habilitados en el proveedor de base de datos (Neon/Supabase) desde el primer despliegue en producción. |
| RNF09 | Compatibilidad | La PWA debe funcionar en los navegadores/dispositivos reales que usan Carlos y su trabajador. | Verificada en Chrome (Android) y un navegador de escritorio como mínimo. |
 
<br>

## 2.3. Lenguaje Ubicuo (Glosario del Dominio)

Términos consensuados organizados por bounded context, para que el vocabulario del negocio y el vocabulario del código sean el mismo.

<br>

**Subdominio Reservas**
 
| Término | Significado |
|---|---|
| Cancha | Espacio deportivo alquilable del colegio (vóley, fútbol o básquet). El sistema administra 5. |
| Franja horaria | Bloque de tiempo en el que una cancha puede alquilarse (ej. 6:00 pm – 7:00 pm). |
| Alquiler | Reserva confirmada de una cancha, para un cliente, en una fecha y franja horaria específica. |
| Doble reserva | Situación inválida en la que dos alquileres ocupan la misma cancha en la misma franja horaria. El sistema debe impedirla siempre (RF06). |
| Bloqueo por mantenimiento | Franja horaria marcada como no disponible por el administrador, sin estar asociada a un alquiler. |
| Disponibilidad | Estado de una cancha en una franja horaria: libre, alquilada o bloqueada. |

<br>

**Subdominio Pagos**
 
| Término | Significado |
|---|---|
| Pago | Registro de dinero recibido por un alquiler. Puede ser total o parcial. |
| Pago parcial | Pago que cubre solo una parte del monto total del alquiler; el alquiler queda con saldo pendiente. |
| Pendiente | Estado de un alquiler cuyo monto (total o restante) aún no ha sido cobrado. |
| Método de pago | Forma en la que se recibió el dinero (efectivo, Yape, u otro registrado manualmente). |

<br>

**Subdominio Clientes**
 
| Término | Significado |
|---|---|
| Cliente | Persona o grupo externo (equipo, institución) que alquila una o más canchas. No tiene acceso al sistema (ver 1.4). |
| Historial de cliente | Listado de alquileres pasados asociados a un cliente. |

<br>

**Subdominio Identidad y Acceso**
 
| Término | Significado |
|---|---|
| Administrador | Usuario con acceso al sistema: Carlos o su trabajador autorizado. Único rol funcional del sistema. |
| Sesión | Periodo en el que un administrador permanece autenticado tras iniciar sesión. |
 
 
## 2.4. User Stories

>*Las User Stories expresan necesidades reales del negocio de Carlos, no funcionalidades de pantalla. Cada historia describe una capacidad operacional con impacto concreto en la gestión de "La Canchita de Carlos". Los criterios de aceptación siguen la estructura Gherkin (Given/When/Then) y validan **comportamiento del dominio**: estados que cambian, **invariantes que se protegen**, y eventos que se emiten — no lo que muestra la pantalla. Los aggregates raíz (`Alquiler`, `Cancha`, `Cliente`, `Pago`, `Usuario`) y los Domain Events utilizados en estas historias fueron derivados del Event Storming (sección 4.1). Los criterios de aceptación se redactan en tiempo presente y tercera persona, sin referencias a detalles de interfaz.*
<br>
 
### Epics
 
| **ID** | **Título** | **Descripción** | **Historias Relacionadas** |
|---|---|---|---|
| **EP01** | **Identidad y Acceso** | Capacidad de negocio que garantiza que solo Carlos y su trabajador autorizado accedan al sistema, protegiendo la información operativa y financiera del negocio. | US01, US02, US03 |
| **EP02** | **Gestión de Reservas** | Capacidad de negocio central: administrar la disponibilidad de las 5 canchas y garantizar que nunca coexistan dos alquileres para el mismo horario. | US04, US05, US06, US07, US08 |
| **EP03** | **Gestión de Clientes** | Capacidad de negocio que permite mantener un registro de quién alquila, para dar seguimiento comercial básico. | US09, US10 |
| **EP04** | **Gestión de Canchas** | Capacidad de negocio que permite mantener actualizado el inventario de canchas del colegio y sus precios, base para calcular correctamente cada alquiler. | US11, US12, US13 |
| **EP05** | **Gestión de Pagos** | Capacidad de negocio que permite registrar y trazar el dinero cobrado por cada alquiler, incluyendo pagos parciales. | US14, US15, US16 |
| **EP06** | **Panel Operativo del Día** | Capacidad de negocio que da a Carlos visibilidad inmediata de la operación diaria: qué se alquiló, cuánto se cobró y qué falta cobrar. | US17, US18, US19 |
 
<br>

### User Stories
 
| **ID** | **Título** | **Descripción** | **Criterios de Aceptación** | **Epic ID** |
|---|---|---|---|---|
| **EP01 – Identidad y Acceso** |||||
| **US01** | Iniciar sesión de forma segura | Como administrador, quiero iniciar sesión con mis credenciales para acceder únicamente si soy un usuario autorizado del negocio. | **Escenario 1 – Login exitoso:** <br> **Given:** el administrador ingresa credenciales correctas de una cuenta `Usuario` existente <br> **When:** el sistema valida las credenciales <br> **Then:** se emite el evento `SesionIniciada`, se genera un token de sesión y el administrador accede al panel. <br><br> **Escenario 2 – Credenciales inválidas rechazadas:** <br> **Given:** el administrador ingresa una contraseña incorrecta <br> **When:** el sistema valida <br> **Then:** el sistema rechaza el acceso, no se emite `SesionIniciada` y ningún dato del negocio queda expuesto. | EP01 |
| **US02** | Operar con múltiples cuentas de administrador | Como administrador, quiero que exista más de una cuenta activa para que Carlos y su trabajador operen en paralelo sin bloquearse mutuamente. | **Escenario 1 – Sesiones simultáneas válidas:** <br> **Given:** existen dos cuentas `Usuario` activas (Carlos y su trabajador) <br> **When:** ambas inician sesión al mismo tiempo <br> **Then:** ambas sesiones permanecen activas de forma independiente y cada una puede registrar alquileres sin invalidar la sesión del otro. <br><br> **Escenario 2 – Acción de un administrador visible para el otro:** <br> **Given:** el trabajador registra un `Alquiler` <br> **When:** Carlos consulta el calendario desde su propia sesión <br> **Then:** el nuevo `Alquiler` es visible de inmediato, sin necesidad de que Carlos reinicie sesión. | EP01 |
| **US03** | Proteger la información del negocio sin sesión válida | Como administrador, quiero que ningún dato del negocio sea accesible sin sesión iniciada, para proteger información operativa y financiera. | **Escenario 1 – Acceso sin sesión rechazado:** <br> **Given:** no existe una sesión válida <br> **When:** se intenta consultar cualquier `Alquiler`, `Cliente` o `Pago` <br> **Then:** el sistema deniega el acceso y no retorna ningún dato del dominio. <br><br> **Escenario 2 – Sesión cerrada invalida el acceso:** <br> **Given:** un administrador tenía sesión activa <br> **When:** cierra sesión (`SesionCerrada`) <br> **Then:** cualquier intento posterior de consultar datos con ese token es rechazado. | EP01 |
| **EP02 – Gestión de Reservas** |||||
| **US04** | Visualizar disponibilidad de canchas | Como administrador, quiero ver la disponibilidad de las 5 canchas en vista diaria, semanal y mensual, para planificar rápido los alquileres. | **Escenario 1 – Disponibilidad reflejada correctamente:** <br> **Given:** existen `Alquiler` activos y `BloqueoHorario` vigentes sobre distintas canchas <br> **When:** el administrador consulta el calendario para una fecha <br> **Then:** el sistema retorna cada franja como libre, alquilada o bloqueada, reflejando el estado real de los aggregates `Alquiler` y `BloqueoHorario`. <br><br> **Escenario 2 – Cambio de vista sin alterar el dominio:** <br> **Given:** el administrador está viendo la vista diaria <br> **When:** cambia a vista semanal o mensual <br> **Then:** el sistema recalcula la disponibilidad para el nuevo rango sin modificar ningún `Alquiler` o `BloqueoHorario` existente. | EP02 |
| **US05** | Registrar, editar y cancelar un alquiler | Como administrador, quiero registrar, editar y cancelar un alquiler, para que el sistema refleje exactamente lo acordado con el cliente. | **Escenario 1 – Registro exitoso:** <br> **Given:** la cancha y franja horaria solicitadas están libres <br> **When:** el administrador registra el alquiler con cliente, cancha, fecha y horario <br> **Then:** se crea el aggregate `Alquiler` en estado `RESERVADO` y se emite el evento `AlquilerRegistrado`. <br><br> **Escenario 2 – Edición reevaluando disponibilidad:** <br> **Given:** un `Alquiler` existente en estado `RESERVADO` <br> **When:** el administrador cambia su horario a una franja también libre <br> **Then:** el sistema actualiza el `Alquiler` y emite `AlquilerEditado`. <br><br> **Escenario 3 – Cancelación libera la franja:** <br> **Given:** un `Alquiler` en estado `RESERVADO` <br> **When:** el administrador lo cancela <br> **Then:** el `Alquiler` transita a estado `CANCELADO`, se emite `AlquilerCancelado` y la franja queda disponible de inmediato para un nuevo registro. | EP02 |
| **US06** | Impedir la doble reserva de una cancha | Como administrador, quiero que el sistema impida crear un alquiler en un horario ya ocupado, para que nunca ocurra una doble reserva. | **Escenario 1 – Doble reserva rechazada (invariante central):** <br> **Given:** ya existe un `Alquiler` en estado `RESERVADO` para la cancha X en la franja 6:00–7:00 pm <br> **When:** el administrador intenta registrar otro `Alquiler` para la misma cancha y franja <br> **Then:** el sistema rechaza la operación, no se crea un nuevo `Alquiler` y se emite el evento `DobleReservaRechazada` en lugar de `AlquilerRegistrado`. <br><br> **Escenario 2 – Franja liberada permite nueva reserva:** <br> **Given:** el `Alquiler` que ocupaba la franja X fue cancelado (`AlquilerCancelado`) <br> **When:** el administrador registra un nuevo alquiler para esa misma cancha y franja <br> **Then:** el sistema lo acepta y emite `AlquilerRegistrado`, porque la invariante de exclusividad ya no se viola. <br><br> **Escenario 3 – Edición que colisiona con otro alquiler:** <br> **Given:** el `Alquiler` A ocupa la franja X y el `Alquiler` B ocupa la franja Y de la misma cancha <br> **When:** el administrador intenta editar B para moverlo a la franja X <br> **Then:** el sistema rechaza la edición, `B` conserva su horario original y se emite `DobleReservaRechazada`. | EP02 |
| **US07** | Bloquear una franja por mantenimiento | Como administrador, quiero bloquear manualmente una franja de una cancha por mantenimiento, para que no pueda alquilarse mientras no esté disponible. | **Escenario 1 – Bloqueo exitoso:** <br> **Given:** la franja de la cancha X está libre <br> **When:** el administrador la marca como bloqueada por mantenimiento <br> **Then:** se crea un `BloqueoHorario` para esa cancha y franja, se emite `HorarioBloqueado`, y la franja deja de estar disponible para alquileres. <br><br> **Escenario 2 – No se puede bloquear una franja con alquiler activo:** <br> **Given:** la franja de la cancha X ya tiene un `Alquiler` en estado `RESERVADO` <br> **When:** el administrador intenta bloquearla <br> **Then:** el sistema rechaza el bloqueo, no se crea `BloqueoHorario` y el `Alquiler` existente no se ve afectado. | EP02 |
| **US08** | Buscar y filtrar el historial de alquileres | Como administrador, quiero buscar y filtrar el historial de alquileres, para resolver dudas o reclamos de clientes rápidamente. | **Escenario 1 – Filtro con resultados:** <br> **Given:** existen `Alquiler` registrados con distintas fechas, canchas, clientes y estados <br> **When:** el administrador filtra por una combinación de esos criterios <br> **Then:** el sistema retorna únicamente los `Alquiler` que cumplen todos los criterios, sin modificar su estado. <br><br> **Escenario 2 – Filtro sin coincidencias:** <br> **Given:** los criterios seleccionados no corresponden a ningún `Alquiler` registrado <br> **When:** el sistema procesa la búsqueda <br> **Then:** retorna un conjunto vacío sin alterar el historial existente. | EP02 |
| **EP03 – Gestión de Clientes** |||||
| **US09** | Registrar, editar y eliminar clientes | Como administrador, quiero registrar, editar y eliminar clientes, para mantener actualizada la información de contacto del negocio. | **Escenario 1 – Registro exitoso:** <br> **Given:** el administrador ingresa nombre y contacto de un nuevo cliente <br> **When:** confirma el registro <br> **Then:** se crea el aggregate `Cliente` y se emite `ClienteRegistrado`, quedando disponible de inmediato para asociarse a un `Alquiler`. <br><br> **Escenario 2 – Eliminación de cliente con historial:** <br> **Given:** un `Cliente` tiene `Alquiler` asociados en su historial <br> **When:** el administrador intenta eliminarlo <br> **Then:** el sistema conserva los `Alquiler` históricos intactos (referenciando al cliente por su identificador), sin romper la trazabilidad del historial existente. | EP03 |
| **US10** | Consultar historial de un cliente | Como administrador, quiero ver el historial de alquileres de un cliente, para conocer su frecuencia de uso. | **Escenario 1 – Historial con alquileres:** <br> **Given:** un `Cliente` tiene uno o más `Alquiler` asociados <br> **When:** el administrador consulta su ficha <br> **Then:** el sistema retorna la lista de `Alquiler` de ese cliente ordenados por fecha, sin modificar ningún estado. <br><br> **Escenario 2 – Cliente sin alquileres:** <br> **Given:** un `Cliente` fue registrado pero aún no tiene `Alquiler` asociados <br> **When:** el administrador consulta su ficha <br> **Then:** el sistema retorna historial vacío sin fabricar datos. | EP03 |
| **EP04 – Gestión de Canchas** |||||
| **US11** | Registrar y editar canchas | Como administrador, quiero dar de alta y editar las canchas del colegio, para mantener el sistema alineado a la infraestructura real. | **Escenario 1 – Alta exitosa:** <br> **Given:** el administrador ingresa nombre y disciplina de una cancha nueva <br> **When:** confirma el registro <br> **Then:** se crea el aggregate `Cancha` y se emite `CanchaRegistrada`. <br><br> **Escenario 2 – Nombre de cancha duplicado:** <br> **Given:** ya existe una `Cancha` con ese nombre <br> **When:** el administrador intenta registrar otra con el mismo nombre <br> **Then:** el sistema rechaza el registro y la `Cancha` existente no se altera. | EP04 |
| **US12** | Configurar precios por cancha | Como administrador, quiero configurar el precio de cada cancha, para que el sistema calcule montos correctos automáticamente. | **Escenario 1 – Precio actualizado y aplicado:** <br> **Given:** una `Cancha` existente con un precio configurado <br> **When:** el administrador actualiza el precio a un valor válido (mayor a cero) <br> **Then:** se emite `PrecioCanchaActualizado` y todo nuevo `Alquiler` para esa cancha calcula el monto con el precio vigente. <br><br> **Escenario 2 – Precio inválido rechazado:** <br> **Given:** el administrador intenta fijar un precio en cero o negativo <br> **When:** confirma <br> **Then:** el sistema rechaza el cambio y la `Cancha` conserva su precio anterior. | EP04 |
| **US13** | Ver disponibilidad consolidada de todas las canchas | Como administrador, quiero ver la disponibilidad consolidada de todas las canchas, para decidir rápido qué ofrecer a un cliente que llama. | **Escenario 1 – Vista consolidada correcta:** <br> **Given:** las 5 canchas tienen distintas combinaciones de `Alquiler` y `BloqueoHorario` para una fecha <br> **When:** el administrador consulta la vista consolidada <br> **Then:** el sistema retorna, en una sola respuesta, el estado de disponibilidad de las 5 canchas para esa fecha. | EP04 |
| **EP05 – Gestión de Pagos** |||||
| **US14** | Registrar estado de pago de un alquiler | Como administrador, quiero marcar un alquiler como pagado o pendiente, para saber qué dinero falta cobrar. | **Escenario 1 – Pago total registrado:** <br> **Given:** un `Alquiler` con estado de pago `PENDIENTE` <br> **When:** el administrador registra un `Pago` por el monto total <br> **Then:** se emite `PagoRegistrado`, el `Alquiler` transita su estado de pago a `PAGADO` y el saldo pendiente queda en cero. <br><br> **Escenario 2 – Monto excede el total del alquiler:** <br> **Given:** un `Alquiler` tiene un monto total definido <br> **When:** el administrador intenta registrar un `Pago` mayor a ese total <br> **Then:** el sistema rechaza el registro, protegiendo la invariante de que el pago nunca puede exceder el total adeudado. | EP05 |
| **US15** | Registrar pagos parciales | Como administrador, quiero registrar pagos parciales, para llevar control cuando el cliente abona por partes. | **Escenario 1 – Pago parcial con saldo recalculado:** <br> **Given:** un `Alquiler` con estado de pago `PENDIENTE` y monto total S/ 100 <br> **When:** el administrador registra un `Pago` parcial de S/ 40 <br> **Then:** se emite `PagoParcialRegistrado`, el `Alquiler` transita a estado de pago `PARCIAL` y el saldo pendiente queda en S/ 60. <br><br> **Escenario 2 – Suma de parciales completa el pago:** <br> **Given:** un `Alquiler` en estado `PARCIAL` con saldo pendiente de S/ 60 <br> **When:** el administrador registra un nuevo `Pago` de S/ 60 <br> **Then:** el `Alquiler` transita automáticamente a estado `PAGADO` y el saldo pendiente queda en cero. | EP05 |
| **US16** | Registrar método de pago | Como administrador, quiero registrar el método de pago usado, para tener trazabilidad de cómo se cobró cada alquiler. | **Escenario 1 – Método de pago asociado al registro:** <br> **Given:** el administrador registra un `Pago` (total o parcial) <br> **When:** selecciona el método (efectivo, Yape u otro) <br> **Then:** el `Pago` queda persistido con el método indicado, disponible en el historial del `Alquiler`. | EP05 |
| **EP06 – Panel Operativo del Día** |||||
| **US17** | Ver alquileres del día | Como administrador, quiero ver los alquileres del día al iniciar sesión, para saber de un vistazo qué toca hoy. | **Escenario 1 – Panel refleja alquileres activos del día:** <br> **Given:** existen `Alquiler` en estado `RESERVADO` para la fecha actual <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna esos `Alquiler`, excluyendo los que estén en estado `CANCELADO`. | EP06 |
| **US18** | Ver ingreso total del día | Como administrador, quiero ver el ingreso total del día, para llevar control diario sin sacar cuentas manualmente. | **Escenario 1 – Ingreso calculado desde pagos reales:** <br> **Given:** existen uno o más `Pago` (totales y/o parciales) registrados en la fecha actual <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna la suma exacta de esos `Pago`, sin incluir montos de alquileres aún no pagados. | EP06 |
| **US19** | Ver pagos pendientes del día | Como administrador, quiero ver los pagos pendientes del día, para hacer seguimiento a los clientes que aún deben. | **Escenario 1 – Pendientes correctamente identificados:** <br> **Given:** existen `Alquiler` del día con estado de pago `PENDIENTE` o `PARCIAL` <br> **When:** el administrador consulta el panel <br> **Then:** el sistema retorna esos `Alquiler` junto con su saldo pendiente, excluyendo los que ya están en estado `PAGADO`. | EP06 |
 
<br>

### Technical Stories
 
| **ID** | **Título** | **Descripción** | **Criterios de Aceptación** | **Epic ID** |
|---|---|---|---|---|
| **TS01** | Endpoint de registro de alquiler con validación de doble reserva | Como Developer, quiero implementar el endpoint de registro de `Alquiler` en Express validando la invariante de exclusividad de horario a nivel de transacción de base de datos. | **Escenario 1 – Registro exitoso (201):** <br> **Given:** POST `/api/alquileres` con cancha y franja libres <br> **When:** el servidor procesa dentro de una transacción <br> **Then:** crea el `Alquiler`, emite `AlquilerRegistrado` y retorna 201. <br><br> **Escenario 2 – Conflicto de horario (409):** <br> **Given:** la franja solicitada ya está ocupada por otro `Alquiler` activo <br> **When:** el servidor evalúa el constraint único de cancha+franja+estado <br> **Then:** retorna 409, no persiste el nuevo registro y responde con el `Alquiler` en conflicto. | EP02 |
| **TS02** | Endpoint de login y emisión de JWT | Como Developer, quiero implementar el endpoint de autenticación en Express para emitir un JWT a los administradores válidos. | **Escenario 1 – Login exitoso (200):** <br> **Given:** POST `/api/auth/login` con credenciales válidas de un `Usuario` <br> **When:** el servidor valida el hash de la contraseña <br> **Then:** retorna 200 con JWT y expiración. <br><br> **Escenario 2 – Credenciales inválidas (401):** <br> **Given:** contraseña incorrecta <br> **When:** el servidor valida <br> **Then:** retorna 401 sin emitir token. | EP01 |
| **TS03** | Endpoint de registro de pagos con recálculo de saldo | Como Developer, quiero implementar el endpoint de registro de `Pago` en Express, recalculando el saldo pendiente del `Alquiler` asociado en una misma transacción. | **Escenario 1 – Pago parcial registrado (201):** <br> **Given:** POST `/api/pagos` con monto menor al saldo pendiente del `Alquiler` <br> **When:** el servidor procesa <br> **Then:** crea el `Pago`, actualiza el estado del `Alquiler` a `PARCIAL`, emite `PagoParcialRegistrado` y retorna 201 con el nuevo saldo. <br><br> **Escenario 2 – Monto excede saldo pendiente (400):** <br> **Given:** el monto enviado es mayor al saldo pendiente <br> **When:** el servidor valida <br> **Then:** retorna 400 y no persiste el pago. | EP05 |
| **TS04** | Endpoint de health check | Como Developer, quiero implementar un endpoint `/health` en Express para verificar que el backend y la conexión a base de datos estén operativos, dado que Render suspende el servicio por inactividad. | **Escenario 1 – Sistema operativo (200):** <br> **Given:** el backend está corriendo y la conexión a PostgreSQL responde <br> **When:** se consulta GET `/health` <br> **Then:** retorna 200 con estado `ok`. <br><br> **Escenario 2 – Base de datos no disponible (503):** <br> **Given:** la conexión a PostgreSQL falla <br> **When:** se consulta GET `/health` <br> **Then:** retorna 503, permitiendo detectar el problema antes de que Carlos reporte que "la app no funciona". | EP02 |


 
## 2.5. Product Backlog

>*El Product Backlog consolida las funcionalidades priorizadas por valor operacional para el negocio de "La Canchita de Carlos". Las historias están estimadas en Story Points (escala Fibonacci) y ordenadas por impacto operacional y dependencias funcionales: el subdominio núcleo (Reservas) precede a los subdominios de soporte (Clientes, Canchas, Pagos, Panel), porque ahí se concentra el riesgo de negocio más alto — la doble reserva. Las Technical Stories se listan al final para no contaminar la priorización por valor de negocio.*
 
**Total de Story Points: 65 | Total de historias: 23 (19 User Stories + 4 Technical Stories)**

<br>
 
| **N°** | **Story ID** | **Épica** | **Título** | **Descripción** | **Story Points** |
|---|---|---|---|---|---|
| 1 | **US01** | EP01 – Identidad y Acceso | Iniciar sesión de forma segura | Como administrador, quiero iniciar sesión con mis credenciales para acceder únicamente si soy un usuario autorizado del negocio. | 3 |
| 2 | **US02** | EP01 – Identidad y Acceso | Operar con múltiples cuentas de administrador | Como administrador, quiero que exista más de una cuenta activa para que Carlos y su trabajador operen en paralelo sin bloquearse mutuamente. | 2 |
| 3 | **US03** | EP01 – Identidad y Acceso | Proteger la información del negocio sin sesión válida | Como administrador, quiero que ningún dato del negocio sea accesible sin sesión iniciada, para proteger información operativa y financiera. | 2 |
| 4 | **US04** | EP02 – Gestión de Reservas | Visualizar disponibilidad de canchas | Como administrador, quiero ver la disponibilidad de las 5 canchas en vista diaria, semanal y mensual, para planificar rápido los alquileres. | 5 |
| 5 | **US05** | EP02 – Gestión de Reservas | Registrar, editar y cancelar un alquiler | Como administrador, quiero registrar, editar y cancelar un alquiler, para que el sistema refleje exactamente lo acordado con el cliente. | 5 |
| 6 | **US06** | EP02 – Gestión de Reservas | Impedir la doble reserva de una cancha | Como administrador, quiero que el sistema impida crear un alquiler en un horario ya ocupado, para que nunca ocurra una doble reserva. | 5 |
| 7 | **US07** | EP02 – Gestión de Reservas | Bloquear una franja por mantenimiento | Como administrador, quiero bloquear manualmente una franja de una cancha por mantenimiento, para que no pueda alquilarse mientras no esté disponible. | 3 |
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
| 20 | **TS01** | EP02 – Gestión de Reservas | Endpoint de alquiler con validación de conflicto | Como Developer, quiero implementar el endpoint de registro de `Alquiler` en Express validando la invariante de exclusividad de horario a nivel de transacción de base de datos. | 3 |
| 21 | **TS02** | EP01 – Identidad y Acceso | Endpoint de login y emisión de JWT | Como Developer, quiero implementar el endpoint de autenticación en Express para emitir un JWT a los administradores válidos. | 2 |
| 22 | **TS03** | EP05 – Gestión de Pagos | Endpoint de pagos con recálculo de saldo | Como Developer, quiero implementar el endpoint de registro de `Pago` en Express, recalculando el saldo pendiente del `Alquiler` asociado en una misma transacción. | 3 |
| 23 | **TS04** | EP02 – Gestión de Reservas | Endpoint de health check | Como Developer, quiero implementar un endpoint `/health` en Express para verificar que el backend y la base de datos estén operativos, dado que Render suspende el servicio por inactividad. | 1 |
 
<br>

<div align="center">

**Herramienta utilizada:** `Trello`

**URL del Product Backlog:** *(pendiente — se agrega el link al tablero una vez creado)*
 
</div>

 
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
 
