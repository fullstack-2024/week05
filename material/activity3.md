### JavaScript `filter()` Lab

In this lab, we'll explore the usage of the `filter()` method in JavaScript. `filter()` is a higher-order function that allows you to create a new array containing only elements that pass a certain condition.

Before starting the lab exercises, ensure that Node.js and npm are installed on your system. You can check their versions using the following commands:

```bash
node -v
npm -v
```

> If you do not have Node.js and npm installed, follow this guideline [here](./node.md).

> Create a new directory named `week5-lab3` to organize your work for this activity.

#### Exercise 1: Filtering Ages to Find Adults

```javascript
const ages = [32, 33, 16, 40];

function checkAdult(age) {
  return age >= 18;
}

const adults = ages.filter(checkAdult);
console.log("Adults:", adults);
```

#### Exercise 2: Filtering Words with Length Greater Than 6

```javascript
const words = ['spray', 'elite', 'exuberant', 'destruction', 'present'];

const longWords = words.filter(function (word) {
  return word.length > 6;
});

console.log("Long words:", longWords);
```

#### Exercise 3: Filtering Numbers Greater Than or Equal to 10

```javascript
function isBigEnough(value) {
  return value >= 10;
}

const filteredNumbers = [12, 5, 8, 130, 44].filter(isBigEnough);
console.log("Filtered numbers:", filteredNumbers);
```

#### Exercise 4: Filtering Even Numbers

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const evenNumbers = numbers.filter(function (num) {
  return num % 2 === 0;
});

console.log("Even numbers:", evenNumbers);
```

#### Exercise 5: Filtering Palindromes

```javascript
function isPalindrome(word) {
  return word === word.split('').reverse().join('');
}

const words = ['level', 'hello', 'radar', 'world', 'racecar'];

const palindromes = words.filter(isPalindrome);
console.log("Palindromes:", palindromes);
```

> This code snippet filters out palindromes from an array of words and stores them in a new array named `palindromes`. Let's break down the code:

1. ```javascript
   function isPalindrome(word) {
     return word === word.split('').reverse().join('');
   }
   ```
   This function `isPalindrome` checks if a given word is a palindrome or not. A palindrome is a word, phrase, number, or other sequences of characters that reads the same forward and backward. This function achieves this by splitting the word into an array of characters using `split('')`, reversing the array using `reverse()`, and then joining the reversed array back into a string using `join('')`. If the resulting string is equal to the original word, it means the word is a palindrome, and the function returns `true`; otherwise, it returns `false`.

2. ```javascript
   const words = ['level', 'hello', 'radar', 'world', 'racecar'];
   ```
   This line initializes an array `words` containing several words, some of which are palindromes and others are not.

3. ```javascript
   const palindromes = words.filter(isPalindrome);
   ```
   This line applies the `filter()` method to the `words` array, using the `isPalindrome` function as the filter criteria. The `filter()` method creates a new array containing only the elements of the original array for which the provided function returns `true`. In this case, it filters out only the palindromes from the `words` array.

4. ```javascript
   console.log("Palindromes:", palindromes);
   ```
   Finally, this line logs the filtered array of palindromes to the console, showing which words from the original array are palindromes.

Overall, this code demonstrates how to use the `filter()` method to filter out specific elements from an array based on a given condition, in this case, identifying palindromes.

#### Exercise 6: Filtering Strings Containing a Specific Substring

```javascript
const words = ['apple', 'banana', 'orange', 'pineapple', 'grape'];

const filteredWords = words.filter(function (word) {
  return word.includes('apple');
});

console.log("Words containing 'apple':", filteredWords);
```

#### Exercise 7: Filtering Arrays of Objects

```javascript
const products = [
  { id: 1, name: 'Apple', price: 1.99 },
  { id: 2, name: 'Banana', price: 0.99 },
  { id: 3, name: 'Orange', price: 2.49 },
  { id: 4, name: 'Grape', price: 3.99 }
];

const expensiveProducts = products.filter(function (product) {
  return product.price > 2.0;
});

console.log("Expensive products:", expensiveProducts);
```

#### Exercise 8: Filtering Arrays with Null or Undefined Values

```javascript
const values = [1, null, 2, undefined, 3, 4, null, 5, undefined];

const nonNullUndefinedValues = values.filter(function(value) {
  return value !== null && value !== undefined;
});

console.log("Non-null and non-undefined values:", nonNullUndefinedValues);
```

#### Exercise 9: Filtering Arrays Using Arrow Functions

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const evenNumbers = numbers.filter(function(num) {
  return num % 2 === 0;
});

console.log("Even numbers:", evenNumbers);
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

