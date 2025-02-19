Diseño uno

Problemas primer diseño


- Faltan atributos :
* No tiene un identificador único .
* No tiene capacidad máxima (capacidad).
-Faltan métodos :
* No tiene un método para consultar disponibilidad (estaDisponible()).
* No tiene un método para liberar un espacio (liberar()).
- Problema de encapsulación:
* Los atributos están públicos (+) cuando deberían ser privados (-).
-Falta un método para liberar reservas:
* No hay una función en GestorReservas para liberar reservas .
-Errores en las relaciones:
* La flecha de Espacio a Reserva debería ir en la dirección contraria.
* La relación de GestorReservas con Reserva usa --o en vez de o--.


classDiagram
    class Espacio {
        -string id
        -string tipo
        -bool disponible
        -int capacidad
        -double tarifa
        +bool estaDisponible()
        +double consultarTarifaHora()
        +void liberar()
    }

    class Reserva {
        +Espacio* espacio
        +int duracion
        +double calcularCosto()
    }

    class GestorReservas {
        +list<Reserva> reservas
        +void realizarReserva(Espacio, int)
        +void cancelarReserva(Espacio)
        +void liberarReserva(Reserva)
    }

    Reserva --> Espacio
    GestorReservas o-- Reserva


Diseño dos

Problemas segundo diseño:

 Faltan atributos :
* No tiene un identificador único .
* No tiene capacidad máxima (capacidad).
-Faltan métodos :
* No tiene un método para consultar disponibilidad (estaDisponible()).
* No tiene un método para liberar un espacio (liberar()).
- Problema de encapsulación:
* Los atributos están públicos (+) cuando deberían ser privados (-).
-Falta un método para liberar reservas:
* No hay una función en GestorReservas para liberar reservas .

classDiagram
    class Espacio {
        -string id
        -string tipo
        -bool disponible
        -int capacidad
        -double tarifa
        +bool estaDisponible()
        +double consultarTarifaHora()
        +void liberar()
    }

    class Reserva {
        +Espacio* espacio
        +int duracion
        +double calcularCosto()
    }

    class GestorReservas {
        +list<Reserva> reservas
        +void realizarReserva(Espacio, int)
        +void cancelarReserva(Espacio)
        +void liberarReserva(Reserva)
    }

    Reserva --> Espacio
    GestorReservas o-- Reserva




Problemas  tercer diseño:
-Faltan atributos esenciales en Espacio:
* No tiene un identificador único .
- Falta un método para liberar reservas en GestorReservas:
* No hay una función para que el administrador pueda liberar reservas .

classDiagram
    class Espacio {
        -string id
        -string tipo
        -bool disponible
        -int capacidad
        -double tarifa
        +bool estaDisponible()
        +double consultarTarifaHora()
        +void liberar()
    }

    class Reserva {
        +Espacio* espacio
        +int duracion
        +double calcularCosto()
    }

    class GestorReservas {
        +list<Reserva> reservas
        +void realizarReserva(Espacio, int)
        +void cancelarReserva(Espacio)
        +void liberarReserva(Reserva)
    }

    Reserva --> Espacio
    GestorReservas o-- Reserva

