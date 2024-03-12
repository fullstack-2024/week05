# MongoDB CRUD Operations Lab

In this activity, you will learn how to perform CRUD (Create, Read, Update, Delete) operations using MongoDB with Node.js. Follow the step-by-step instructions below to set up the lab environment and perform each operation.

## Part 1: Instructions

### Prerequisites

Before you begin, ensure that you have MongoDB installed and running on your local machine.

> Follow these [instructions](./mongodb-install.md)

### Step 1: Set Up the Project

1. Create a new directory for your project.
2. Open a terminal and navigate to the project directory.
3. Run `npm init -y` to initialize a new Node.js project.

### Step 2: Install Dependencies

Install the `mongodb` package, which provides the necessary tools for interacting with MongoDB.

```bash
npm install mongodb
```

### Step 3: Write the Code

Create a JavaScript file, such as `crud.js`, and paste the provided code into it:

```javascript
const { MongoClient } = require('mongodb');

// Connection URI
const uri = 'mongodb://localhost:27017';

// Database Name
const dbName = 'mydatabase'; // Replace with your database name

// Collection Name
const collectionName = 'mycollection'; // Replace with your collection name

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
        const insertResult = await collection.insertOne({ name: "John", age: 30, city: "New York" });
        console.log(`Document inserted with id: ${insertResult.insertedId}`);

        // Find documents
        const documents = await collection.find({}).toArray();
        console.log("All documents:");
        console.log(documents);

        // Update a document
        const updateResult = await collection.updateOne({ name: "John" }, { $set: { age: 35 } });
        console.log(`${updateResult.modifiedCount} document(s) updated.`);

        // Find updated document
        const updatedDocument = await collection.findOne({ name: "John" });
        console.log("Updated document:");
        console.log(updatedDocument);

        // Delete a document
        const deleteResult = await collection.deleteOne({ name: "John" });
        console.log(`${deleteResult.deletedCount} document(s) deleted.`);

    } finally {
        // Close the connection
        await client.close();
    }
}

main().catch(console.error);
```

### Step 4: Run the Script

Save the `crud.js` file. Open a terminal, navigate to your project directory, and run the following command:

```bash
node crud.js
```

This will execute the script, performing CRUD operations on the MongoDB database as described in the code.


## Explanation

Let's break down the steps involved in setting up the lab and executing the provided MongoDB CRUD operations code:

### Step 1: Set Up the Project

In this step, we prepare the directory structure for our project and initialize a new Node.js project.

1. **Create a new directory**: We create a new directory to contain our project files.
2. **Navigate to the project directory**: Using the terminal, we change our current directory to the newly created project directory.
3. **Initialize a new Node.js project**: We use the `npm init -y` command to initialize a new Node.js project with default settings. This creates a `package.json` file in the project directory, which stores metadata about the project and its dependencies.

### Step 2: Install Dependencies

We install the `mongodb` package, which provides the necessary tools for interacting with MongoDB.

1. **Install `mongodb` package**: We use the `npm install mongodb` command to install the `mongodb` package. This command downloads the package from the npm registry and adds it as a dependency to our project.

### Step 3: Write the Code

We create a JavaScript file, `crud.js`, and paste the provided MongoDB CRUD operations code into it.

1. **Create `crud.js` file**: We create a new JavaScript file named `crud.js` in our project directory.
2. **Paste the provided code**: We copy the provided code snippet, which contains the MongoDB CRUD operations logic, into the `crud.js` file.

### Step 4: Run the Script

We execute the `crud.js` script to perform the MongoDB CRUD operations.

1. **Save the `crud.js` file**: We save the changes made to the `crud.js` file.
2. **Open a terminal**: Using the terminal, we navigate to our project directory where the `crud.js` file is located.
3. **Run the script**: We use the `node crud.js` command to execute the `crud.js` script. This command runs the Node.js interpreter, which executes the JavaScript code in the `crud.js` file.
4. **View the output**: The script performs CRUD operations on the MongoDB database as described in the code. We can view the output in the terminal, which includes messages indicating the success of each operation and any retrieved documents.

## Conclusion

Congratulations! You have completed the MongoDB CRUD operations lab. You have learned how to connect to a MongoDB server, insert documents, retrieve documents, update documents, and delete documents using Node.js and the `mongodb` package. These skills are essential for building robust applications that interact with MongoDB databases.