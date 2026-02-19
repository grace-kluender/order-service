# Order Service (REST API)

This repository contains the Order Service for a microservices-based e-commerce platform.

The Order Service is responsible for:
- Creating orders
- Retrieving orders
- Updating order status
- Verifying products via the Product Service
- Persisting order data in PostgreSQL

---

## Tech Stack

- Node.js
- Express
- PostgreSQL (pg)
- Axios (inter-service HTTP calls)
- CORS

---

## Repository Structure

This repository follows a standardized structure used across all microservices repositories:

```
.
├── src/
│ └── index.js # Express server and API routes
├── docs/ # Design notes and documentation
├── scripts/ # Operational helper scripts
├── package.json
└── README.md
```

---

## Prerequisites

- Node.js (LTS recommended)
- npm
- PostgreSQL running locally
- Database initialized using `database/src/init.sql`

---

## Environment Variables

The service supports the following environment variables:

| Variable        | Default      | Description |
|-----------------|-------------|-------------|
| PORT            | 3002        | API server port |
| DB_HOST         | localhost   | PostgreSQL host |
| DB_NAME         | ecommerce   | Database name |
| DB_USER         | postgres    | Database user |
| DB_PASSWORD     | password    | Database password |

If not provided, default values are used.

---

## Build

From the `order-service` directory:

```bash
npm install
npm start
```

## Run/Deploy (Local)

```bash
DB_HOST=localhost DB_NAME=ecommerce DB_USER=postgres DB_PASSWORD=password \
PRODUCT_SERVICE_URL=http://localhost:3001 \
PORT=3002 npm start
```

## Verify Health

```bash
curl -i http://localhost:3002/health
curl -s http://localhost:3002/orders
```

## Create an Order

```bash
curl -s -X POST http://localhost:3002/orders \
  -H "Content-Type: application/json" \
  -d '{"productId":1,"quantity":1}'
```
