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

.
├── src/
│ └── index.js # Express server and API routes
├── docs/ # Design notes and documentation
├── scripts/ # Operational helper scripts
├── package.json
└── README.md


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

## Run Locally

From the `order-service` directory:

```bash
npm install
npm start
