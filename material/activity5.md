# Activity 5

In this activity, we will explore Node.js built in modules:`fs` /`os`  and the difference between synchronous  asynchronous operations

> Create a new directory named `week5-lab5` to organize your work for this activity.

## Part 1

In this part, you will explore the Node.js `fs` (File System) and `os` (Operating System) modules to better understand how system calls and file operations work. Additionally, we will discuss the security implications of these operations, emphasizing the importance of proper error handling and security practices.

### Objectives

1. Understand the `fs` and `os` modules in Node.js.
2. Execute system calls and file operations using Node.js.
3. Recognize security implications related to file and system access.


### File System Operations

1. In your project directory, create a JavaScript file (e.g., `sys-calls.js`) where you'll perform the tasks in this lab.

2. Import the `fs` module and perform the following file system operations:
- Create a  `sample.txt` file and add some text to it.
- Read the contents of  `sample.txt` file using `fs.readFile()`. Handle errors appropriately and log the content to the console.

    <details>
    <summary>How to</summary>

    ```javascript
    const fs = require('fs');
    fs.readFile('sample.txt', 'utf8', (err, data) => {
        if (err) {
        console.error('Error reading file:', err);
        } else {
        console.log('File contents:', data);
        }
    });
    ```

    </details>

- Write data to a new file (e.g., `output.txt`) using `fs.writeFile()`. Handle errors and confirm the data has been written.

    <details>
    <summary>How to</summary>

    ```javascript
    fs.writeFile('output.txt', 'This is some sample data.', (err) => {
    if (err) {
    console.error('Error writing file:', err);
    } else {
    console.log('Data written to output.txt');
    }
    });
    ```

- Run your program and observe the results. Discuss the potential security risks involved when reading or writing files and the importance of error handling in these operations.

### Operating System Information

1. Import the `os` module and access various pieces of information about the operating system.

    <details>
    <summary>How to</summary>

    ```javascript
    const os = require('os');
    ```
    </details>

   a. Print the hostname using `os.hostname()` e.g `console.log('Hostname:', os.hostname());`
   b. Display the OS platform with `os.platform()`.
   c. Determine the available CPU cores with `os.cpus()`.

2. Run your program and discuss the types of information that can be accessed through the `os` module. Consider the potential security implications of disclosing such information.


3. Use `fs.writeFile()` to log `os.hostname()`, `os.platform()` and  `os.cpus()`

    <details>
    <summary>How to</summary>

      ```js
      const os = require('os');
      const fs = require('fs');

      const hostname = os.hostname();
      const platform = os.platform();
      const cpus = os.cpus();

      // Logging the information to the console
      console.log('Hostname:', hostname);
      console.log('Platform:', platform);
      console.log('CPU Cores:', cpus.length);

      // Writing the information to a file
      const fileInfo = `
      Hostname: ${hostname}
      Platform: ${platform}
      CPU Cores: ${cpus.length}
      `;

      fs.writeFile('os_info.txt', fileInfo, (err) => {
        if (err) {
          console.error('Error writing file:', err);
          return;
        }
        console.log('Information written to os_info.txt file.');
      });
      ```
    </details>

### Asynchronous operations

In your script, you invoked `fs.readFile()` and `fs.writeFile()`  prior to logging the OS information like `os.platform()`. Explain why the observed output may look as follows:

```sh
Hostname: DESKTOP-DAB97SL
OS Platform: win32
Data written to output.txt
File contents: This is some text
```

<details>
<summary>Explanation</summary>

- **fs.readFile()** and **fs.writeFile()** are asynchronous functions: These file system operations are designed to work asynchronously, which means they don't block the execution of the rest of your code. They initiate file read and write operations in the background and continue with the execution of the subsequent code without waiting for them to complete.

- **Logging with os.platform()**: When you call `os.platform()` to log the information about the operating system, it typically executes immediately since it's a synchronous operation. It provides the OS information in your output.

- **Execution Flow**: Here's the order of execution with the described sequence:

   - The script starts.
   - `fs.readFile()` and `fs.writeFile()` are called. They initiate their respective file operations but don't block the script's execution.
   - Immediately after, `os.platform()` is called, logging the OS information.

- **Potential Output Issues**: The output could have a couple of issues due to the asynchronous nature of file operations:

   - The OS information might be logged before the `fs.readFile()` and `fs.writeFile()` operations complete. This is because these file operations are running concurrently in the background, and there's no guarantee that they will finish before `os.platform()` executes.

   - If your script relies on the data read from a file by `fs.readFile()` or the data being written by `fs.writeFile()`, it may not be available or complete at the point when `os.platform()` executes.

</details>




<details>
<summary>Sample solution</summary>

 ```js
const fs = require('fs').promises;
const os = require('os');

async function readFileAndLogOSInfo() {
  try {
    const data = await fs.readFile('output.txt', 'utf8');
    console.log('Data from file:', data);

    const platform = os.platform();
    console.log('OS Platform:', platform);
  } catch (error) {
    console.error('Error:', error);
  }
}

readFileAndLogOSInfo();
```

</details>

## Part 2

**Step 1**

1. In your project directory, 
- create a JavaScript file (e.g., `synchronous.js`) where you'll perform the tasks in this lab.
- Create a  `sample.txt` file and add some text to it.

2. import the `fs` module:

```javascript
const fs = require('fs');
```

3. Synchronously read the contents of a `sample.txt` using `fs.readFileSync()`. Handle errors, if any, and log the content to the console:

<details>
<summary>How to</summary>

```javascript
try {
  const data = fs.readFileSync('sample.txt', 'utf8');
  console.log('File contents (Synchronous Read):', data);
} catch (err) {
  console.error('Error reading file:', err);
}
```
</details>

4. Synchronously write data to a new file using `fs.writeFileSync()`. Handle errors, if any, and confirm the data has been written:

<details>
<summary>How to</summary>

```javascript
try {
  fs.writeFileSync('output.txt', 'This is some sample data (Synchronous Write).');
  console.log('Data written to output.txt (Synchronous Write)');
} catch (err) {
  console.error('Error writing file:', err);
}
```
</details>

**Step 5: Operating System Information**

1. Import the `os` module and access various pieces of information about the operating system:

```javascript
const os = require('os');
```

2. Print the hostname using `os.hostname()`:

```javascript
console.log('Hostname:', os.hostname());
```

3. Display the OS platform with `os.platform()`:

```javascript
console.log('OS Platform:', os.platform());
```

4. Determine the available CPU cores with `os.cpus()`:

```javascript
console.log('CPU Cores:', os.cpus());
```

**Step 6**

Use `fs.writeFileSync()` to log `os.hostname()` and `os.platform()`.


<details>
<summary>Sample solution</summary>

```js
const fs = require('fs');
const os = require('os');


const info = `Hostname: ${os.hostname()}\nPlatform: ${os.platform()}`;

// Write the information to a file
try {
  fs.writeFileSync('system_info.txt', info);
  console.log('System information has been written to system_info.txt');
} catch (err) {
  console.error('Error writing system information:', err);
}
```

</details>

**Step 7**

Run Your Program and observe the results.


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

