# MongoDB

## Part 1: MongoDB Insertion

In this part, you will learn how to insert documents into a MongoDB database using Node.js. We will guide you step by step to create a script that connects to a MongoDB server, inserts documents into a collection, and closes the connection.

## Prerequisites

Before you start, ensure you have the following:

- Node.js installed on your machine.
- MongoDB installed and running locally on your machine.

> Follow these [instructions](./mongodb-install.md)

## Step 1: Set Up the Project

1. Create a new directory for your project.
2. Open a terminal and navigate to the project directory.
3. Run `npm init -y` to initialize a new Node.js project.

## Step 2: Install Dependencies

We will be using the `mongodb` package to interact with MongoDB.

Run the following command in your terminal:

```bash
npm install mongodb
```

## Step 3: Write the Code

Create a new JavaScript file, for example, `insertion.js`, and paste the following code into it:

```javascript
const { MongoClient } = require("mongodb");

// Connection URI
const uri = "mongodb://localhost:27017";

// Database Name
const dbName = "blog";

// Collection Name
const collectionName = "posts";

// Create a new MongoClient
const client = new MongoClient(uri);

async function main() {
  try {
    // Connect the client to the server
    await client.connect();
    console.log("Connected successfully to server");

    const database = client.db(dbName);
    const collection = database.collection(collectionName);

    // Insert a document
    const insertResult1 = await collection.insertOne({
      title: "Post Title 1a",
      body: "Body of post 1a",
      category: "News",
      likes: 1,
      tags: ["news", "events"],
      date: new Date(),
    });
    console.log(`Document inserted with id: ${insertResult1.insertedId}`);

    // Insert another document
    const insertResult2 = await collection.insertOne({
      title: "Post Title 1b",
      body: "Body of post 1b",
      category: "Tech",
      likes: 3,
      tags: ["Tech", "events"],
      date: new Date(),
    });
    console.log(`Document inserted with id: ${insertResult2.insertedId}`);
  } finally {
    // Close the connection
    await client.close();
    console.log("Connection closed");
  }
}

main().catch(console.error);
```

## Step 4: Run the Script

Save the `insertion.js` file. Open a terminal, navigate to your project directory, and run the following command:

```bash
node insertion.js
```

This will execute the script, connecting to your local MongoDB server, inserting documents into the `posts` collection in the `blog` database, and then closing the connection.

## Conclusion

Congratulations! You have successfully created a Node.js script to insert documents into a MongoDB database. You can now use this knowledge to perform more advanced operations with MongoDB in your Node.js projects.


## Part 2: 

Follow the step by step by step instructions and write a similar code to part for the `ecommerce` database

### Step 1: Import MongoDB Module

```javascript
const { MongoClient } = require("mongodb");
```

This line imports the `MongoClient` class from the `mongodb` module. This class allows us to interact with MongoDB from our Node.js application.

### Step 2: Define Connection URI

```javascript
const uri = "mongodb://localhost:27017";
```

Here, we define the connection URI for our MongoDB server. This URI specifies the protocol (`mongodb://`), the host (`localhost`), and the port (`27017`) where MongoDB is running. Adjust the URI according to your MongoDB setup.

### Step 3: Define Database and Collection Names

```javascript
const dbName = "ecommerce";
const collectionName = "products";
```

We specify the name of the database (`ecommerce`) and the collection (`products`) within that database where we want to insert documents.

### Step 4: Create a MongoClient Instance

```javascript
const client = new MongoClient(uri);
```

Here, we create a new instance of the `MongoClient` class, passing in the connection URI as a parameter. This instance will be used to connect to the MongoDB server.

### Step 5: Connect to the MongoDB Server

```javascript
await client.connect();
```

Using the `connect()` method, we establish a connection to the MongoDB server specified by the connection URI. This step is essential before performing any operations on the database.

### Step 6: Access the Database and Collection

```javascript
const database = client.db(dbName);
const collection = database.collection(collectionName);
```

Once connected, we access the desired database (`blog`) using the `db()` method and the specified database name. Then, we access the desired collection (`posts`) within that database using the `collection()` method and the specified collection name.

### Step 7: Insert Documents into the Collection

```javascript
await collection.insertOne({ /* document data */ });
```

We use the `insertOne()` method to insert a single document into the collection. In the provided code, we insert two documents into the `products` collection.

    ```js
    // Insert a document (car product)
    await collection.insertOne({
      name: "Tesla Model S",
      brand: "Tesla",
      type: "Car",
      price: 79999,
      colors: ["Red", "Blue", "White"],
      dateAdded: new Date(),
    });
    console.log("Car product inserted");

    // Insert another document (car product)
    const insertResult = await collection.insertOne({
      name: "BMW X5",
      brand: "BMW",
      type: "Car",
      price: 69999,
      colors: ["Black", "Silver", "Grey"],
      dateAdded: new Date(),
    });
    console.log(`Car product inserted with id: ${insertResult.insertedId}`);
    ```

### Step 8: Close the Connection

```javascript
await client.close();
```

Finally, we close the connection to the MongoDB server using the `close()` method. It's important to close the connection after completing our operations to free up resources and maintain connection management.

### try ... catch ... finally

Let's discuss the role of the `try`, `catch`, and `finally` blocks in the provided code snippet:

### `try` Block:

The `try` block encapsulates the code where potential errors may occur. In this case, it contains the main logic of the program, including connecting to the MongoDB server, performing database operations, and any other asynchronous tasks.

### `finally` Block:

The `finally` block is executed regardless of whether an error occurred within the `try` block or not. It's commonly used for cleanup tasks or releasing resources. In this snippet, it ensures that the MongoDB client connection is closed after the execution of the main logic, regardless of whether any errors occurred.



```js
async function main() {
  try {
    // codehere
	
  } finally {
    // Close the connection
    await client.close();
  }
}

main().catch(console.error);
```

### Conclusion

The code establishes a connection to a MongoDB server, accesses a specific database and collection, inserts documents into the collection, and then closes the connection. These are the essential steps involved in interacting with MongoDB using Node.js.


<!-- 
The combination of the `try` block to handle potential errors and the `finally` block to ensure cleanup and resource management ensures the robustness and reliability of the application. It's a common pattern in asynchronous code to handle errors gracefully and ensure proper cleanup of resources. Additionally, the `.catch()` method at the end of the `main()` function catches any errors that occurred during the execution of the asynchronous code and logs them to the console for debugging purposes.
-->
