### JavaScript Map Lab

In this lab, we'll explore the usage of the `map` function in JavaScript. `map` is a higher-order function that allows you to apply a function to each element of an array and return a `new arra`y with the results.

Before starting the lab exercises, ensure that Node.js and npm are installed on your system. You can check their versions using the following commands:

```bash
node -v
npm -v
```

> If you do not have Node.js and npm installed, follow this guideline [here](./node.md).

> Create a new directory named `week5-lab1` to organize your work for this activity.

### example 1:

```javascript
const array0 = [1, 4, 9, 16];
// Pass a function to map
const map0 = array0.map(function(x) 
{return x * 3});
console.log(map0);
```

#### Exercise 2: Using `map` to Calculate Square Roots

```javascript
const numbers = [4, 9, 16, 25];
const map2 = numbers.map(Math.sqrt);
console.log(map2);
```

#### Exercise 3: Using `map` to Double Numbers

```javascript
const array1 = [1, 4, 9, 16];
const map3 = array1.map(function(x) {
  return x * 2;
});
console.log(map3);
```

#### Exercise 4: Using `map` to Convert Celsius to Fahrenheit

```javascript
const celsiusTemperatures = [0, 10, 20, 30, 40];
const fahrenheitTemperatures = celsiusTemperatures.map(function(celsius) {
  return (celsius * 9/5) + 32;
});
console.log(fahrenheitTemperatures);
```

#### Exercise 5: Using `map` to Convert Strings to Uppercase

```javascript
const fruits = ["apple", "banana", "cherry", "date"];
const uppercaseFruits = fruits.map(function(fruit) {
  return fruit.toUpperCase();
});
console.log(uppercaseFruits);
```

#### Exercise 6: Using `map` to Extract Specific Properties

```javascript
const products = [
  { id: 1, name: "Product A", price: 10 },
  { id: 2, name: "Product B", price: 20 },
  { id: 3, name: "Product C", price: 30 }
];
const productNames = products.map(function(product) {
  return product.name;
});
console.log(productNames);
```

#### Exercise 7: Using `map` to Convert Strings to Arrays

```javascript
const sentences = ["Hello World", "How are you?", "I am fine."];
const words = sentences.map(function(sentence) {
  return sentence.split(" ");
});
console.log(words);
```

#### Exercise 8: Using `map` to Create HTML Elements

```javascript
const names = ["John", "Jane", "Bob", "Alice"];
const listItems = names.map(function(name) {
  return `<li>${name}</li>`;
});
console.log(listItems);
```

#### Exercise 9: Using `map` to Extract Lengths of Strings

```javascript
const words = ["apple", "banana", "cherry", "date"];
const lengths = words.map(function(word) {
  return word.length;
});
console.log(lengths);
```

#### Exercise 10: Using `map` to Format Dates

```javascript
const dates = [new Date("2022-01-01"), new Date("2022-02-02"), new Date("2022-03-03")];
const formattedDates = dates.map(function(date) {
  return `${date.getMonth() + 1}/${date.getDate()}/${date.getFullYear()}`;
});
console.log(formattedDates);
```

#### Exercise 11: Using `map` to Combine First and Last Names

```javascript
function getFullName(item) {
  return [item.firstname, item.lastname].join(" ");
}

const persons = [
  {firstname: "Malcom", lastname: "Reynolds"},
  {firstname: "Kaylee", lastname: "Frye"},
  {firstname: "Jayne", lastname: "Cobb"}
];

const map1 = persons.map(getFullName);
console.log(map1);
```

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

