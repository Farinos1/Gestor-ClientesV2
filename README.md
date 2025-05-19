# :desktop_computer: Reparacion de Equipos - Subsistema de Gestión de Materiales

> _Sistema de gestión de materiales para el servicio técnico de reparaciones informáticas._

---

## :bookmark_tabs: Índice

- [:wrench: Introducción](#wrench-introducción)
- [:package: Funcionalidades del Subsistema](#package-funcionalidades-del-subsistema)
  - [:card_index_dividers: Registro de clientes](#card_index_dividers-registro-de-clientes)
  - [:books: Historial de reparaciones por cliente](#books-historial-de-reparaciones-por-clientes)
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

### :card_index_dividers: Registro de clientes

Permite agregar nuevos registros de clientes al sistema, incluyendo:


- Nombre del cliente o institución
- Descripción completa
- Información de contacto (teléfono, correo electrónico)
- Tipo de cliente: particular o institucional

---

### :books: Historial de reparaciones por clientes

- Generación de reportes: Permite crear un historial completo de las reparaciones realizadas a cada cliente.
- Asociaciones con clientes: Registra que reparaciones se han realizado para cada cliente e institución.
- Detalles de reparaciones: Fecha, tipo de reparación, materiales utilizados y costos.

---

### :receipt: Presupuesto personalizados

- Presupuestos automáticos: El sistema genera presupuestos personalizados basados en los trabajos solicitados por el cliente.
- Costos: Muestra el costo de mano de obra, materiales y otros gastos asociados.
- Envío de presupuestos: Permite enviar presupuestos por correo o a través del sistema al cliente.

---

### :truck: Envio notificaciones

- Estado de reparación: Notificaciones automáticas sobre el avance de la reparación de un equipo.
- Coste final: Al finalizar la reparación, el sistema envía una notificación con el costo total.
- Tiempo estimado de entrega: Envía alertas al cliente cuando la reparación se acerca a la fecha de entrega o si se produce algún retraso.

---

### :jigsaw: Clasificacion clientes

- Clasifica a los clientes en grupos según  frecuencia de uso, tipo de servicio solicitado o cantidad de reparaciones.
- Análisis de clientes frecuentes: Permite identificar clientes recurrentes o los cuales con mayor cantidad de servicios.

---

## :bar_chart: Estructura del Código Java

```java
/**
 * <h2>Clase Usuario</h2>
 * <p>
 * Representa un usuario base con información común como nombre, dirección, contacto
 * y tipo de cliente. Esta clase sirve como clase padre para clases más específicas como
 * Cliente o Institucion.
 * </p>
 *
 * <p>Incluye constructores para crear objetos desde cero, con parámetros o copiando
 * otro objeto de tipo Usuario.</p>
 *
 * @author Alejandro Farinós Ramos
 * @version 1.0
 * @date 15-04-2025
 */
public class Usuario {
    
    /** Nombre del usuario */
    private String nombre;
    
    /** Dirección del usuario */
    private String direccion;
    
    /** Tipo de cliente (particular o institucional) */
    private String tipoCliente;
    
    /** Información de contacto del usuario */
    private String contacto;

    /**
     * <p>Constructor por defecto. Inicializa los campos con valores vacíos.</p>
     */
    public Usuario() {
        nombre = " ";
        direccion = " ";
        contacto = "";
        tipoCliente = " ";
    }

    /**
     * <p>Constructor parametrizado. Permite inicializar todos los atributos del usuario.</p>
     *
     * @param nombre Nombre del usuario
     * @param direccion Dirección del usuario
     * @param contacto Información de contacto
     * @param tipoCliente Tipo de cliente (particular o institucional)
     */
    public Usuario(String nombre, String direccion, String contacto, String tipoCliente) {
        this.nombre = nombre;
        this.direccion = direccion;
        this.contacto = contacto;
        this.tipoCliente = tipoCliente;
    }

    /**
     * <p>Constructor copia. Crea un nuevo objeto Usuario copiando los valores
     * de otro objeto Usuario existente.</p>
     *
     * @param u1 Objeto Usuario del cual se copian los datos
     */
    public Usuario(Usuario u1) {
        this.nombre = u1.nombre;
        this.direccion = u1.direccion;
        this.contacto = u1.contacto;
        this.tipoCliente = u1.tipoCliente;
    }

    /**
     * <p>Establece el nombre del usuario.</p>
     *
     * @param nombre Nombre a asignar
     */
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    /**
     * <p>Establece la dirección del usuario.</p>
     *
     * @param direccion Dirección a asignar
     */
    public void setDireccion(String direccion) {
        this.direccion = direccion;
    }

    /**
     * <p>Establece el contacto del usuario.</p>
     *
     * @param contacto Información de contacto a asignar
     */
    public void setContacto(String contacto) {
        this.contacto = contacto;
    }

    /**
     * <p>Establece el tipo de cliente.</p>
     *
     * @param tipoCliente Tipo de cliente a asignar (particular o institucional)
     */
    public void setTipoCliente(String tipoCliente) {
        this.tipoCliente = tipoCliente;
    }

    /**
     * <p>Devuelve el nombre del usuario.</p>
     *
     * @return Nombre del usuario
     */
    public String getNombre() {
        return nombre;
    }

    /**
     * <p>Devuelve la dirección del usuario.</p>
     *
     * @return Dirección del usuario
     */
    public String getDireccion() {
        return direccion;
    }

    /**
     * <p>Devuelve el contacto del usuario.</p>
     *
     * @return Información de contacto
     */
    public String getContacto() {
        return contacto;
    }

    /**
     * <p>Devuelve el tipo de cliente.</p>
     *
     * @return Tipo de cliente (particular o institucional)
     */
    public String getTipoCliente() {
        return tipoCliente;
    }

    /**
     * <p>Devuelve una representación en texto del objeto Usuario.</p>
     *
     * @return Cadena con los datos del usuario
     */
    public String toString() {
        return "Los datos del usuario son nombre: " + nombre + " direccion: " + direccion + " contacto: " + contacto + " tipo de cliente: " + tipoCliente;
    }
}

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
