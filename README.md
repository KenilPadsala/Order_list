| Field Name     | Type                 | Description                              |
| -------------- | -------------------- | ---------------------------------------- |
| `id`           | `bigIncrements`      | Primary key                              |
| `order_id`     | `unsignedBigInteger` | Foreign key to `orders` table            |
| `product_id`   | `unsignedBigInteger` | Foreign key to `products` table          |
| `product_name` | `string`             | Cached product name at the time of order |
| `quantity`     | `integer`            | Quantity of the product ordered          |
| `price`        | `decimal(10,2)`      | Price per unit at the time of order      |
| `total`        | `decimal(10,2)`      | `price * quantity`                       |
| `created_at`   | `timestamp`          | Laravel default                          |
| `updated_at`   | `timestamp`          | Laravel default                          |
