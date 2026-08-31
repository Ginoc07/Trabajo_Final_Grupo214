# Trabajo Final Integrador

## Grupo 214

### Integrantes
- Agustina Aguilera
- Akier Aguirrezabala
- Gino Canevaro

---

## Sistema de Gestión de Inventario Para Cadena de Almacenes

### Descripción

Sistema de gestión de inventario para una pequeña cadena de almacenes que recientemente incorporó una tercera sucursal.

El crecimiento del negocio genera la necesidad de contar con una herramienta que permita centralizar la información de las distintas sucursales, mejorar el control de la mercadería y disponer de información útil para el análisis y la toma de decisiones.

### Problema

Con el crecimiento de la cadena, la gestión del inventario se vuelve más compleja. El control poco centralizado puede generar faltantes, exceso de stock, pérdidas por vencimiento y dificultades para planificar compras y analizar el comportamiento de los productos.

**Impacto estimado:** se estima que la falta de visibilidad centralizada entre sucursales genera aproximadamente entre un 10% y 15% de pérdidas mensuales por vencimientos no detectados a tiempo y quiebres de stock, además de horas de trabajo administrativo destinadas a conciliar información entre sucursales de forma manual.

### Actores y roles

- **Administrador central:** gestiona productos, categorías, sucursales y proveedores; accede a reportes consolidados de toda la cadena para la toma de decisiones.
- **Encargado de sucursal:** registra entradas y salidas de mercadería en su sucursal, consulta el stock local y recibe alertas de stock mínimo.
- **(Rol a futuro) Proveedor:** podría integrarse en una etapa posterior para la gestión de compras, actualmente fuera del alcance del MVP.

### Objetivo

Desarrollar un sistema que permita mejorar la gestión del inventario de las distintas sucursales y facilitar el acceso a información confiable para la gestión y el análisis del negocio.

---

## Funcionalidades previstas

Entre las principales funcionalidades que se contemplan inicialmente se encuentran:

- Gestión de productos y categorías.
- Gestión de sucursales.
- Control de stock por sucursal.
- Registro de entradas y salidas de mercadería.
- Gestión de proveedores y compras.
- Alertas de stock mínimo y vencimientos.
- Reportes y análisis de información del negocio.

El alcance y las funcionalidades podrán ajustarse durante el desarrollo en función de las necesidades del proyecto y las decisiones tomadas por el equipo.

---

## MVP

La primera versión del sistema contemplará:

- Alta y gestión de productos.
- Gestión de sucursales.
- Control de stock por sucursal.
- Registro de entradas y salidas de mercadería.
- Configuración de stock mínimo.
- Alerta cuando el stock alcance el mínimo establecido.

---

## Stack tecnológico

**Frontend:** JavaScript
Es el lenguaje nativo para aplicaciones web, ya trabajado por el equipo durante la carrera, lo que permite mayor velocidad de desarrollo y menor curva de aprendizaje en esta etapa del proyecto.

**Backend:** Java + Spring Boot
Spring Boot es un framework maduro y sólido para aplicaciones empresariales con lógica de negocio compleja, como el control de stock entre múltiples sucursales, y ofrece un sistema de tipado y seguridad adecuado para este tipo de sistema. Es también una tecnología ya vista en la carrera.

**Base de datos:** MongoDB
Se eligió una base de datos no relacional por la flexibilidad de esquema que ofrece: permite adaptar la estructura de los documentos de producto a atributos variables según la categoría (por ejemplo, productos perecederos con fecha de vencimiento frente a productos que no la requieren) sin necesidad de modificar un esquema rígido a medida que el sistema crezca.

**Control de versiones:** Git + GitHub
Estándar de la industria para trabajo colaborativo en equipo, cumpliendo además con el requisito de repositorio único centralizado exigido por la cátedra.

---

## Repositorio

[https://github.com/Ginoc07/Trabajo_Final_Grupo214](https://github.com/Ginoc07/Trabajo_Final_Grupo214)

## Instalación

Se completará durante el desarrollo del proyecto.

## Despliegue

Se definirá durante el desarrollo del proyecto.
