# CRUD Refugio Spring
## Objetivos:
- Crear un sistema CRUD (Create, Read, Update, Delate) para nuestro refugio.
- Se pueden crear nuevos animales, modificar su nombre, edad o color y eliminarlos.
- Proveer un sistema con criterios de busqueda (por nombre que contengan un valor, por color, por edad mayor o menor que y por id_animal).

## Interfaz del front:
- Los colores se envian como String.

## Base de datos:
Tabla animales
  - Columnas: 
    - id_animal
    - nombre
    - edad
    - color.
    
## En Java.
### Entity: 
Animal. Mapear las columnas con atributos. Crear bean. @Entity

### Repository: 
    @Repository 
    public interface AnimalRepo extends JpaRepository<Animal, Integer>

### Service:
    @Service AnimalService
#### Inyectamos el repository -> @Autowired de AnimalRepo

### Controller: 
    @Controller AnimalController
#### Inyectamos el service -> @Autowired de AnimalService

### Endpoints.
    GET /animales
        Listar todos los animales
    GET /animales/ nombre/ {nombre}
        Busca por nombres que contegan el valor. (usar containig)
    GET /animales/color/{color}
        Busca por color exacto
    GET /animales/edad/{edadDesde}/{edadHasta}
        Busca animales en un rango de edad (usar between)
    GET /animales/id/{id}
        Busca un animal por ID
    GET /animales/nuevo
        Muestra el formulario para crear un nuevo animal
    POST /animales/guardar
        Guarda o actualiza un nuevo animal
    DELATE /animales/id/{id}
        Elimina un animal por ID

*Java backend 5 - ADAITW 2021 | Profesor: Pablo Acevedo | Alumna: Jesica Belen Salva*