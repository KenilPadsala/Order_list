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


Schema::create('order_list', function (Blueprint $table) {
    $table->id();
    $table->foreignId('order_id')->constrained('orders')->onDelete('cascade');
    $table->foreignId('product_id')->constrained('products')->onDelete('cascade');
    $table->string('product_name');
    $table->integer('quantity');
    $table->decimal('price', 10, 2);
    $table->decimal('total', 10, 2);
    $table->timestamps();
});
