# E-Commerce-Product-Power-BI-Dashboard

Here using data from e-commerce purchasing data, MS Power BI reports were created using robust data modeling and DAX fuctions. Tortal of five report pages were created.

## About the Dataset

Used dataset was originally published on Keggle, which contains six separate datasets, namely “purchases”, “products”, “users”, “sessions”, “interactions” and “reviews”. For this Power BI project, except “reviews” dataset other five datasets were considered. 

The **E-Commerce Product Intelligence Dataset** is a synthetically generated, multi-table relational dataset simulating 3.5 years of customer activity for a mid-size online retailer.

## Dataset Description

| Dataset | Description |
| ------- | ----------- |
| purchases | Purchase order line items derived from cart behavior |
| products | Product catalog with categories, pricing, descriptions, ratings, and inventory |
| users | Customer profiles and demographic attributes |
| sessions | User browsing sessions with device and traffic source information |
| interactions | User-product interaction events across 6 behavior types |

## Variable Description

### 🗄️ Master Data Dictionary

| Dataset File | Variable Name | Data Type | Key Type | Technical Description |
| :--- | :--- | :---: | :---: | :--- |
| **`users`** | `user_id` | String / UUID | **PK** | Unique identifier for each customer. |
| | `name` | String | - | Full name of the customer. |
| | `email` | String | - | Email address of the customer. |
| | `age` | Integer | - | Age of the user. |
| | `gender` | String | - | Gender identity (e.g., Male, Female, Non-binary). |
| | `country` | String | - | ISO 3166-1 alpha-2 country code of residence. |
| | `income_level` | String | - | Categorized income bracket (`low`, `medium`, `high`, `very_high`). |
| | `loyalty_tier` | String | - | Customer tier classification (`bronze`, `silver`, `gold`, `platinum`). |
| | `created_at` | DateTime | - | Timestamp when the user profile was created. |
| **`products`** | `product_id` | String / UUID | **PK** | Unique identifier for each product catalog item. |
| | `product_name` | String | - | Name of the retail product item. |
| | `category` | String | - | Top-level product vertical (e.g., `Electronics`, `Clothing`). |
| | `subcategory` | String | - | Granular classification nested under the main category. |
| | `brand` | String | - | Manufacturer or brand name of the item. |
| | `price` | Float / Decimal | - | Listed retail price per unit. |
| | `description` | String | - | Text description highlighting product features. |
| | `stock_quantity` | Integer | - | Current inventory units available in warehouses. |
| | `average_rating` | Float | - | Historical aggregated star rating of the product. |
| | `review_count` | Integer | - | Total number of customer reviews submitted for the item. |
| | `created_at` | DateTime | - | Date-time stamp when the product was added to inventory. |
| **`sessions`** | `session_id` | String / UUID | **PK** | Unique identifier for an individual browsing session. |
| | `user_id` | String / UUID | **FK** | Links back to `users.csv`. |
| | `device` | String | - | Hardware channel used (`mobile`, `desktop`, `tablet`). |
| | `referrer_source` | String | - | Marketing attribution source (e.g., `organic_search`, `email`). |
| | `session_start` | DateTime | - | Timestamp when the user initiated browsing activity. |
| | `session_end` | DateTime | - | Timestamp when the browsing activity concluded. |
| **`interactions`** | `interaction_id` | String / UUID | **PK** | Unique record identifier for a micro-behavior event. |
| | `session_id` | String / UUID | **FK** | Links back to `sessions.csv`. |
| | `user_id` | String / UUID | **FK** | Links back to `users.csv`. |
| | `product_id` | String / UUID | **FK** | Links back to `products.csv`. |
| | `interaction_type` | String | - | Action type (`view`, `click`, `add_to_cart`, `add_to_wishlist`, etc.). |
| | `interaction_value` | Float / Varying | - | Associated metric or value multiplier weight if applicable. |
| | `timestamp` | DateTime | - | Exact timestamp when the action occurred. |
| **`purchases`** | `purchase_id` | String / UUID | **PK** | Unique identifier for a checkout transaction order line item. |
| | `user_id` | String / UUID | **FK** | Links back to `users.csv`. |
| | `product_id` | String / UUID | **FK** | Links back to `products.csv`. |
| | `session_id` | String / UUID | **FK** | Links back to `sessions.csv`. |
| | `quantity` | Integer | - | Quantity volume of the item purchased in the order line. |
| | `unit_price` | Float / Decimal | - | Price per unit captured at the exact moment of transaction. |
| | `total_amount` | Float / Decimal | - | Calculated subtotal value (`quantity` × `unit_price`). |
| | `purchase_date` | DateTime | - | Date and time stamp when the payment transaction cleared. |
| | `payment_method` | String | - | Payment gateway channel used (e.g., Credit Card, Digital Wallet). |
| | `shipping_status` | String | - | Lifecycle tracking status of the order line fulfillment. |
