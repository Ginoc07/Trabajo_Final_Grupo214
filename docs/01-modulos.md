# Listado de Módulos Funcionales

**Sistema de Gestión de Inventario — Cadena de Almacenes | Grupo 214**

Prioridad: **Alta** (parte del MVP), **Media** (fase posterior al MVP, dentro del alcance del proyecto), **Baja** (deseable / a futuro).

| # | Módulo | Descripción | Prioridad |
|---|---|---|---|
| 1 | **Autenticación y Autorización** | Login de usuarios, generación de token de sesión (JWT), control de acceso según rol (`ADMIN_CENTRAL`, `ENCARGADO_SUCURSAL`). Base para restringir todos los demás módulos. | **Alta** |
| 2 | **Gestión de Usuarios** | ABM de usuarios del sistema, asignación de rol y de sucursal. Solo accesible por el administrador central. | **Alta** |
| 3 | **Gestión de Categorías** | ABM de categorías de producto y definición de los atributos variables esperados por cada una (ej. vencimiento para perecederos). | **Alta** |
| 4 | **Gestión de Productos** | ABM de productos: nombre, categoría, unidad de medida, precio, condición de perecedero y atributos variables según categoría. | **Alta** |
| 5 | **Gestión de Sucursales** | ABM de sucursales (nombre, dirección, responsable asignado). | **Alta** |
| 6 | **Control de Stock por Sucursal** | Consulta del stock actual por producto y sucursal, configuración del stock mínimo y de la fecha de vencimiento cuando corresponde. | **Alta** |
| 7 | **Registro de Movimientos de Stock** | Registro de entradas (compra, transferencia, devolución) y salidas (venta, transferencia, merma, vencimiento) de mercadería, con actualización automática del stock y trazabilidad completa (usuario, fecha, motivo). | **Alta** |
| 8 | **Motor de Alertas de Stock Mínimo** | Generación automática de una alerta cuando, tras un movimiento de salida, el stock de un producto en una sucursal llega o cae por debajo del mínimo configurado. | **Alta** |
| 9 | **Notificaciones por Email (Brevo)** | Envío de notificaciones automáticas ante alertas de stock mínimo, vencimiento próximo o necesidad de aprobación de montos, integrando la API externa de Brevo. | **Media** |
| 10 | **Alertas de Vencimiento** | Generación de alertas preventivas cuando faltan N días (parámetro configurable) para el vencimiento de un producto perecedero. | **Media** |
| 11 | **Gestión de Proveedores** | ABM de proveedores de la cadena (datos de contacto, CUIT, estado). | **Media** |
| 12 | **Órdenes de Compra** | Registro de órdenes de compra a proveedores, con detalle de ítems, cálculo de monto total y circuito de aprobación cuando el monto supera un umbral configurado. | **Media** |
| 13 | **Reportes y Análisis** | Reportes consolidados de stock, movimientos y vencimientos entre todas las sucursales, pensados para la toma de decisiones del administrador central. | **Media** |
| 14 | **Panel de Alertas / Bandeja de Notificaciones** | Vista centralizada donde el usuario ve las alertas activas relevantes a su rol/sucursal y su estado de resolución. | **Baja** |
| 15 | **Rol Proveedor (a futuro)** | Posible incorporación de un portal para que el proveedor participe directamente en la gestión de compras. Explícitamente fuera del alcance del MVP. | **Baja / Futuro** |

---

## Relación módulos ↔ requerimientos funcionales

| Módulo | Requerimientos funcionales asociados (README) |
|---|---|
| Autenticación y Autorización | RF-14 |
| Gestión de Usuarios | RF-14 |
| Gestión de Categorías | RF-02 |
| Gestión de Productos | RF-01 |
| Gestión de Sucursales | RF-03 |
| Control de Stock por Sucursal | RF-06, RF-07, RF-10 |
| Registro de Movimientos de Stock | RF-04, RF-05 |
| Motor de Alertas de Stock Mínimo | RF-08 |
| Notificaciones por Email (Brevo) | RF-09 |
| Alertas de Vencimiento | RF-09, RF-10 |
| Gestión de Proveedores | RF-11 |
| Órdenes de Compra | RF-12 |
| Reportes y Análisis | RF-13 |

## Criterio de priorización

Los módulos marcados **Alta** conforman el **MVP** descripto en el README del proyecto (alta y gestión de productos, sucursales, stock, movimientos, stock mínimo y alertas). Los módulos **Media** son funcionalidades complementarias previstas explícitamente en el alcance del proyecto (proveedores, compras, notificaciones por email, reportes) y se implementan en fases posteriores según el *Plan de integración*. Los módulos **Baja/Futuro** no forman parte del compromiso de entrega actual.
