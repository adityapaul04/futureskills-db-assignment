## Q 1: Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.

The relationship between the "Product" and "Product_Category" entities is a many-to-one relationship, denoted by the notation "^ to 1".

This means that:
- Many products can belong to one specific category, but
- Each individual product belongs to only one category.

This relationship is established through a foreign key constraint in the 'Product' table, where the 'category_id' column references the primary key 'id' column in the 'Product_Category' table. This ensures data integrity and allows efficient querying and management of the product catalog based on different categories.

## Q 2: How could you ensure that each product in the "Product" table has a valid category assigned to it?

In the schema definition or during table creation, we should specify the foreign key constraint on the 'category_id' column in the "Product" table. This constraint establishes a link between the 'category_id' column in the "Product" table and the 'id' column in the "Product_Category" table.

```sql
ALTER TABLE Product
ADD CONSTRAINT fk_category
FOREIGN KEY (category_id)
REFERENCES Product_Category(id);
```
With the foreign key constraint in place, the database management system automatically ensures referential integrity. It won't allow the insertion or updating of records in the "Product" table if the category_id value doesn't exist in the "Product_Category" table.