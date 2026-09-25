classDiagram

    class CRUD~T~ {
        <<interface>>
        +crear(T entidad)
        +modificar(T entidad)
        +eliminar(Long id)
        +buscarPorId(Long id)
        +listar()
    }

    class Producto {
        +Long id
        +String nombre
        +Categoria categoria
        +String unidadMedida
        +BigDecimal precio
        +Boolean perecedero
        +Map~String,Object~ atributosVariables
        +actualizarPrecio()
        +cambiarCategoria()
    }

    class Categoria {
        +Long id
        +String nombre
    }

    class Sucursal {
        +Long id
        +String nombre
        +String direccion
        +Usuario responsable
        +asignarResponsable()
    }

    class StockSucursal {
        +Long id
        +Producto producto
        +Sucursal sucursal
        +Integer cantidadActual
        +Integer stockMinimo
        +LocalDate fechaVencimiento
        +configurarStockMinimo(cantidad)
        +verificarStockMinimo()
    }

    class MovimientoStock {
        +Long id
        +Producto producto
        +Sucursal sucursal
        +Usuario usuario
        +TipoMovimiento tipo
        +Integer cantidad
        +LocalDateTime fecha
    }

    class Usuario {
        +Long id
        +String nombre
        +String email
        +Rol rol
        +Sucursal sucursal
        +autenticar()
        +tienePermiso()
    }

    class Proveedor {
        +Long id
        +String nombre
        +String contacto
    }

    class OrdenCompra {
        +Long id
        +Proveedor proveedor
        +Sucursal sucursalDestino
        +LocalDate fecha
        +EstadoOrden estado
        +BigDecimal montoTotal
        +Boolean requiereAprobacion
        +agregarItem()
        +calcularTotal()
        +solicitarAprobacion()
        +aprobar()
        +rechazar()
    }

    class ItemOrdenCompra {
        +Long id
        +Producto producto
        +Integer cantidad
        +BigDecimal precioUnitario
        +calcularSubtotal()
    }

    class Alerta {
        +Long id
        +TipoAlerta tipo
        +Producto producto
        +Sucursal sucursal
        +LocalDateTime fechaGeneracion
        +Boolean notificada
        +generar()
        +marcarComoNotificada()
    }

    class TipoMovimiento {
        <<enumeration>>
        ENTRADA
        SALIDA
    }

    class Rol {
        <<enumeration>>
        ADMINISTRADOR_CENTRAL
        ENCARGADO_SUCURSAL
        OPERADOR
    }

    class EstadoOrden {
        <<enumeration>>
        PENDIENTE
        APROBADA
        RECHAZADA
        RECIBIDA
    }

    class TipoAlerta {
        <<enumeration>>
        STOCK_MINIMO
        VENCIMIENTO
        APROBACION
    }

    Producto ..|> CRUD
    Categoria ..|> CRUD
    Sucursal ..|> CRUD
    Usuario ..|> CRUD
    Proveedor ..|> CRUD

    Categoria "1" --> "0..*" Producto
    Producto "1" --> "0..*" StockSucursal
    Sucursal "1" --> "0..*" StockSucursal

    Producto "1" --> "0..*" MovimientoStock
    Sucursal "1" --> "0..*" MovimientoStock
    Usuario "1" --> "0..*" MovimientoStock

    Sucursal "1" --> "0..*" Usuario
    Sucursal "0..1" --> "1" Usuario : responsable

    Proveedor "1" --> "0..*" OrdenCompra
    Sucursal "1" --> "0..*" OrdenCompra : destino
    OrdenCompra "1" --> "1..*" ItemOrdenCompra
    Producto "1" --> "0..*" ItemOrdenCompra

    Producto "1" --> "0..*" Alerta
    Sucursal "1" --> "0..*" Alerta

    MovimientoStock --> TipoMovimiento
    Usuario --> Rol
    OrdenCompra --> EstadoOrden
    Alerta --> TipoAlerta