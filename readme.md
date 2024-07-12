# E-Commerce Backend

This is an e-commerce backend application built using Node.js, Express.js, Sequelize, and PostgreSQL. The application provides RESTful APIs for managing categories, products, and tags, allowing CRUD operations on each entity.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
  - [Categories](#categories)
  - [Products](#products)
  - [Tags](#tags)
- [Database Models](#database-models)
- [Environment Variables](#environment-variables)
- [Troubleshooting](#troubleshooting)
- [License](#license)
- [Contact Info](#contact-info)
- [Video](#video)

## Installation

### Prerequisites

- Node.js
- PostgreSQL
- npm or yarn

### Steps

1. Clone the repository:

```bash
git clone https://github.com/B1LLYBAGZ/e-commerce-backend.git
cd e-commerce-backend
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Set up the PostgreSQL database:

- Create a new PostgreSQL database.
- Create a `.env` file in the root directory and add your database credentials (see [Environment Variables](#environment-variables)).

4. Create the database schema and seed the database:

```bash
npm run seed
```

5. Start the server:

```bash
nodemon server.js
# or
node server.js
```

## Usage

### Running the Server

To start the server, run:

```bash
node server.js
# or, to use nodemon for automatic restarts:
nodemon server.js
```

The server will start on `http://localhost:3001`.

### Testing the API Endpoints

You can use tools like Insomnia or Postman to test the API endpoints. The endpoints are detailed below.

## API Endpoints

### Categories

#### Get All Categories

- **URL:** `/api/categories`
- **Method:** `GET`
- **Description:** Retrieve a list of all categories.

#### Get Category by ID

- **URL:** `/api/categories/:id`
- **Method:** `GET`
- **Description:** Retrieve a category by its ID.

#### Create Category

- **URL:** `/api/categories`
- **Method:** `POST`
- **Description:** Create a new category.
- **Request Body:**
  ```json
  {
    "category_name": "New Category"
  }
  ```

#### Update Category

- **URL:** `/api/categories/:id`
- **Method:** `PUT`
- **Description:** Update a category by its ID.
- **Request Body:**
  ```json
  {
    "category_name": "Updated Category"
  }
  ```

#### Delete Category

- **URL:** `/api/categories/:id`
- **Method:** `DELETE`
- **Description:** Delete a category by its ID.

### Products

#### Get All Products

- **URL:** `/api/products`
- **Method:** `GET`
- **Description:** Retrieve a list of all products.

#### Get Product by ID

- **URL:** `/api/products/:id`
- **Method:** `GET`
- **Description:** Retrieve a product by its ID.

#### Create Product

- **URL:** `/api/products`
- **Method:** `POST`
- **Description:** Create a new product.
- **Request Body:**
  ```json
  {
    "product_name": "New Product",
    "price": 19.99,
    "stock": 100,
    "category_id": 1,
    "tagIds": [1, 2]
  }
  ```

#### Update Product

- **URL:** `/api/products/:id`
- **Method:** `PUT`
- **Description:** Update a product by its ID.
- **Request Body:**
  ```json
  {
    "product_name": "Updated Product",
    "price": 24.99,
    "stock": 40,
    "category_id": 1,
    "tagIds": [1, 3]
  }
  ```

#### Delete Product

- **URL:** `/api/products/:id`
- **Method:** `DELETE`
- **Description:** Delete a product by its ID.

### Tags

#### Get All Tags

- **URL:** `/api/tags`
- **Method:** `GET`
- **Description:** Retrieve a list of all tags.

#### Get Tag by ID

- **URL:** `/api/tags/:id`
- **Method:** `GET`
- **Description:** Retrieve a tag by its ID.

#### Create Tag

- **URL:** `/api/tags`
- **Method:** `POST`
- **Description:** Create a new tag.
- **Request Body:**
  ```json
  {
    "tag_name": "New Tag"
  }
  ```

#### Update Tag

- **URL:** `/api/tags/:id`
- **Method:** `PUT`
- **Description:** Update a tag by its ID.
- **Request Body:**
  ```json
  {
    "tag_name": "Updated Tag"
  }
  ```

#### Delete Tag

- **URL:** `/api/tags/:id`
- **Method:** `DELETE`
- **Description:** Delete a tag by its ID.

## Database Models

### Category

- **id**: Integer, primary key, auto-increment
- **category_name**: String, not null

### Product

- **id**: Integer, primary key, auto-increment
- **product_name**: String, not null
- **price**: Decimal, not null, validates as decimal
- **stock**: Integer, not null, default value of 10, validates as numeric
- **category_id**: Integer, references `Category` model's `id`

### Tag

- **id**: Integer, primary key, auto-increment
- **tag_name**: String

### ProductTag

- **id**: Integer, primary key, auto-increment
- **product_id**: Integer, references `Product` model's `id`
- **tag_id**: Integer, references `Tag` model's `id`

## Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```
DB_NAME=your_database_name
DB_USER=your_postgres_username
DB_PASSWORD=your_postgres_password
DB_HOST=localhost
DB_PORT=5432
```

## Troubleshooting

### Common Errors

- **SequelizeForeignKeyConstraintError**: Ensure that referenced foreign keys exist in the respective tables.
- **Validation Errors**: Ensure that the data types and constraints match the model definitions.

### Checking Server Logs

Monitor the server logs for detailed error messages. This can help in identifying and fixing issues.

## License

This project is licensed under the MIT License.

## Contact Info

For any questions or support, please contact:

- **Email**: 098williamhogan@gmail.com
- **GitHub**: [B1LLYBAGZ](https://github.com/B1LLYBAGZ)

## Video

[Untitled_ Jul 11, 2024 5_58 PM.webm](https://github.com/user-attachments/assets/6c6f999f-2047-4e70-bf2d-52b76b1028a2)
