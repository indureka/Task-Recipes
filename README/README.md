# Recipe Manager

# Overview

Recipe Manager is a CRUD (Create, Read, Update, Delete) application built with Node.js, Express.js, and Mongoose to manage recipes. It follows the MVC architecture and provides a RESTful API for managing recipe data.

The project is integrated with MongoDB for data storage and includes robust error handling and input validation.

# Features

Create Recipe: Add a new recipe.

Retrieve Recipes: Fetch all recipes.

Fetch a single recipe by its ID.

Update Recipe: Modify an existing recipe using its ID.

Delete Recipe: Remove a recipe using its ID.


# Technologies Used

Node.js: Backend runtime environment.
Express.js: Web framework for handling routes and middleware.
Mongoose: Object Data Modeling (ODM) library for MongoDB.
MongoDB: Database for storing recipe data.
dotenv: To manage environment variables.
Postman: For API testing.
Nodemon: For automatic server restarts during development.

Installation and Setup

Clone the repository:

git clone https://github.com/yourusername/recipe-manager.git

cd recipe-manager
Install dependencies:

npm install

Set up environment variables: Create a .env file in the root directory and add:

PORT Number and MONGO_URL

Run the server:

Start the development server:

npm run dev

The server will run on http://localhost:5000.

# API Endpoints
Base URL: http://localhost:5000/api/recipes


1. Create a Recipe

Method: POST
Endpoint: /
Example Request Body:

{
  "title": "Fruit Salad",
  "ingredients": ["apples", "bananas", "oranges"],
  "instructions": "Chop fruits and mix.",
  "cookingTime": 10
}

2. Get All Recipes

Method: GET
Endpoint: /

3. Get a Recipe by ID

Method: GET
Endpoint: /:id

4. Update a Recipe

Method: PUT
Endpoint: /:id

Example Request Body:

{
  "title": "Updated Fruit Salad",
  "ingredients": ["apples", "bananas", "kiwi", "grapes"],
  "instructions": "Mix fruits with honey and lime juice.",
  "cookingTime": 15
}

5. Delete a Recipe

Method: DELETE
Endpoint: /:id

# Testing the API

1. Create a Recipe (POST)

Method: POST
URL: http://localhost:5000/api/recipes

Go to the Body tab, select raw, and choose JSON format.

{
  "title": "Fruit Salad",
  "ingredients": ["apples", "bananas", "oranges"],
  "instructions": "Chop fruits and mix them together.",
  "cookingTime": 10
}


Expected Response:

{
  "message": "Recipe created successfully!",
  "data": {
    "_id": "64b7f6f3c35d6a2d88e9f7f5",
    "title": "Fruit Salad",
    "ingredients": ["apples", "bananas", "oranges"],
    "instructions": "Chop fruits and mix them together.",
    "cookingTime": 10,
    "__v": 0
  }
}


2. Get All Recipes (GET)

Method: GET
URL: http://localhost:5000/api/recipes

Expected Response:

[
  {
    "_id": "64b7f6f3c35d6a2d88e9f7f5",
    "title": "Fruit Salad",
    "ingredients": ["apples", "bananas", "oranges"],
    "instructions": "Chop fruits and mix them together.",
    "cookingTime": 10,
    "__v": 0
  }
]

3. Get a Recipe by ID (GET)

Method: GET
URL: http://localhost:5000/api/recipes/:id
Replace :id with the actual ID of a recipe.

Expected Response:

{
  "_id": "64b7f6f3c35d6a2d88e9f7f5",
  "title": "Fruit Salad",
  "ingredients": ["apples", "bananas", "oranges"],
  "instructions": "Chop fruits and mix them together.",
  "cookingTime": 10,
  "__v": 0
}

4. Update a Recipe (PUT)

Method: PUT
URL: http://localhost:5000/api/recipes/:id
Replace :id with the actual ID of a recipe.

Go to the Body tab, select raw, and choose JSON format.

{
  "title": "Updated Fruit Salad",
  "ingredients": ["apples", "bananas", "kiwi", "grapes"],
  "instructions": "Chop fruits and mix them together with lime juice.",
  "cookingTime": 15
}

Expected Response:

{
  "message": "Recipe updated successfully!",
  "data": {
    "_id": "64b7f6f3c35d6a2d88e9f7f5",
    "title": "Updated Fruit Salad",
    "ingredients": ["apples", "bananas", "kiwi", "grapes"],
    "instructions": "Chop fruits and mix them together with lime juice.",
    "cookingTime": 15,
    "__v": 0
  }
}

5. Delete a Recipe (DELETE)

Method: DELETE
URL: http://localhost:5000/api/recipes/:id
Replace :id with the actual ID of a recipe.

Expected Response:

{
  "message": "Recipe deleted successfully!"
}

#Error Handling:
For invalid IDs or missing fields, the API will return appropriate error messages in JSON format.