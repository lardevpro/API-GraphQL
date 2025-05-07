# ¿Cómo funciona GraphQL?

GraphQL funciona como un lenguaje de consulta intermedio entre el cliente y el servidor. En lugar de múltiples endpoints REST, GraphQL expone un único punto de entrada para que el cliente solicite exactamente los datos que necesita.

## ⚙️ Flujo de funcionamiento

1. **El cliente realiza una consulta**  
   El frontend escribe una consulta declarativa especificando los campos y estructuras de datos que desea recibir.

2. **El servidor interpreta la consulta**  
   El servidor GraphQL recibe la solicitud y valida la consulta contra un esquema definido con tipos y relaciones.

3. **Resolución de datos (Resolvers)**  
   Cada campo solicitado se resuelve mediante funciones llamadas *resolvers*. Estas pueden acceder a bases de datos, APIs externas u otras fuentes.

4. **Se construye la respuesta**  
   GraphQL arma un objeto JSON con la estructura exacta pedida por el cliente.

## 🧱 Componentes principales

- **Schema (Esquema)**  
  Define los tipos de datos disponibles, las relaciones entre ellos y las operaciones permitidas (`Query`, `Mutation`, `Subscription`).

- **Query**  
  Operación para leer datos.

- **Mutation**  
  Operación para escribir, actualizar o eliminar datos.

- **Resolvers**  
  Funciones que obtienen los datos reales para cada campo solicitado en la consulta.

## 🧪 Ejemplo de consulta y respuesta

### Consulta

```graphql
query {
  libro(id: "10") {
    titulo
    autor {
      nombre
    }
  }
}
```
### Respuesta

```
{
  "data": {
    "libro": {
      "titulo": "1984",
      "autor": {
        "nombre": "George Orwell"
      }
    }
  }
}
```
## 🔁 Comparación con REST

| REST                             | GraphQL                            |
|----------------------------------|-------------------------------------|
| Varios endpoints                 | Un solo endpoint                    |
| Devuelve estructura fija         | Devuelve estructura personalizada   |
| Difícil de versionar             | Flexible y evolutivo                |
| Puede requerir múltiples llamadas| Solo una consulta                   |

## 📦 Beneficios del funcionamiento

- Eficiencia en el consumo de datos
- Mayor control para el cliente
- Desarrollo frontend más independiente del backend
- Menor carga en la red

## 🚧 Consideraciones

- Requiere definir un buen esquema y control de resolvers.
- Es importante proteger la API ante consultas complejas o maliciosas (uso de `depth limit`, `cost analysis`, etc).

