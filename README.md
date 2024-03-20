# Fast Cart 🛒

This project demonstrates building a microservices architecture using FastAPI and Redis. It consists of two main microservices: Inventory Microservice and Payment Microservice. The Inventory Microservice handles storing products and their quantities, while the Payment Microservice processes orders and payments. Redis is utilized as both a data store and for event streaming between microservices. 🚀

## Introduction

This project demonstrates building a microservices architecture using FastAPI and Redis. It consists of two main microservices: Inventory Microservice and Payment Microservice. The Inventory Microservice handles storing products and their quantities, while the Payment Microservice processes orders and payments. Redis is utilized as both a data store and for event streaming between microservices. 📦

## Setup and Run

### Prerequisites

- Python (3.7+)
- Redis

### Clone the Repository

```bash
git clone https://github.com/jsy10101/Fast-Cart.git
cd Fast-Cart
```

### Setting Up the Inventory Microservice

1. Navigate to the `Fast-Cart` directory.

```bash
cd inventory
```

2. Install dependencies.

```bash
pip install -r requirements.txt
```

3. Start the FastAPI server.

```bash
uvicorn main:app --reload
```

### Setting Up the Payment Microservice

1. Navigate to the `payment` directory.

```bash
cd ../payment
```

2. Install dependencies.

```bash
pip install -r requirements.txt
```

3. Start the FastAPI server.

```bash
uvicorn main:app --reload
```

## App Demo

The application allows users to create products and purchase them. Upon creation, products are stored in the Inventory Microservice. Users can then purchase these products through the Payment Microservice. Redis is utilized for storing data and facilitating communication between microservices via event streaming. 🛒💳

## Inventory Microservice Setup

### FastAPI Setup

To set up the Inventory Microservice, install FastAPI and Uvicorn by following the instructions at [FastAPI Documentation](https://fastapi.tiangolo.com/).

### Creating Product Models

Define product models using Redis-ORM for storing products in the Redis database. 🗃️

### API Endpoints

- **GET /products:** Retrieve all products.
- **POST /products:** Create a new product.
- **GET /products/{id}:** Retrieve a specific product.
- **DELETE /products/{id}:** Delete a product. 🛠️

## Payment Microservice Setup

### Connecting to Redis

Connect to the same Redis database as the Inventory Microservice to process orders. 🔄

### Processing Orders

- Retrieve product information from the Inventory Microservice using HTTP requests.
- Process orders, calculate total prices, and change order status to 'completed' asynchronously. 📦💰

### Handling Asynchronous Tasks

Utilize FastAPI's background tasks to handle asynchronous processing, ensuring that orders are processed efficiently without blocking the main thread. ⏳

### Refunding Orders

In case of errors or delays, handle refunds by changing order status to 'refunded' and notifying customers via email. 🛍️🔙
