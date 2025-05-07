# 🧩 Esquema de Comunicación en una Arquitectura con GraphQL

Este esquema representa cómo fluye la información desde el **cliente (frontend)** hasta la **base de datos**, pasando por el **servidor GraphQL**.

---

## 🖼️ Esquema General
```
+------------+ +----------------+ +------------------+
| Frontend | <-----> | Servidor API | <-----> | Base de Datos |
| (cliente) | Query | (GraphQL) | Resolver ejecuta lógica |
+------------+ +----------------+ +------------------+
| | |
|---Consulta GraphQL--> |
| | |
| Analiza la consulta |
| Ejecuta resolvers |
| | |
| |---Consulta SQL/noSQL----->|
| |<---Datos desde DB---------|
|<---Respuesta JSON---| |

```
---

## 🔁 Flujo Paso a Paso

1. **Frontend** envía una consulta (query o mutation) en lenguaje GraphQL.
2. **Servidor GraphQL** recibe la consulta y la interpreta según el esquema.
3. Se invocan los **resolvers** correspondientes.
4. Cada resolver se comunica con servicios o directamente con la **base de datos**.
5. Los datos se devuelven al servidor GraphQL.
6. GraphQL forma una respuesta JSON basada en lo que pidió el cliente.
7. La **respuesta JSON** se envía de vuelta al frontend.

---

## 🧠 Claves del proceso

- El cliente **solo recibe los campos que pide**, ni más ni menos.
- Cada campo en la query es atendido por un **resolver** que decide cómo obtener los datos.
- Se puede acceder a múltiples fuentes de datos (bases SQL, NoSQL, APIs externas).
- Toda la comunicación se hace a través de **un único endpoint GraphQL**.

---

## 🛠️ Tecnologías involucradas

- **Frontend**: React, Angular, Vue, etc. usando librerías como Apollo Client o Relay.
- **Servidor**: Node.js (Apollo Server, Express), Java (GraphQL-Java), Python, etc.
- **Base de datos**: PostgreSQL, MongoDB, MySQL, u otros orígenes.

---

