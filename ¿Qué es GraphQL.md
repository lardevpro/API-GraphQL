# ¿Qué es GraphQL?

GraphQL es un lenguaje de consultas para APIs y un entorno de ejecución para esas consultas. Fue desarrollado por Facebook en 2012 y liberado como proyecto open source en 2015.

## 🧠 Conceptos clave

- **Consulta precisa de datos**: Permite a los clientes pedir exactamente los datos que necesitan, sin obtener más ni menos.
- **Un único endpoint**: A diferencia de REST, que suele tener múltiples endpoints, GraphQL expone una única URL para todas las operaciones.
- **Tipos fuertemente tipados**: Usa un sistema de tipos que define claramente qué datos están disponibles y cómo acceder a ellos.
- **Consulta jerárquica**: El formato de las consultas refleja la estructura del resultado esperado.

## 📦 Ventajas

- Evita el **overfetching** (pedir más datos de los necesarios) y el **underfetching** (pedir menos datos y tener que hacer más peticiones).
- Excelente para aplicaciones móviles y SPA, donde la eficiencia del ancho de banda es crucial.
- El **autodescubrimiento** mediante introspección facilita la documentación y el desarrollo con herramientas como GraphiQL o Apollo Studio.

## ⚙️ Ejemplo básico de consulta

```graphql
query {
  usuario(id: "1") {
    nombre
    correo
  }
}
```
Este ejemplo pide solo el `nombre` y el `correo` del usuario con ID 1.

## 🚫 Desventajas

- Puede ser más complejo de implementar en el backend.
- Las consultas mal diseñadas pueden generar cargas innecesarias si no se controla adecuadamente.
- No siempre es la mejor opción para operaciones simples o casos donde REST ya funciona bien.

## 🔧 Casos de uso comunes

- Aplicaciones con interfaces ricas en datos y altamente dinámicas (como paneles, apps móviles o SPA).
- Microservicios y agregación de múltiples fuentes de datos.
- Proyectos que requieren una evolución rápida del frontend sin depender del backend.

## 🔚 Conclusión

GraphQL es una potente alternativa a REST para APIs modernas. Permite consultas flexibles, eficaces y adaptables a las necesidades del cliente, pero requiere una implementación y seguridad cuidadosas.


[Sitio oficial de graphQL](https://graphql.org/)
