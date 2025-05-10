# 🧾 OrderFlow

A clean and modular Spring Boot application following **Hexagonal Architecture (Ports & Adapters)** and **Domain-Driven Design (DDD)** principles.

## 🚀 Tech Stack

- **Java 17 (Temurin)**
- **Spring Boot 3.3**
- **PostgreSQL (via Docker)**
- **Maven**
- **Spring Data JPA**
- **Spring Web / REST**
- **Spring Security (optional)**
- **H2 (in-memory database for testing)**

## 🧱 Project Structure

```
orderflow
├── domain          # Business logic (Order entity, value objects, interfaces)
├── application     # Use cases (CreateOrderUseCase, etc.)
├── infrastructure  # Database, config, persistence, Kafka (optional)
├── interfaces      # REST controllers, DTOs, mappers
├── src/test        # Unit and integration tests
└── docker-compose.yml
```

## 🐳 Getting Started with Docker

Start PostgreSQL via Docker:

```bash
docker compose up -d
```

Default credentials:
- DB: `orderflowdb`
- User: `orderflow`
- Password: `secret123`

## ▶️ Run the Application

Make sure PostgreSQL is running, then launch:

```bash
mvn clean spring-boot:run
```

Access your API at:  
`http://localhost:8080/orders`

## 🧪 Run Tests

```bash
mvn clean test
```

Tests are run using H2 in-memory database.

## 📦 API Example

### POST `/orders`

```json
{
  "customerEmail": "client@example.com",
  "amount": 89.99
}
```

### Response

```json
{
  "id": "uuid",
  "customerEmail": "client@example.com",
  "amount": 89.99,
  "status": "PENDING",
  "createdAt": "2025-05-10T11:45:12"
}
```

## ✅ Roadmap

- [x] PostgreSQL + Docker integration
- [x] Order entity + REST controller
- [x] Clean architecture with DDD
- [x] Testing configuration with H2
- [ ] Swagger UI (API documentation)
- [ ] Kafka event publishing
- [ ] JWT authentication

## 📄 License

MIT
