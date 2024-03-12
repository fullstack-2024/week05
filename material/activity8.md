# MongoDB InsertMany Lab

In this lab, you will learn how to use the `insertMany()` method in MongoDB to insert multiple documents into a collection. Follow the step-by-step instructions below to set up the lab environment and execute the provided code.

## Part 1: insertMany

### Prerequisites

Before you begin, ensure that you have MongoDB installed and running on your local machine.

> Follow these [instructions](./mongodb-install.md)

### Step 1: Set Up the Project

1. Create a new directory for your project.
2. Open a terminal and navigate to the project directory.
3. Run `npm init -y` to initialize a new Node.js project.

## Step 2: Install Dependencies

We will be using the `mongodb` package to interact with MongoDB.

Run the following command in your terminal:

```bash
npm install mongodb
```

### Step 3: Write the Code

Create a JavaScript file, such as `insertMany.js`, and paste the provided code into it.

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

    // Insert multiple documents
    await collection.insertMany([
      {
        title: "Post Title 2",
        body: "Body of post.",
        category: "Event",
        likes: 2,
        tags: ["news", "events"],
        date: new Date(),
      },
      {
        title: "Post Title 3",
        body: "Body of post.",
        category: "Technology",
        likes: 3,
        tags: ["Tech", "events"],
        date: new Date(),
      },
      {
        title: "Post Title 4",
        body: "Body of post.",
        category: "Event",
        likes: 4,
        tags: ["news", "events"],
        date: new Date(),
      },
    ]);
    console.log("Inserted 3 Documents");
  } finally {
    // Close the connection
    await client.close();
  }
}

main().catch(console.error);
```

### Step 4: Run the Script

Save the `insertMany.js` file. Open a terminal, navigate to your project directory, and run the following command:

```bash
node insertMany.js
```

This will execute the script, inserting multiple documents into the MongoDB collection as described in the code.

### Conclusion

Congratulations! You have completed the MongoDB InsertMany lab. You have learned how to use the `insertMany()` method to efficiently insert multiple documents into a MongoDB collection. This skill is essential for efficiently populating databases with data in MongoDB.

## Part 2: Find All Documents

In this part, you will learn how to use the `find()` method to retrieve all documents from a MongoDB collection.

### Instructions

1. **Set Up the Project**: Create a new directory for your project and initialize a new Node.js project using `npm init -y`.

2. **Install Dependencies**: Install the `mongodb` package by running `npm install mongodb`.

3. **Write the Code**: Create a JavaScript file, such as `find-all.js`, and paste the following code:

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

    // Find documents
    const documents = await collection.find({}).toArray();
    console.log("All documents:");
    console.log(documents);
  } finally {
    // Close the connection
    await client.close();
  }
}

main().catch(console.error);
```

4. **Run the Script**: Save the file and execute the script using `node find-all.js`.

## Part 3: Find One Document

In this part, you will learn how to use the `findOne()` method to retrieve a single document from a MongoDB collection.

### Instructions

1. **Write the Code**: Create another JavaScript file, such as `find-one.js`, and paste the following code:

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

    // Find a single document
    const document = await collection.findOne({});
    console.log("First document:");
    console.log(document);
  } finally {
    // Close the connection
    await client.close();
  }
}

main().catch(console.error);
```

2. **Run the Script**: Save the file and execute the script using `node find-one.js`.

### Conclusion

By following the steps in both parts of this lab, you have learned how to use the `find()` and `findOne()` methods to fetch documents from a MongoDB collection using Node.js. Understanding these operations is essential for querying and retrieving data from MongoDB databases in your applications.