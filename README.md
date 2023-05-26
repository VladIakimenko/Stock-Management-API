## Technical Task  
Stock Management API with CRUD logic for stocks with products. The project is intended to manage the product inventory across multiple warehouses. It should facilitate operations such as creation, receiving detailed description, update, and deletion of both products and warehouses.

## Description
Each product is characterized by a unique name and an optional description. Warehouses are places where these products are stored. The cost of storing a product may vary from warehouse to warehouse, meaning the same product could potentially have different storage costs at different locations.
This API includes functionality for product search based on product names and descriptions, as well as warehouse search based on the products stored in them.

## Features
- **Product CRUD Operations**: The API allows performing CRUD operations on products. 
- **Warehouse CRUD Operations**: API can perform CRUD operations on warehouses.
- **Product Search**: Search for products by name and description.
- **Warehouse Search**: Possibility to find warehouses that store a specific product.
- **Pagination**: As the number of products and warehouses can be large, the API implements client-side pagination to manage the display of lists.

## Endpoints
Detailed breakout of the API endpoints can be found in the requests-samples.http. This includes examples of requests that can be used for testing.  
The file contains tests for situations such as:

    Product and warehouse creation
    Updating of product descriptions and warehouse product lists
    Product deletion
    Product search based on name and description
    Warehouse search that holds a specific product, identified by product id, name, or description

## Implementation details
One of the unique features is the serialization of warehouses. Each warehouse in the system, in addition to its own attributes, provides a detailed listing of all the products it currently holds. This is achieved using a nested serializer for product positions.
During the process of updating a warehouse, the system intelligently manages product positions. When new product data is supplied, the system determines which existing product positions need to be deleted, updated, or created. This automatic discovery ensures data consistency and requires less manual data handling.