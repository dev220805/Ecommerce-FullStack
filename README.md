# E-Commerce Full Stack Platform

A full-stack e-commerce application built with **React, TypeScript, Java Spring Boot, and PostgreSQL**, featuring secure authentication, product management, shopping cart, checkout, and order tracking. The platform also incorporates asynchronous event processing using RabbitMQ and audit logging with MongoDB.

## Features

- **User Authentication:** Secure registration and login using JWT authentication with role-based access control.
- **Product Management:** Create, update, delete, search, and browse products with image uploads.
- **Category Management:** Organize products into categories for easier browsing.
- **Shopping Cart:** Add, update, and remove products from the cart.
- **Order Management:** Complete checkout and access individual order details and order history.
- **Event-Driven Processing:** RabbitMQ handles asynchronous order events and decouples background processing.
- **Audit Logging:** MongoDB stores activity logs, including order events and product searches.
- **Responsive UI:** Modern frontend built with React, TypeScript, Tailwind CSS, and Bootstrap.
- **Containerization:** Docker and Docker Compose support for running the application and its dependencies.
- **Kubernetes Support:** Deployment manifests for container orchestration.

## Tech Stack

| Category | Technologies |
|---|---|
| Frontend | React, TypeScript, Vite |
| Styling | Tailwind CSS, Bootstrap, shadcn/ui |
| Backend | Java 21, Spring Boot 3 |
| Security | Spring Security, JWT |
| Database | PostgreSQL, MongoDB, H2 |
| Messaging | RabbitMQ, Spring AMQP |
| ORM | Spring Data JPA, Hibernate |
| Database Migration | Flyway |
| API | REST API, Axios, Swagger |
| Build Tools | Maven, npm |
| DevOps | Docker, Docker Compose, Kubernetes |
| CI/CD | GitHub Actions, GitLab CI |

## Project Structure

```text
Ecommerce-FullStack/
│
├── Ecommerce-Backend/
│   └── src/
│       └── main/
│           └── java/
│               └── com/cart/ecom_proj/
│                   ├── controller/
│                   ├── model/
│                   ├── repo/
│                   ├── service/
│                   ├── security/
│                   ├── config/
│                   ├── cart/
│                   ├── order/
│                   ├── category/
│                   └── audit/
│
├── Ecommerce-Frontend/
│   └── src/
│       ├── api/
│       ├── components/
│       ├── pages/
│       ├── Context/
│       ├── types/
│       └── App.tsx
│
├── k8s/
├── .github/
├── docker-compose.yml
└── README.md
```

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Java 21
- Maven
- Node.js and npm
- Docker Desktop (for full-stack deployment)
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/dev220805/Ecommerce-FullStack.git
cd Ecommerce-FullStack
```

### 2. Run the Backend

```bash
cd Ecommerce-Backend
mvn spring-boot:run
```

The backend runs at:

`http://localhost:8080`

Swagger API documentation:

`http://localhost:8080/swagger-ui.html`

The default development profile uses an in-memory H2 database.

### 3. Run the Frontend

Open a new terminal:

```bash
cd Ecommerce-Frontend
npm install
npm run dev
```

The frontend runs at:

`http://localhost:5173`

### 4. Run Using Docker Compose

From the project root directory:

```bash
docker compose up --build
```

This starts the frontend, backend, PostgreSQL, MongoDB, and RabbitMQ services.

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | User login |
| GET | `/api/products` | Get all products |
| GET | `/api/products/{id}` | Get product details |
| GET | `/api/products/search?keyword=` | Search products |
| POST | `/api/products` | Add a product |
| GET | `/api/categories` | Get all categories |
| GET | `/api/cart` | Get shopping cart |
| POST | `/api/cart` | Add item to cart |
| POST | `/api/orders` | Place an order |
| GET | `/api/orders/{userId}` | Get order history |

## Testing

### Backend

```bash
cd Ecommerce-Backend
mvn test
```

### Frontend

```bash
cd Ecommerce-Frontend
npm run lint
npm run build
```

## Deployment

The application supports multiple deployment approaches:

- **Docker Compose:** Run the complete application stack using containers.
- **Kubernetes:** Deploy application services using the manifests provided in the `k8s/` directory.
- **CI/CD:** Automated build and testing pipelines using GitHub Actions and GitLab CI.

## Architecture

The application follows a modular architecture:

1. React frontend communicates with the Spring Boot backend through REST APIs.
2. Spring Security validates JWT tokens and manages role-based access.
3. PostgreSQL stores users, products, carts, and orders.
4. RabbitMQ processes order-related events asynchronously.
5. MongoDB maintains audit logs and activity records.

## License

This project is intended for educational and portfolio purposes.