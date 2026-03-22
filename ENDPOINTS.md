# API Endpoints Documentation

## QuickBite Food Delivery FastAPI Project
**Version:** 1.0.0  
**Total Endpoints:** 16

This document lists all the API endpoints with their descriptions. Each endpoint has a corresponding screenshot in the `screenshots/` folder.

---

## Menu Endpoints (9 endpoints)

### 1. GET / - Root Endpoint
**Description:** Returns the root endpoint response
**Screenshot:** `endpoints/01-root.png`
**Method:** GET
**Path:** `/`

### 2. GET /menu/summary - Menu Summary
**Description:** Get a summary of the menu
**Screenshot:** `endpoints/02-menu-summary.png`
**Method:** GET
**Path:** `/menu/summary`

### 3. GET /menu/filter - Filter Menu
**Description:** Filter menu items based on criteria
**Screenshot:** `endpoints/03-menu-filter.png`
**Method:** GET
**Path:** `/menu/filter`
**Parameters:** category, min_price, max_price (example)

### 4. GET /menu/search - Search Menu
**Description:** Search for menu items by name or keyword
**Screenshot:** `endpoints/04-menu-search.png`
**Method:** GET
**Path:** `/menu/search`
**Parameters:** query, search_term

### 5. GET /menu/sort - Sort Menu
**Description:** Sort menu items by various criteria
**Screenshot:** `endpoints/05-menu-sort.png`
**Method:** GET
**Path:** `/menu/sort`
**Parameters:** sort_by (name, price, rating, etc.)

### 6. GET /menu/page - Paginate Menu
**Description:** Get paginated menu items
**Screenshot:** `endpoints/06-menu-page.png`
**Method:** GET
**Path:** `/menu/page`
**Parameters:** page, limit

### 7. GET /menu/browse - Browse Menu
**Description:** Browse menu items with various options
**Screenshot:** `endpoints/07-menu-browse.png`
**Method:** GET
**Path:** `/menu/browse`
**Parameters:** category, offset, limit

### 8. GET /menu - Get Full Menu
**Description:** Get the complete menu with all items
**Screenshot:** `endpoints/08-menu-get-all.png`
**Method:** GET
**Path:** `/menu`
**Returns:** Array of all menu items

### 9. GET /menu/{item_id} - Get Menu Item
**Description:** Get a specific menu item by ID
**Screenshot:** `endpoints/09-menu-get-item.png`
**Method:** GET
**Path:** `/menu/{item_id}`
**Parameters:** item_id (path parameter)

---

## Order Endpoints (3 endpoints)

### 10. GET /orders - Get Orders
**Description:** Retrieve all orders or user's orders
**Screenshot:** `endpoints/10-orders-get-all.png`
**Method:** GET
**Path:** `/orders`
**Returns:** Array of orders

### 11. POST /orders - Create Order
**Description:** Create a new order
**Screenshot:** `endpoints/11-orders-create.png`
**Method:** POST
**Path:** `/orders`
**Request Body:** OrderRequest schema
- items: array of items
- user_id: user identifier
- delivery_address: delivery location

### 12. GET /orders/search - Search Orders
**Description:** Search orders by status, user, or date
**Screenshot:** `endpoints/12-orders-search.png`
**Method:** GET
**Path:** `/orders/search`
**Parameters:** status, user_id, date_range

---

## Cart Endpoints (4 endpoints)

### 13. POST /cart/add - Add To Cart
**Description:** Add an item to the shopping cart
**Screenshot:** `endpoints/13-cart-add.png`
**Method:** POST
**Path:** `/cart/add`
**Request Body:**
- item_id: ID of the menu item
- quantity: number of items
- customizations: optional customizations

### 14. GET /cart - Get Cart
**Description:** Retrieve the current shopping cart
**Screenshot:** `endpoints/14-cart-get.png`
**Method:** GET
**Path:** `/cart`
**Returns:** Cart object with items and total

### 15. DELETE /cart/{item_id} - Remove From Cart
**Description:** Remove an item from the shopping cart
**Screenshot:** `endpoints/15-cart-remove-item.png`
**Method:** DELETE
**Path:** `/cart/{item_id}`
**Parameters:** item_id (path parameter)

### 16. POST /cart/checkout - Checkout Cart
**Description:** Complete the checkout process
**Screenshot:** `endpoints/16-cart-checkout.png`
**Method:** POST
**Path:** `/cart/checkout`
**Request Body:** CheckoutRequest schema
- user_id: user identifier
- delivery_address: delivery address
- payment_method: payment method

---

## Response Format

All endpoints return JSON responses with appropriate HTTP status codes:
- **200 OK:** Successful request
- **400 Bad Request:** Invalid request parameters
- **404 Not Found:** Resource not found
- **500 Internal Server Error:** Server error

## Schema Objects

### CheckoutRequest
Request body for checkout endpoint

### OrderRequest  
Request body for creating orders

### HTTPValidationError
Validation error response

### ValidationError
Individual field validation error

---

## API Documentation
**Swagger UI:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs

## Created Date
March 22, 2026
