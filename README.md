# Social Network API

## Overview
This API powers a social media network, allowing you to manage users, thoughts, reactions, and friendships. It uses a NoSQL database (MongoDB) to handle large amounts of unstructured data efficiently. This guide will help you get started with setting up, using, and testing the API.

## Features
- **Manage Users**: Create, update, retrieve, and delete user profiles.
- **Manage Thoughts**: Create, update, retrieve, and delete thoughts.
- **Manage Reactions**: Add and delete reactions to thoughts.
- **Manage Friendships**: Add and remove friends from user profiles.

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v16 or later)
- [MongoDB](https://www.mongodb.com/) (Make sure MongoDB is installed and running)
- [Insomnia](https://insomnia.rest/) or any other API client for testing

### Installation

1. **Clone the Repository**

    ```sh
    git clone https://github.com/your-username/social-network-api.git
    cd social-network-api
    ```

2. **Install Dependencies**

    ```sh
    npm install
    ```

3. **Set Up Environment Variables**

    Create a `.env` file in the root directory of the project and add the following environment variable:

    ```env
    MONGODB_URI=mongodb://localhost:27017/social-network
    ```

    Replace `mongodb://localhost:27017/social-network` with your MongoDB connection string if necessary.

4. **Start the Server**

    ```sh
    npm start
    ```

    The server will start and listen on port `3000` by default. You can adjust the port in your configuration if needed.

## API Routes

### Users

- **GET /api/users**
  
  Retrieve a list of all users.

- **GET /api/users/:id**
  
  Retrieve a specific user by ID.

- **POST /api/users**
  
  Create a new user.

- **PUT /api/users/:id**
  
  Update a user by ID.

- **DELETE /api/users/:id**
  
  Delete a user by ID.

### Thoughts

- **GET /api/thoughts**
  
  Retrieve a list of all thoughts.

- **GET /api/thoughts/:id**
  
  Retrieve a specific thought by ID.

- **POST /api/thoughts**
  
  Create a new thought.

- **PUT /api/thoughts/:id**
  
  Update a thought by ID.

- **DELETE /api/thoughts/:id**
  
  Delete a thought by ID.

### Reactions

- **POST /api/thoughts/:thoughtId/reactions**
  
  Add a reaction to a specific thought.

- **DELETE /api/thoughts/:thoughtId/reactions/:reactionId**
  
  Delete a reaction from a specific thought.

### Friendships

- **POST /api/users/:userId/friends/:friendId**
  
  Add a friend to a user's friend list.

- **DELETE /api/users/:userId/friends/:friendId**
  
  Remove a friend from a user's friend list.

## Testing the API

Use [Insomnia](https://insomnia.rest/) or any other API client to test the routes. For each route, you can perform CRUD operations and ensure that the data is being handled correctly. 

### Example Insomnia Collections

- **Users Collection**: Includes requests to create, read, update, and delete users.
- **Thoughts Collection**: Includes requests to create, read, update, and delete thoughts.
- **Reactions Collection**: Includes requests to add and delete reactions.
- **Friendships Collection**: Includes requests to add and remove friends.

## Troubleshooting

- **Connection Refused Error**: Ensure MongoDB is running and that the `MONGODB_URI` environment variable is correctly set.
- **Validation Errors**: Check the API documentation for required fields and formats.
- **Server Issues**: Review logs for errors and ensure all dependencies are installed.
