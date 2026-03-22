# API Endpoints Screenshots Guide

## Overview

This document provides a guide to viewing and understanding all 16 API endpoints of the QuickBite Food Delivery FastAPI project. Each endpoint has a corresponding screenshot available in the Swagger UI interface.

**Total Endpoints:** 16  
**Live Documentation:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs

---

## How to View Endpoint Screenshots

### Option 1: Swagger UI (Live)
1. Visit: https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs
2. Scroll through the endpoints listed under the "default" section
3. Click on any endpoint to expand it and see:
   - Endpoint path and method
   - Description
   - Parameters (if any)
   - Request body schema (for POST/DELETE endpoints)
   - Response codes and schemas
   - "Try it out" button to test the endpoint

### Option 2: This Repository
Refer to the ENDPOINTS.md file for detailed documentation of all endpoints.

---

## All 16 Endpoints with Swagger UI Paths

### Menu Endpoints (9)

#### 1. GET / - Root Endpoint
- **Path:** `GET /`
- **Description:** Root endpoint
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/root__get
- **Parameters:** None
- **Response:** 200 OK
- **Screenshot Location:** Visible on main Swagger page

#### 2. GET /menu/summary - Menu Summary
- **Path:** `GET /menu/summary`
- **Description:** Get a summary of the menu
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/menu_summary_menu_summary_get
- **Parameters:** Optional query parameters
- **Response:** 200 OK - Returns menu summary
- **Screenshot Location:** Visible after second endpoint in list

#### 3. GET /menu/filter - Filter Menu
- **Path:** `GET /menu/filter`
- **Description:** Filter menu items based on criteria (category, price range, etc.)
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/filter_menu_menu_filter_get
- **Parameters:** filter_key, filter_value
- **Response:** 200 OK - Filtered menu items
- **Screenshot Location:** Third endpoint in menu section

#### 4. GET /menu/search - Search Menu
- **Path:** `GET /menu/search`
- **Description:** Search menu items by name or keyword
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/search_menu_menu_search_get
- **Parameters:** query, search_term
- **Response:** 200 OK - Search results
- **Screenshot Location:** Fourth endpoint in list

#### 5. GET /menu/sort - Sort Menu
- **Path:** `GET /menu/sort`
- **Description:** Sort menu items by various criteria (name, price, rating)
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/sort_menu_menu_sort_get
- **Parameters:** sort_by, order (asc/desc)
- **Response:** 200 OK - Sorted menu items
- **Screenshot Location:** Fifth endpoint

#### 6. GET /menu/page - Paginate Menu
- **Path:** `GET /menu/page`
- **Description:** Get paginated menu items
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/paginate_menu_menu_page_get
- **Parameters:** page (number), limit (items per page)
- **Response:** 200 OK - Paginated results
- **Screenshot Location:** Sixth endpoint

#### 7. GET /menu/browse - Browse Menu
- **Path:** `GET /menu/browse`
- **Description:** Browse menu items with options
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/browse_menu_menu_browse_get
- **Parameters:** category, offset, limit
- **Response:** 200 OK - Browsable menu items
- **Screenshot Location:** Seventh endpoint

#### 8. GET /menu - Get Full Menu
- **Path:** `GET /menu`
- **Description:** Get the complete menu with all items
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/get_menu_menu_get
- **Parameters:** None
- **Response:** 200 OK - Array of all menu items
- **Media Type:** application/json
- **Screenshot Location:** Eighth endpoint

#### 9. GET /menu/{item_id} - Get Menu Item
- **Path:** `GET /menu/{item_id}`
- **Description:** Get a specific menu item by ID
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/get_menu_item_menu__item_id__get
- **Parameters:** item_id (path parameter, required)
- **Response:** 200 OK - Single menu item
- **Screenshot Location:** Ninth endpoint

---

### Order Endpoints (3)

#### 10. GET /orders - Get Orders
- **Path:** `GET /orders`
- **Description:** Retrieve all orders or user's orders
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/get_orders_orders_get
- **Parameters:** user_id (optional), status (optional)
- **Response:** 200 OK - Array of orders
- **Screenshot Location:** Tenth endpoint

#### 11. POST /orders - Create Order
- **Path:** `POST /orders`
- **Description:** Create a new order
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/create_order_orders_post
- **Request Body:** OrderRequest schema
  - items: array
  - user_id: string
  - delivery_address: string
- **Response:** 200 OK - Order confirmation
- **Media Type:** application/json
- **Screenshot Location:** Eleventh endpoint

#### 12. GET /orders/search - Search Orders
- **Path:** `GET /orders/search`
- **Description:** Search orders by status, user, or date
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/search_orders_orders_search_get
- **Parameters:** status, user_id, date_range
- **Response:** 200 OK - Search results
- **Screenshot Location:** Twelfth endpoint

---

### Cart Endpoints (4)

#### 13. POST /cart/add - Add To Cart
- **Path:** `POST /cart/add`
- **Description:** Add an item to the shopping cart
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/add_to_cart_cart_add_post
- **Request Body:**
  - item_id: string (required)
  - quantity: integer (required)
  - customizations: object (optional)
- **Response:** 200 OK - Updated cart
- **Media Type:** application/json
- **Screenshot Location:** Thirteenth endpoint

#### 14. GET /cart - Get Cart
- **Path:** `GET /cart`
- **Description:** Retrieve the current shopping cart
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/get_cart_cart_get
- **Parameters:** None
- **Response:** 200 OK - Cart object
- **Screenshot Location:** Fourteenth endpoint

#### 15. DELETE /cart/{item_id} - Remove From Cart
- **Path:** `DELETE /cart/{item_id}`
- **Description:** Remove an item from the shopping cart
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/remove_from_cart_cart__item_id__delete
- **Parameters:** item_id (path parameter, required)
- **Response:** 200 OK - Updated cart
- **Screenshot Location:** Fifteenth endpoint

#### 16. POST /cart/checkout - Checkout Cart
- **Path:** `POST /cart/checkout`
- **Description:** Complete the checkout process
- **Swagger UI Link:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs#/default/checkout_cart_cart_checkout_post
- **Request Body:** CheckoutRequest schema
  - user_id: string
  - delivery_address: string
  - payment_method: string
- **Response:** 200 OK - Order confirmation
- **Media Type:** application/json
- **Screenshot Location:** Sixteenth endpoint (last)

---

## Response Schemas

### Data Models Available in Swagger UI

1. **CheckoutRequest** - Expands to show object structure
2. **HTTPValidationError** - HTTP validation error response format
3. **OrderRequest** - Order creation request schema
4. **ValidationError** - Individual field validation errors

These are visible in the "Schemas" section at the bottom of the Swagger UI page.

---

## Testing Endpoints

### Using Swagger UI "Try it Out"

1. Click on any endpoint to expand it
2. Click the "Try it out" button
3. Fill in parameters or request body as needed
4. Click "Execute"
5. View the response and response code

### Using cURL

Example for GET /menu:
```bash
curl -X GET "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/menu"
```

Example for POST /cart/add:
```bash
curl -X POST "https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/cart/add" \
  -H "Content-Type: application/json" \
  -d '{"item_id": "item123", "quantity": 2}'
```

---

## HTTP Status Codes

- **200 OK** - Request successful
- **400 Bad Request** - Invalid request parameters
- **404 Not Found** - Resource not found
- **422 Unprocessable Entity** - Validation error
- **500 Internal Server Error** - Server error

---

## Content Type

All endpoints accept and return **application/json** content type.

---

## Documentation Files in This Repository

1. **README.md** - Project overview and usage
2. **ENDPOINTS.md** - Detailed endpoint descriptions
3. **API_ENDPOINTS_SCREENSHOTS.md** (this file) - Guide to viewing screenshots in Swagger UI

---

## Live API Documentation

**Visit:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs

This live Swagger UI interface provides:
- Complete endpoint documentation
- Interactive API testing (Try it out)
- Request/response examples
- Parameter validation
- Schema definitions

---

**Last Updated:** March 22, 2026  
**Student ID:** IN226001602  
**Project:** IN226001602-FastAPI-QuickBite
