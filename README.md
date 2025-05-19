# :desktop_computer: Reparacion de Equipos - Subsistema de Gestión de Materiales

> _Sistema de gestión de materiales para el servicio técnico de reparaciones informáticas._

---

## :bookmark_tabs: Índice

- [:wrench: Introducción](#wrench-introducción)
- [:package: Funcionalidades del Subsistema](#package-funcionalidades-del-subsistema)
  - [:card_index_dividers: Registro de clientes](#card_index_dividers-registro-de-clientes)
  - [:books: Historial de reparaciones por cliente](#inbox_tray-historial-de-reparaciones-por-clientes)
  - [:receipt: Presupuesto personalizados](#receipt-presupuestos-personalizados)
  - [:truck: Envio notificaciones](#hammer_and_wrench-envio-notificaciones)
  - [:jigsaw: Clasificacion clientes](#clock4-clasificacion-clientes)
- [:bar_chart: Estructura del Código Java](#bar_chart-estructura-del-código-java)
- [:framed_picture: Galería de Imágenes](#framed_picture-galería-de-imágenes)
- [:warning: Notificaciones y Alertas](#warning-notificaciones-y-alertas)
- [:busts_in_silhouette: Integrantes del Grupo](#busts_in_silhouette-integrantes-del-grupo)

## :wrench: Introducción

El Subsistema de Gestión de Usuarios del Servicio es una parte esencial del sistema de reparaciones informáticas. Este módulo permite:

- :memo: Registrar y mantener actualizada la información de clientes, tanto particulares como instituciones.
- :open_file_folder: Consultar el historial de reparaciones asociadas a cada cliente.
- :receipt: Generar presupuestos personalizados según los servicios solicitados.
- :incoming_envelope: Enviar notificaciones automáticas sobre el estado y coste de las reparaciones.
- :jigsaw: Clasificar a los clientes según criterios como frecuencia de uso, tipo de reparaciones o volumen de servicios.

> :bulb: Este subsistema se integra con los módulos de reparaciones, materiales e informes para ofrecer una gestión completa del servicio técnico.

---

## :package: Funcionalidades del Subsistema

### :card_index_dividers: Registro de materiales y repuestos

Permite agregar nuevos ítems al inventario, incluyendo:

- Nombre del material
- Descripción
- Proveedor
- Precio unitario
- Cantidad

---

### :inbox_tray: Gestión de stock

- Control de entradas y salidas.
- Visualización de stock actual.
- Alerta de **stock bajo** cuando la cantidad llega al mínimo.
- Recuento automatizado.

---

### :receipt: Orden de compras

- Generación automática de pedidos a proveedores.
- Historial completo de órdenes emitidas.
- Asociaciones con proveedores registrados.

---

### :hammer_and_wrench: Asignación de materiales

- Los materiales pueden asignarse a reparaciones específicas.
- Se registra cantidad usada, fecha y técnico responsable.

---

### :clock4: Historial de materiales

- Informes por período, reparación o cliente.
- Consulta del uso y coste acumulado por reparación.

---

## :bar_chart: Estructura del Código Java

```java
public class Material {
    private String nombre;
    private int stock;
    private String proveedor;
    private double precio;

    public Material(String nombre, int stock, String proveedor, double precio) {
        this.nombre = nombre;
        this.stock = stock;
        this.proveedor = proveedor;
        this.precio = precio;
    }

    public void actualizarStock(int cantidad) {
        this.stock += cantidad;
    }

    public boolean esStockBajo() {
        return this.stock < 5;
    }

    // Getters y Setters...
}
```

---



## :warning: Notificaciones y Alertas

> :white_check_mark: **NOTIFICACIÓN**: El nuevo repuesto *Memoria RAM 8GB* ha sido registrado correctamente.

> :warning: **ADVERTENCIA**: El stock de *Disco SSD 500GB* está por debajo del mínimo.

> :x: **ERROR**: No se ha podido actualizar el stock debido a un fallo de conexión con la base de datos.

---

## :busts_in_silhouette: Integrantes del Grupo

Este proyecto ha sido desarrollado por estudiantes del **1º DAW - IES Font de Sant Lluís**:

- :bust_in_silhouette: Manuel Rubio
- :bust_in_silhouette: Irma
- :bust_in_silhouette: Ruben
- :bust_in_silhouette: Alejandro

| Nombre     | Rol   | Subsistema             |
|------------|-------|------------------------|
| Manu       | Scrum | Gestión de materiales  |
| Ruben      | Portavoz    | Gestión de reparaciones|
| Alejandro  | Secretario    | Gestión de clientes    |
| Irma       | Portavoz    | Gestión de informes    |

---

:link: [Volver al índice](#bookmark_tabs-índice)

[Repositorio del proyecto principal](https://github.com/RubenSanchezAng/Reparacion-de-ordenadores "Repositorio del proyecto principal")
