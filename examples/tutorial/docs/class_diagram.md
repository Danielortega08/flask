# Diagrama de Classes UML — Aplicació Flaskr

## Objectiu
Aquest document presenta el diagrama de classes UML de l'aplicació web **Flaskr**. L'objectiu és representar visualment l'estructura de dades, els atributs, els mètodes principals i les relacions de cardinalitat entre les entitats del sistema (`User` i `Post`) per facilitar la comprensió i el manteniment del projecte.

```mermaid
classDiagram
    class User {
        +int id PK
        +string username UK
        +string password
        +register(username, password)
        +login(username, password)
        +load_logged_in_user()
        +logout()
        +login_required(view)
    }

    class Post {
        +int id PK
        +int author_id FK
        +timestamp created
        +string title
        +string body
        +index()
        +create(title, body)
        +get_post(id, check_author)
        +update(id, title, body)
        +delete(id)
    }

    User "1" --> "0..*" Post : escriu / publica
```
