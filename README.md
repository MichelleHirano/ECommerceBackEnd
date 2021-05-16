# ECommerceBackEnd

### Description

Internet retail, also known as e-commerce, is the largest sector of the electronics industry, having generated an estimated US$29 trillion in 2017 (Source: United Nations Conference on Trade and Development). E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. Due to the prevalence of these platforms, developers should understand the fundamental architecture of e-commerce sites.

Your challenge is to build the back end for an e-commerce site. You’ll take a working Express.js API and configure it to use Sequelize to interact with a MySQL database.




### App Demo

- Create Schema and Seed data

![Alt Text](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/gifs/1.gif)
[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/schema-seed-startserver.webm)

- GET routes to return all categories, all products

![Alt Text](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/gifs/2.gif)
[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/get%20all.mp4)

- GET routes to return a single category, a single product, and a single tag

![Alt Text](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/gifs/3.gif)
[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/single%20route.mp4)

- POST, PUT, and DELETE routes for Categories

[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/postputdelete_categories.mp4)

- POST, PUT, and DELETE routes for Products

[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/postputdelete_products.mp4)

- POST, PUT, and DELETE routes for Tags

[Video](https://github.com/MichelleHirano/ECommerceBackEnd/blob/7588bd341d2b09de64ec2d3f2913d7d31bd391b6/tograde/videos/postputdelete_tags.mp4)

### User Story

```text
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

### Acceptance Criteria

```text
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database
```

### Database Models

- `Category`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `category_name`
        - String
        - Doesn't allow null values

- `Product`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `product_name`
        - String
        - Doesn't allow null values

    - `price`
        - Decimal
        - Doesn't allow null values
        - Validates that the value is a decimal

    - `stock`
        - Integer
        - Doesn't allow null values
        - Set a default value of 10
        - Validates that the value is numeric

    - `category_id`
        - Integer
        - References the category model's id

- `Tag`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `tag_name`
        - String

- `ProductTag`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `product_id`
        - Integer
        - References the product model's id

    - `tag_id`
        - Integer
        - References the tag model's id

### Associations

*You'll need to execute association methods on your Sequelize models to create the following relationships between them:*

- Product belongs to Category, as a category can have multiple products but a product can only belong to one category.

- Category has many Product models.

- Product belongs to many Tag models. Using the ProductTag through model, allow products to have multiple tags and tags to have many products.

- Tag belongs to many Product models.

### Instructions on how to run the app

- Add a .env file to the root of the app with the following details

```text
DB_NAME='ecommerce_db'
DB_USER='root'
DB_PW='xxx'
```
