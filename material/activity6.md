# Using a Third-Party Module with npm

## Part 1

In this lab, we'll walk through the process of installing a third-party module (`funct-dates`) using npm and using it in a Node.js project. We'll also initialize a new Node.js project using `npm init -y` for managing dependencies.

#### Step 1: Initialize a Node.js Project

1. Open your terminal or command prompt.

2. Create a new directory for your project:
   ```bash
   mkdir my-node-project
   cd my-node-project
   ```

3. Initialize a new Node.js project with a `package.json` file using the `-y` flag to accept all default settings:
   ```bash
   npm init -y
   ```

#### Step 2: Install the Third-Party Module

1. Install the `npm install date-fns` module using npm:
   ```bash
   npm install date-fns
   ```

   This command will download and install the `date-fns` module into the `node_modules` directory of your project and add it as a dependency in your `package.json` file.

#### Step 3: Write Code to Use the Module

1. Create a new JavaScript file named `app.js` in your project directory.

2. Write code to use the `date-fns` module in `app.js`:
   ```javascript
      // Import specific functions from date-fns
   const { format, addDays } = require('date-fns');

   // Get the current date
   const currentDate = new Date();

   // Format the current date
   const formattedDate = format(currentDate, 'MMMM dd, yyyy');
   console.log('Formatted Date:', formattedDate);

   // Add 7 days to the current date
   const futureDate = addDays(currentDate, 7);
   console.log('Future Date:', format(futureDate, 'MMMM dd, yyyy'));
   ```

#### Step 4: Run the Application

1. Run your Node.js application using the following command:
   ```bash
   node app.js
   ```

   This command will execute the `app.js` file and display the formatted date in the console.

#### Step 5: Additional Steps (Optional)

1. If you plan to share your project with others or deploy it to a production environment, you may want to include the `node_modules` directory in your `.gitignore` file to prevent it from being tracked by version control.

   Example `.gitignore` file:
   ```
   node_modules/
   ```

2. If you want to share your project with others, you can provide instructions for them to install dependencies using the following command:
   ```bash
   npm install
   ```

   This command will install all dependencies listed in the `package.json` file.

Congratulations! You've successfully installed and used a third-party module (`date-fns`) in a Node.js project using npm. You can explore further and use other modules available on npm to enhance your Node.js projects.

## Part 2: Building a "Hello World" Application using Express.js

Express.js is a popular web application framework for Node.js that simplifies the process of building web applications and APIs. In this lab, we'll create a simple "Hello World" application using Express.js and explain each step involved.

#### Step 1: Setting up the Project

1. **Install Node.js and npm**: Before starting, ensure that you have Node.js and npm installed on your system. You can download and install them from the official Node.js website: [Node.js Downloads](https://nodejs.org/en/download/).

2. **Create a Project Directory**: Create a new directory for your project. You can name it whatever you like. For example:
   ```bash
   mkdir express-hello-world
   cd express-hello-world
   ```

3. **Initialize npm**: Run the following command to initialize npm and create a `package.json` file for managing dependencies:
   ```bash
   npm init -y
   ```

4. **Install Express**: Install Express.js as a project dependency using npm:
   ```bash
   npm install express
   ```

#### Step 2: Writing the Code

Create a new file named `app.js` (or any other preferred name) in your project directory and write the following code:

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

#### Step 3: Understanding the Code

- **Importing Express**: We import the Express.js library using the `require()` function and assign it to the variable `express`.

- **Creating an Express Application**: We create an Express application by calling the `express()` function and store the returned application object in the variable `app`.

- **Defining Routes**: We define a route for handling HTTP GET requests to the root URL (`'/'`). When a GET request is made to this route, Express executes the callback function `(req, res)` where `req` is the request object and `res` is the response object. In this callback function, we use `res.send()` to send the response "Hello World!" back to the client.

- **Starting the Server**: We start the Express server by calling the `listen()` method on the `app` object. The server listens on port `3000` (or any other port specified) for incoming connections. Once the server is running, we log a message to the console indicating that the server is listening on the specified port.

#### Step 4: Running the Application

To run the Express application, execute the following command in your project directory:

```bash
node app.js
```

You should see the message "Example app listening on port 3000" logged to the console, indicating that the server is running. You can then open your web browser and navigate to `http://localhost:3000` to see the "Hello World!" message displayed in the browser.

Congratulations! You've successfully created and run a "Hello World" application using Express.js. You can now explore further and build more complex web applications and APIs using Express.js.


------
## Push to GitHub

**Local Git Repository**

1. Make the project directory a Git repository by running:

```bash
git init
```

2. Make sure that you have the `.gitignore` file and exclude the `node_modules` directory from version control:

```
node_modules/
``` 

3. Stage all the changes:

```bash
git add .
```

4. Commit the changes:

```bash
git commit -m  "Add message here"

```

**Part 3: Push to GitHub**

1. Create a new repository on GitHub:

- Go to the GitHub website .
- Click on the plus sign icon in the top right corner of the page, and then select "New repository."
- Fill in the details for your new repository:
   - Repository name: Choose a name for your new repository.
   - Description (optional): Add a short description to explain the repository's purpose.
   - Visibility: Choose between "Public" or "Private," depending on who should have access.
   - Do not initialize the repository with a `README` file or a `.gitignore` file.
- Click the "Create repository" button to create your new repository.


2. Link your local repository to the GitHub repository:

```bash
git remote add origin <GitHub Repository URL>
```

3. Push your local repository to GitHub:

```bash
git push -u origin main
```

4. Refresh the GitHub repository page to see your changes.

