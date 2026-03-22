# QuickBite Food Delivery - FastAPI Project

## Project Information

**Student ID:** IN226001602  
**Project Name:** QuickBite Food Delivery System  
**Framework:** FastAPI  
**Language:** Python  
**Version:** 1.0.0  
**OpenAPI Version:** 3.1  
**Total Endpoints:** 16

---

## Project Description

QuickBite is a complete FastAPI-based food delivery system that demonstrates modern REST API development practices. The project includes comprehensive endpoints for menu management, order processing, and shopping cart operations.

### Key Features

- ✅ **Menu Management**: 9 endpoints for browsing, filtering, searching, and sorting menu items
- ✅ **Order Processing**: 3 endpoints for order creation, retrieval, and search
- ✅ **Shopping Cart**: 4 endpoints for cart management and checkout
- ✅ **API Documentation**: Auto-generated Swagger UI and OpenAPI specification
- ✅ **Request Validation**: HTTPValidation and custom error handling
- ✅ **Data Schemas**: Structured request/response models

---

## Project Structure

```
IN226001602-FastAPI-QuickBite/
├── README.md                      # This file
├── ENDPOINTS.md                   # Detailed endpoint documentation
├── screenshots/                   # Endpoint screenshots
│   ├── 01-root.png
│   ├── 02-menu-summary.png
│   ├── 03-menu-filter.png
│   ├── 04-menu-search.png
│   ├── 05-menu-sort.png
│   ├── 06-menu-page.png
│   ├── 07-menu-browse.png
│   ├── 08-menu-get-all.png
│   ├── 09-menu-get-item.png
│   ├── 10-orders-get-all.png
│   ├── 11-orders-create.png
│   ├── 12-orders-search.png
│   ├── 13-cart-add.png
│   ├── 14-cart-get.png
│   ├── 15-cart-remove-item.png
│   └── 16-cart-checkout.png
└── docs/                          # Additional documentation
    └── API_REFERENCE.md
```

---

## API Endpoints Overview

### Menu Endpoints (9)

| # | Method | Path | Description |
|---|--------|------|-------------|
| 1 | GET | `/` | Root endpoint |
| 2 | GET | `/menu/summary` | Get menu summary |
| 3 | GET | `/menu/filter` | Filter menu items |
| 4 | GET | `/menu/search` | Search menu items |
| 5 | GET | `/menu/sort` | Sort menu items |
| 6 | GET | `/menu/page` | Paginate menu items |
| 7 | GET | `/menu/browse` | Browse menu |
| 8 | GET | `/menu` | Get full menu |
| 9 | GET | `/menu/{item_id}` | Get specific menu item |

### Order Endpoints (3)

| # | Method | Path | Description |
|---|--------|------|-------------|
| 10 | GET | `/orders` | Get all orders |
| 11 | POST | `/orders` | Create new order |
| 12 | GET | `/orders/search` | Search orders |

### Cart Endpoints (4)

| # | Method | Path | Description |
|---|--------|------|-------------|
| 13 | POST | `/cart/add` | Add item to cart |
| 14 | GET | `/cart` | Get cart contents |
| 15 | DELETE | `/cart/{item_id}` | Remove item from cart |
| 16 | POST | `/cart/checkout` | Checkout cart |

---

## API Documentation

### Swagger UI
Access the interactive API documentation at:
```
https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs
```

### OpenAPI Specification
View the complete OpenAPI specification at:
```
https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/openapi.json
```

---

## Request/Response Formats

### Content Type
All endpoints use **application/json** for request and response bodies.

### Status Codes

- **200 OK** - Successful GET, PUT requests
- **201 Created** - Successful POST request
- **400 Bad Request** - Invalid request parameters or body
- **404 Not Found** - Resource not found
- **422 Unprocessable Entity** - Validation error
- **500 Internal Server Error** - Server error

### Error Response Format

```json
{
  "detail": "Error message description"
}
```

---

## Data Models

### CheckoutRequest
Request schema for cart checkout

### OrderRequest
Request schema for creating orders

### HTTPValidationError
HTTP validation error response

### ValidationError
Individual field validation error

---

## Endpoint Screenshots

Each endpoint has a dedicated screenshot showing the Swagger UI interface. Screenshots include:
- Endpoint definition and description
- Required and optional parameters
- Request body schema (for POST/PUT requests)
- Response schema and examples
- HTTP status codes

See the `screenshots/` folder and `ENDPOINTS.md` for detailed information on each endpoint.

---

## Usage Examples

### Menu Operations

**Get all menu items:**
```bash
curl -X GET "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/menu"
```

**Search menu items:**
```bash
curl -X GET "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/menu/search?query=pizza"
```

### Order Operations

**Get all orders:**
```bash
curl -X GET "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/orders"
```

**Create an order:**
```bash
curl -X POST "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/orders" \
  -H "Content-Type: application/json" \
  -d '{"items": [...], "user_id": "user123", "delivery_address": "123 Main St"}'
```

### Cart Operations

**Get cart:**
```bash
curl -X GET "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/cart"
```

**Add to cart:**
```bash
curl -X POST "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/cart/add" \
  -H "Content-Type: application/json" \
  -d '{"item_id": "item123", "quantity": 2}'
```

---

## Technology Stack

- **Framework:** FastAPI (Python)
- **Documentation:** Swagger UI / OpenAPI 3.1
- **Validation:** Pydantic
- **Server:** Uvicorn (ASGI)
- **Environment:** GitHub Codespaces

---

## Documentation Files

- **README.md** (this file) - Project overview and usage guide
- **ENDPOINTS.md** - Detailed documentation for all 16 API endpoints
- **screenshots/** - Visual documentation of each endpoint in Swagger UI

---

## How to View Endpoint Screenshots

1. Navigate to the `screenshots/` folder in this repository
2. Each screenshot is numbered and named according to its endpoint
3. Screenshots show the complete Swagger UI interface for each endpoint
4. Reference the `ENDPOINTS.md` file for endpoint descriptions

---

## Development Information

**Created:** March 22, 2026  
**Student ID:** IN226001602  
**Platform:** GitHub Codespaces  
**Repository:** IN226001602-FastAPI-QuickBite

---

## Key Learnings

This project demonstrates:
- ✅ Building RESTful APIs with FastAPI
- ✅ Request/response validation with Pydantic
- ✅ API documentation with Swagger UI
- ✅ HTTP methods and status codes
- ✅ Data modeling and schemas
- ✅ Error handling and validation
- ✅ API endpoint organization

---

## Contact & Support

For questions or issues regarding this project, please refer to the ENDPOINTS.md file for detailed endpoint information.

---

**Last Updated:** March 22, 2026  
**Status:** ✅ Complete with 16 API Endpoints
