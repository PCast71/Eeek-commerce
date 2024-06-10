# E-commerce Backend

## Description

This project is the backend for an e-commerce application, providing a RESTful API for managing products, categories, and tags. The API is built using Node.js, Express.js, and Sequelize ORM for interacting with a MySQL database.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Endpoints](#endpoints)
  - [Categories](#categories)
  - [Products](#products)
  - [Tags](#tags)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. **Clone the repository**:
    ```bash
    git clone git@github.com:PCast71/Eeek-commerce.git
    cd e-commerce-backend
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Set up the database**:
    - Make sure you have MySQL installed and running on your machine.
    - Create a `.env` file in the root directory and add your database credentials:
        ```env
        DB_NAME=ecommerce_db
        DB_USER=your_mysql_username
        DB_PASSWORD=your_mysql_password
        DB_HOST=localhost
        DB_DIALECT=mysql
        ```

4. **Create the database and tables**:
    ```bash
    mysql -u root -p < db/schema.sql
    ```

5. **Seed the database with initial data**:
    ```bash
    node seeds/index.js
    ```

## Usage

1. **Start the server**:
    ```bash
    node server.js
    ```

2. **The API will be running on**:
    `http://localhost:3001`

## Endpoints

### Categories

- **GET /api/categories**: Get all categories
- **GET /api/categories/:id**: Get a category by ID
- **POST /api/categories**: Create a new category
  - Request body should include:
    ```json
    {
      "category_name": "New Category"
    }
    ```
- **PUT /api/categories/:id**: Update a category by ID
  - Request body should include:
    ```json
    {
      "category_name": "Updated Category"
    }
    ```
- **DELETE /api/categories/:id**: Delete a category by ID

### Products

- **GET /api/products**: Get all products
- **GET /api/products/:id**: Get a product by ID
- **POST /api/products**: Create a new product
  - Request body should include:
    ```json
    {
      "product_name": "New Product",
      "price": 29.99,
      "stock": 100,
      "category_id": 1,
      "tagIds": [1, 2, 3]
    }
    ```
- **PUT /api/products/:id**: Update a product by ID
  - Request body can include:
    ```json
    {
      "product_name": "Updated Product",
      "price": 39.99,
      "stock": 150,
      "category_id": 1,
      "tagIds": [1, 2, 3]
    }
    ```
- **DELETE /api/products/:id**: Delete a product by ID

### Tags

- **GET /api/tags**: Get all tags
- **GET /api/tags/:id**: Get a tag by ID
- **POST /api/tags**: Create a new tag
  - Request body should include:
    ```json
    {
      "tag_name": "New Tag"
    }
    ```
- **PUT /api/tags/:id**: Update a tag by ID
  - Request body should include:
    ```json
    {
      "tag_name": "Updated Tag"
    }
    ```
- **DELETE /api/tags/:id**: Delete a tag by ID

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your changes.

## License

This project is licensed under the MIT License.
