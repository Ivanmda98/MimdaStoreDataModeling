# Mimda store inventory

## List of entities

### products

- product_id **(PK)**
- product
- price
- supplier

### products_variant

- variant_id **(PK)**
- product_id **(FK)**
- size
- color
- prize
- image
- stock

### suppliers

- supplier_id **(PK)**
- supplier
- supplier_type_id **(FK)**
- phone_number
- address_id **(FK)**
- email
- contact

### suppliers_type

- supplier_type_id **(PK)**
- supplier_type

### suppliers_address

- address_id **(PK)**
- supplier_id **(FK)**
- country_id **(FK)**
- estate
- cp
- colony
- street
- exterior_number
- interior_number

### countries

- county_id **(PK)**
- country

### purchase_orders

- purchase_order_id **(PK)**
- supplier_id **(FK)**
- order_date
- status
- shipping_cost
- delivery_date
- total_amount
- note

### purchase_order_itmes

- purchase_order_item_id **(PK)**
- purchase_order_id **(FK)**
- variant_id **(FK)**
- quantity
- unit_price
- subtotal

## Relations

### products _to_ supliers

- A **product** _could be supplied_ by different **supplier** (_1 to Many_).
- A **supplier** _supplies_ diferents **products** (_1 to many_).
- Relation _1:N_

### products _to_ products_variant

- A **product** _could have_ many **variants** (_1 to many_).
- A **variant** _is about_ a **product** (_1 to 1_).
- Relation _1:N_

### suppliers to supplier_types

- A **supplier** _can be assigned_ a **supplier type** (_1 to 1_).
- A **supplier type** _could be assigned_ to different **suppliers** (_1 to many_).
- Relation _1:N_

### suppliers to suppliers_address

- A **supplier** _could have_ diferent **addresses** (_1 to many_).
- An **address** _can be just assigned_ to a **supplier** (_1 to 1_).
- Relation _1:N_

### suppliers_address to countries

- An **address** _can be assigned_ a **country** (_1 to 1_).
- A **country** _could be assigned_ to different **addressess** (_1 to many_).
- Relation _1:N_

### purchase_orders to suppliers
- A **purchase order** _could be_ suplied by a **supplier** (_1 to 1_).
- A **suplier** _could suplied_ different **orders** (_1 to many_).
- Relation _1:N_

### purchase_order_items to purchase_orders
- A **purchase order** _could have_ many **items** (_1 to many_).
- An **item** is related to a  **purchase_order_item** (_1 to 1_).
- Relation _1:1_

