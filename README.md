# Access Control and User Management Service

### A clean, layered REST API built with TypeScript, Node.js, Express, MongoDB, and Mongoose

## Project Overview

Access Control and User Management Service is a backend REST API for managing users, authentication, roles, permissions, and posts. It applies secure software design principles by separating HTTP concerns, business rules, security checks, and database access. This structure helps protect application resources while keeping the code easier to understand, test, maintain, and extend as the application grows.

The API is available locally at:

```text
http://localhost:4000/users-service/v1
```

## Key Architectural Features

- **Separation of responsibilities:** Routes, controllers, services, repositories, models, schemas, mappers, and middlewares each have a clear purpose.
- **Layered request flow:** Requests move from routes and middleware to controllers, services, repositories, and MongoDB models.
- **DTO-style data handling:** Request and response data are validated and mapped so that application layers do not depend directly on raw database documents.
- **Custom error handling:** Application errors are represented with custom exceptions and processed by a global error-handling middleware.
- **Reusable middleware:** Authentication, authorization, validation, logging, and error handling are implemented as composable middleware.
- **Authentication and authorization:** JWT-based authentication supports protected resources, roles, and permissions.
- **Safe responses:** Mappers help prevent internal or sensitive database fields from being returned to API clients.
- **Type safety:** TypeScript strict mode is enabled to catch many errors during development and make contracts between layers clearer.


## Main API Capabilities

- User registration, login, logout, and user management
- JWT token verification
- Role and permission management
- Protected user-owned posts
- Request validation with Zod
- Consistent HTTP response and error codes

See the complete endpoint reference in [`documents/api_endpoints.md`](documents/api_endpoints.md).

## Tech Stack

### Project Technologies

| Area                        | Technology                |
| --------------------------- | ------------------------- |
| Language                    | TypeScript                |
| Runtime                     | Node.js                   |
| Web framework               | Express.js                |
| Database                    | MongoDB                   |
| Object data modeling        | Mongoose                  |
| Validation                  | Zod                       |
| Authentication              | JSON Web Tokens           |
| Password security           | bcrypt                    |
| Logging                     | Morgan                    |
| Package manager             | pnpm                      |
| Containers                  | Docker and Docker Compose |
| Operating system experience | Linux                     |

### Broader Backend Experience

In addition to the technologies used in this project, my backend development experience includes:

- Java and Spring Boot
- REST API design and integration
- Object-oriented programming and structured programming
- DTO patterns and custom exception handling
- Relational databases such as PostgreSQL
- Non-relational databases such as MongoDB
- Linux-based development and Docker workflows

## Project Structure

```text
.
├── assets/          # Rendered architecture and flow diagrams
├── documents/       # Architecture, API, domain, and flow documentation
├── plantuml/        # PlantUML source files
├── src/             # TypeScript application source code
├── utils/            # Development and diagram utilities
├── Dockerfile
├── docker-compose.yml
├── package.json
├── pnpm-lock.yaml
├── tsconfig.json
└── todo.md
```

The main source code is organized by responsibility:

```text
src/
├── config/
├── modules/
│   ├── controllers/
│   ├── errors/
│   ├── mappers/
│   ├── middlewares/
│   ├── models/
│   ├── repositories/
│   ├── routes/
│   ├── schemas/
│   ├── services/
│   └── types/
└── sources/
```

## Visual Architecture Reference

The repository includes PlantUML source files in [`plantuml/`](plantuml/) and rendered diagrams in [`assets/`](assets/). These diagrams document the domain model, request flow, error handling, and security middleware flow.

### Layered Architecture

![Normal request flow](assets/normal_request_flow.png)

### Authentication and Authorization Flow

The [authentication and authorization flow](documents/authorization_flow.md) explains how the service verifies users, checks permissions, applies role levels, and protects user-owned resources. It includes a simple [authorization model diagram](assets/authorization_model.png) for readers who want a visual overview.

### Additional References

- [Technical architecture](documents/technical_architecture.md)
- [Domain model](documents/domain_models.md)
- [Normal request flow](documents/normal_request_flow.md)
- [Global error handling flow](documents/global_error_handling_flow.md)
- [Security middleware flow](documents/security_middlewares_flow.md)
- [Authentication and authorization flow](documents/authorization_flow.md)

## Getting Started

### Prerequisites

- Node.js 20 or later
- pnpm
- Docker and Docker Compose

### Install dependencies

```bash
pnpm install
```

### Configure environment variables

Create a `.env` file with the MongoDB and application settings required by the project. Do not commit credentials or secret values to the repository.

### Run with Docker Compose

```bash
docker compose up --build
```

The API runs on port `4000`, and MongoDB runs on port `27017`.

### Run in development mode

```bash
pnpm dev
```

### Build and start the production application

```bash
pnpm build
pnpm start
```

## About the Developer

I am a backend developer focused on building reliable services with clean code, clear architecture, and strong object-oriented principles. I enjoy designing REST APIs, separating responsibilities across well-defined layers, and working with both relational and non-relational databases.

I value teamwork, practical communication, and learning from experienced peers. I continuously improve my technical skills through hands-on projects, code reviews, and the study of backend design patterns and engineering practices.

---

**Created by [Carlos Zubilete](https://github.com/CarlosZubilete)**
