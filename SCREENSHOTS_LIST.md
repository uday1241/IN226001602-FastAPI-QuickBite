# QuickBite Food Delivery API - Complete Endpoint Screenshots

## Project Structure

```
FASTAPI_FOOD_DELIVERY_APP/
├── README.md
├── ENDPOINTS.md
├── SCREENSHOTS_LIST.md (this file)
├── screenshots/
│   ├── Q1_home.png                    # Swagger UI Homepage
│   ├── Q2_get_menu.png                # GET /menu
│   ├── Q3_get_by_id.png               # GET /menu/{item_id}
│   ├── Q4_menu_summary.png            # GET /menu/summary
│   ├── Q5_search_menu.png             # GET /menu/search
│   ├── Q6_sort_menu_by_price.png      # GET /menu/sort
│   ├── Q7_paginate.png                # GET /menu/page
│   ├── Q8_browse.png                  # GET /menu/browse
│   ├── Q9_filter_menu.png             # GET /menu/filter
│   ├── Q10_get_orders.png             # GET /orders
│   ├── Q11_create_order.png           # POST /orders
│   ├── Q12_search_orders.png          # GET /orders/search
│   ├── Q13_add_to_cart.png            # POST /cart/add
│   ├── Q14_view_cart.png              # GET /cart
│   ├── Q15_remove_from_cart.png       # DELETE /cart/{item_id}
│   ├── Q16_checkout.png               # POST /cart/checkout
│   ├── Q17_root_endpoint.png          # GET /
│   ├── Q18_schemas.png                # Data Schemas
│   ├── Q19_validation_errors.png      # Error Schemas
│   └── Q20_response_examples.png      # Response Examples
└── main.py
```

---

## Complete Endpoint Documentation with Screenshots

### 1. **Q1_home.png** - Swagger UI Homepage
- **Description:** Main Swagger UI interface showing all available endpoints
- **View:** Browse all 16 endpoints listed in the default section
- **URL:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs

---

## Menu Endpoints (9 Endpoints)

### 2. **Q2_get_menu.png** - GET /menu
- **Endpoint:** `GET /menu`
- **Description:** Retrieve the complete menu with all items
- **Method:** GET
- **Parameters:** None
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Array of menu items

### 3. **Q3_get_by_id.png** - GET /menu/{item_id}
- **Endpoint:** `GET /menu/{item_id}`
- **Description:** Get a specific menu item by ID
- **Method:** GET
- **Parameters:** item_id (path parameter)
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Single menu item object

### 4. **Q4_menu_summary.png** - GET /menu/summary
- **Endpoint:** `GET /menu/summary`
- **Description:** Get a summary of the menu
- **Method:** GET
- **Parameters:** Optional
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Menu summary data

### 5. **Q5_search_menu.png** - GET /menu/search
- **Endpoint:** `GET /menu/search`
- **Description:** Search for menu items by name or keyword
- **Method:** GET
- **Parameters:** query, search_term
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Array of matching menu items

### 6. **Q6_sort_menu_by_price.png** - GET /menu/sort
- **Endpoint:** `GET /menu/sort`
- **Description:** Sort menu items by various criteria (name, price, rating)
- **Method:** GET
- **Parameters:** sort_by, order
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Sorted menu items

### 7. **Q7_paginate.png** - GET /menu/page
- **Endpoint:** `GET /menu/page`
- **Description:** Get paginated menu items
- **Method:** GET
- **Parameters:** page, limit
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Paginated results

### 8. **Q8_browse.png** - GET /menu/browse
- **Endpoint:** `GET /menu/browse`
- **Description:** Browse menu items with various options
- **Method:** GET
- **Parameters:** category, offset, limit
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Browsable menu items

### 9. **Q9_filter_menu.png** - GET /menu/filter
- **Endpoint:** `GET /menu/filter`
- **Description:** Filter menu items based on criteria
- **Method:** GET
- **Parameters:** filter_key, filter_value
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Filtered menu items

---

## Order Endpoints (3 Endpoints)

### 10. **Q10_get_orders.png** - GET /orders
- **Endpoint:** `GET /orders`
- **Description:** Retrieve all orders
- **Method:** GET
- **Parameters:** user_id (optional), status (optional)
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Array of orders

### 11. **Q11_create_order.png** - POST /orders
- **Endpoint:** `POST /orders`
- **Description:** Create a new order
- **Method:** POST
- **Request Body:** OrderRequest schema
  - items: array
  - user_id: string
  - delivery_address: string
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Order confirmation

### 12. **Q12_search_orders.png** - GET /orders/search
- **Endpoint:** `GET /orders/search`
- **Description:** Search orders by status, user, or date
- **Method:** GET
- **Parameters:** status, user_id, date_range
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Search results

---

## Cart Endpoints (4 Endpoints)

### 13. **Q13_add_to_cart.png** - POST /cart/add
- **Endpoint:** `POST /cart/add`
- **Description:** Add an item to the shopping cart
- **Method:** POST
- **Request Body:**
  - item_id: string (required)
  - quantity: integer (required)
  - customizations: object (optional)
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Updated cart

### 14. **Q14_view_cart.png** - GET /cart
- **Endpoint:** `GET /cart`
- **Description:** Retrieve the current shopping cart
- **Method:** GET
- **Parameters:** None
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Cart object with items and total

### 15. **Q15_remove_from_cart.png** - DELETE /cart/{item_id}
- **Endpoint:** `DELETE /cart/{item_id}`
- **Description:** Remove an item from the shopping cart
- **Method:** DELETE
- **Parameters:** item_id (path parameter)
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Updated cart

### 16. **Q16_checkout.png** - POST /cart/checkout
- **Endpoint:** `POST /cart/checkout`
- **Description:** Complete the checkout process
- **Method:** POST
- **Request Body:** CheckoutRequest schema
  - user_id: string
  - delivery_address: string
  - payment_method: string
- **Response:** 200 OK
- **Media Type:** application/json
- **Response Body:** Order confirmation

---

## Root Endpoint

### 17. **Q17_root_endpoint.png** - GET /
- **Endpoint:** `GET /`
- **Description:** Root endpoint
- **Method:** GET
- **Parameters:** None
- **Response:** 200 OK
- **Media Type:** application/json

---

## Data Models & Schemas (Q18-Q20)

### 18. **Q18_schemas.png** - Data Schemas
- Shows all available data schemas:
  - CheckoutRequest
  - OrderRequest
  - And other request/response models

### 19. **Q19_validation_errors.png** - Validation Error Schemas
- HTTPValidationError
- ValidationError
- Field error details

### 20. **Q20_response_examples.png** - Response Examples
- Sample response bodies
- Response headers
- Media type examples

---

## HTTP Status Codes Reference

| Code | Description |
|------|-------------|
| 200 | Successful Response |
| 400 | Bad Request |
| 404 | Not Found |
| 422 | Validation Error |
| 500 | Internal Server Error |

---

## How to Use Screenshots

1. **View Individual Screenshots:** Open any `Qx_*.png` file to see the endpoint in Swagger UI
2. **Request Details:** Each screenshot shows the request parameters and body
3. **Response Format:** See the response code, body, and headers
4. **Testing:** Use the "Try it out" button visible in screenshots to test
5. **Schema Reference:** View data model structures in schemas section

---

## Live API Documentation

**Swagger UI:** https://sturdy-waddle-7vw76r9pj6qw2r4g-8000.app.github.dev/docs

Visit the live Swagger UI to:
- Interact with all endpoints
- See real-time documentation
- Test endpoints with Try it out
- View full request/response examples

---

## Project Information

- **Student ID:** IN226001602
- **Project:** QuickBite Food Delivery System
- **Framework:** FastAPI (Python)
- **API Version:** 1.0.0
- **OpenAPI Version:** 3.1
- **Total Endpoints:** 16 (20 with variations)
- **Total Screenshots:** 20

---

**Last Updated:** March 22, 2026  
**Status:** ✅ Complete with all 20 screenshots
