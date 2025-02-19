classDiagram
    class Ciudadano {
        -string id
        -string nombre
        -string telefono
        -int puntos
        +void entregarMaterial(Material, double)
        +int consultarPuntos()
        +bool canjearPuntos(int)
    }

    class Material {
        -string tipo
        -double puntosPorKg
        +double calcularPuntos(double peso)
    }

    class Entrega {
        -Material material
        -double peso
        -int puntosObtenidos
        +void calcularPuntos()
    }

    class Empleado {
        -string id
        -string nombre
        +void registrarEntrega(Ciudadano, Material, double)
    }

    class SistemaReciclaje {
        -list<Ciudadano> ciudadanos
        -list<Material> materiales
        +void registrarCiudadano(Ciudadano)
        +void registrarEntrega(string, string, double)
        +int consultarPuntos(string)
        +bool canjearPuntos(string, int)
    }

    Ciudadano --> Entrega
    Entrega --> Material
    Empleado --> Entrega
    SistemaReciclaje o-- Ciudadano
    SistemaReciclaje o-- Material

