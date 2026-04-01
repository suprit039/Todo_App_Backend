# Todo App Backend

This is the backend service for the Todo Application, built using Node.js, Express, and MongoDB. It provides a RESTful API to manage tasks representing a to-do list.

## Technologies Used

* **Node.js**: JavaScript runtime environment.
* **Express.js**: Fast, unopinionated, minimalist web framework for Node.js.
* **MongoDB & Mongoose**: NoSQL database and Object Data Modeling (ODM) library.
* **Dotenv**: Module to load environment variables from a `.env` file.

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

* Node.js installed on your local machine.
* A MongoDB database URI (either local or MongoDB Atlas).

### Installation

1. Clone the repository or download the project files.
2. Navigate to the project directory in your terminal:
   ```bash
   cd Todo_App_backend
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```
4. Create a `.env` file in the root directory and add your environment variables:
   ```env
   PORT=5000
   MONGO_URI=your_mongodb_connection_string
   ```

### Running the Application

To start the server in development mode (using nodemon for hot-reloading):

```bash
npm run dev
```

To start the server normally:

```bash
npm start
```

The server will run on `http://localhost:5000` by default.

## Postman API Testing: Requests and Responses

All APIs have been tested using Postman. Below are the details of the requests and the typical JSON responses you will receive from the endpoints:

### 1. Create a Todo
* **Endpoint:** `POST /api/todos`
* **Request Body:**
  ```json
  {
    "title": "Learn Node.js",
    "status": "pending"
  }
  ```
* **Success Response (201 Created):**
  ```json
  {
    "success": true,
    "data": {
      "title": "Learn Node.js",
      "status": "pending",
      "_id": "67cd8cb600a9d16fdf618355",
      "createdAt": "2026-04-01T21:23:02.670Z",
      "updatedAt": "2026-04-01T21:23:02.670Z",
      "__v": 0
    }
  }
  ```

### 2. Retrieve All Todos
* **Endpoint:** `GET /api/todos`
* **Request Body:** None
* **Success Response (200 OK):**
  ```json
  {
    "success": true,
    "total": 1,
    "page": 1,
    "pages": 1,
    "data": [
      {
        "_id": "67cd8cb600a9d16fdf618355",
        "title": "Learn Node.js",
        "status": "pending",
        "createdAt": "2026-04-01T21:23:02.670Z",
        "updatedAt": "2026-04-01T21:23:02.670Z",
        "__v": 0
      }
    ]
  }
  ```

### 3. Retrieve a Single Todo By ID
* **Endpoint:** `GET /api/todos/:id`
* **Request Body:** None
* **Success Response (200 OK):**
  ```json
  {
    "success": true,
    "data": {
      "_id": "67cd8cb600a9d16fdf618355",
      "title": "Learn Node.js",
      "status": "pending",
      "createdAt": "2026-04-01T21:23:02.670Z",
      "updatedAt": "2026-04-01T21:23:02.670Z",
      "__v": 0
    }
  }
  ```

### 4. Update an Existing Todo
* **Endpoint:** `PUT /api/todos/:id`
* **Request Body:**
  ```json
  {
    "title": "Learn Node.js Completely",
    "status": "completed"
  }
  ```
* **Success Response (200 OK):**
  ```json
  {
    "success": true,
    "data": {
      "_id": "67cd8cb600a9d16fdf618355",
      "title": "Learn Node.js Completely",
      "status": "completed",
      "createdAt": "2026-04-01T21:23:02.670Z",
      "updatedAt": "2026-04-01T21:23:03.034Z",
      "__v": 0
    }
  }
  ```

### 5. Delete a Todo
* **Endpoint:** `DELETE /api/todos/:id`
* **Request Body:** None
* **Success Response (200 OK):**
  ```json
  {
    "success": true,
    "message": "Todo deleted successfully"
  }
  ```
