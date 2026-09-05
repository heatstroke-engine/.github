# HeatStroke Engine

**HeatStroke** es un game engine construido desde cero cuyo objetivo es explorar y aplicar principios de **Data-Oriented Design (DOD)** en un motor de videojuegos moderno, con una arquitectura basada en un **ECS (Entity Component System) de arquetipos** y un **sistema de trabajos (job system) multihilo**.

## Objetivo

El propósito de esta organización es centralizar el desarrollo de HeatStroke y sus distintos subsistemas, manteniendo cada componente en repositorios independientes pero interconectados bajo una misma visión: un motor rápido, escalable y orientado a datos, inspirado en arquitecturas como **Unity DOTS**.

## Filosofía del proyecto

El desarrollo de HeatStroke se apoya en principios consolidados de la industria y la comunidad de Data-Oriented Design:

- **Diseño orientado a datos** por encima del diseño orientado a objetos clásico, priorizando el layout de memoria y el rendimiento en caché.
- **Arquitectura de arquetipos**, donde las entidades con la misma combinación de componentes se agrupan en *chunks* contiguos en memoria (layout SoA), permitiendo iteraciones extremadamente rápidas.
- **Paralelismo real**, mediante un *work-stealing thread pool* y un grafo de dependencias que permite paralelizar sistemas de forma automática y segura.
- **Diseño evaluado empíricamente**, comparando el rendimiento del ECS de arquetipos frente a otras aproximaciones (como los sparse sets) mediante benchmarking riguroso.

## Estructura de la organización

Cada repositorio de esta organización cubre una capa o subsistema concreto del motor:

| Repositorio | Descripción |
|---|---|
| `HeatStroke` *(próximamente)* | Repositorio principal que integra todos los subsistemas del motor. |
| ECS de arquetipos | Núcleo de ECS con gestión de entidades, almacenamiento por arquetipos/chunks y sistema de queries. |
| Job System *(futuro)* | Sistema de trabajos multihilo con work-stealing y grafo de dependencias para paralelizar sistemas automáticamente. |

*(Esta tabla se irá actualizando a medida que se añadan nuevos repositorios al motor.)*

## Referencias e inspiración

El desarrollo de HeatStroke está informado por trabajo previo, tanto académico como de la industria, en el campo del Data-Oriented Design y los ECS de arquetipos:

- Mike Acton — *Data-Oriented Design and C++* (CppCon 2014)
- Richard Fabian — *Data-Oriented Design* (libro)
- Scott Bilas — *A Data-Driven Game Object System* (GDC 2002)
- Adam Martin — serie de artículos sobre Entity Systems
- Sander Mertens — artículos sobre arquitecturas ECS de arquetipos y el proyecto [flecs](https://github.com/SanderMertens/flecs)

También se toman como referencia implementaciones reales como **flecs**, **Bevy ECS** y **Unity Entities (DOTS)**, así como comparativas frente a motores de sparse set como **EnTT**.

## Estado del proyecto

HeatStroke se encuentra en desarrollo activo. Actualmente el foco está en el núcleo del ECS (gestión de entidades, almacenamiento por arquetipos y sistema de queries), como base sobre la que se construirá el resto del motor: comandos diferidos, concurrencia y el job system.

---

*Este README se irá actualizando a medida que el proyecto avance y se incorporen nuevos repositorios.*
