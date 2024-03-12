# Custom Node module 


> If you do not have Node.js and npm installed, follow this guideline [here](./node.md).

> Create a new directory named `week5-lab4` to organize your work for this activity.


### Step 1: Create a JavaScript File

Create a JavaScript file (e.g., `custom-functions.js`) in the project directory

### Step 2: Write the Functions in the JavaScript File

1. In `custom-functions.js`, define these  functions:

   ```javascript
   // 1.
   function cube(x) {
     return x * x * x;
   }

   // 2.
   function fullName(first, last) {
     return first + " " + last;
   }

   // 3.
   function power(base, exp) {
     if (exp === 0) {
       return 1;
     }
     return base * power(base, exp - 1);
   }

   // 4.
   function sumCubes(numbers) {
     var total = 0;
     for (var i = 0; i < numbers.length; i++) {
       total = total + cube(numbers[i]);
     }
     return total;
   }

   module.exports = {
     cube,
     fullName,
     power,
     sumCubes,
   };
   ```

In this file, we've defined the four functions and used `module.exports` to export them as an object with named properties.

### Step 3: Use the Module in Another File

1. To test your module, you can create another JavaScript file (e.g., `test.js`) in the project directory

2. In `test.js`, import your custom module and use the exported functions:

   ```javascript
   const customFunctions = require('./custom-functions');

   console.log(customFunctions.cube(3)); // Test the cube function
   console.log(customFunctions.fullName('John', 'Doe')); // Test the fullName function
   console.log(customFunctions.power(2, 3)); // Test the power function
   console.log(customFunctions.sumCubes([1, 2, 3])); // Test the sumCubes function
   ```

### Step 4: Run the Test File

In your terminal, run the test file to check if your custom module is working as expected:

```bash
node test.js
```

You've now created a custom Node module that exports the specified functions. You can use this module in other Node.js projects by importing it using `require`.


------
## Push to GitHub

**Local Git Repository**

1. Make the project directory a Git repository by running:

```bash
git init
```

<!-- 2. Make sure that you have the `.gitignore` file and exclude the `node_modules` directory from version control:

```
node_modules/
``` -->

2. Stage all the changes:

```bash
git add .
```

3. Commit the changes:

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

