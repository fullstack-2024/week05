### JavaScript `forEach()` Lab

In this lab, we'll explore the usage of the `forEach()` method in JavaScript. `forEach()` is a higher-order function that allows you to `execute a provided function once for each element in an array`.

Before starting the lab exercises, ensure that Node.js and npm are installed on your system. You can check their versions using the following commands:

```bash
node -v
npm -v
```

> If you do not have Node.js and npm installed, follow this guideline [here](./node.md).

> Create a new directory named `week5-lab2` to organize your work for this activity.

#### Exercise 1: Calculating the Sum of Numbers in an Array

```javascript
let sum = 0;
const numbers = [65, 44, 12, 4];

function addNumberToSum(item) {
  sum += item;
}

numbers.forEach(addNumberToSum);

console.log("Sum of numbers:", sum);
```

#### Exercise 2: Logging Each Element of an Array

```javascript
const fruits = ["apple", "orange", "cherry"];

function logFruit(fruit) {
  console.log(fruit);
}

fruits.forEach(logFruit);
```

#### Exercise 3: Logging Each Element of an Array with an Anonymous Function

```javascript
const array1 = ['a', 'b', 'c'];

array1.forEach(function (element) {
  console.log(element);
});
```

#### Exercise 4: Adding 10 to Each Element of an Array

```javascript
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function (num, index, arr) {
  arr[index] = num + 10;
});

console.log(numbers);
```

#### Exercise 5: Reversing Strings in an Array

```javascript
const strings = ["program", "world", "javascript"];

strings.forEach(function (str, index, arr) {
  arr[index] = str.split('').reverse().join('');
});

console.log(strings);
```

#### Exercise 6: Filtering Out Odd Numbers from an Array

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const evenNumbers = [];

numbers.forEach(function (num) {
  if (num % 2 === 0) {
    evenNumbers.push(num);
  }
});

console.log(evenNumbers);
```

#### Exercise 7: Converting Celsius to Fahrenheit

```javascript
const celsiusTemperatures = [0, 10, 20, 30, 40];

celsiusTemperatures.forEach(function (celsius, index, arr) {
  arr[index] = (celsius * 9/5) + 32;
});

console.log(celsiusTemperatures);
```

#### Exercise 8: Capitalizing Each Element of an Array

```javascript
const words = ["apple", "banana", "cherry"];

words.forEach(function (word, index, arr) {
  arr[index] = word.charAt(0).toUpperCase() + word.slice(1);
});

console.log(words);
```

> The expression `word.charAt(0).toUpperCase() + word.slice(1)` is used to capitalize the first letter of a string.

Let's break down the expression:

1. `word.charAt(0)`: This part of the expression retrieves the character at the first index (position) of the string `word`. The method `charAt(0)` returns the character at the specified index, in this case, the first character of the string.

2. `.toUpperCase()`: This method is chained to `charAt(0)` and converts the character retrieved from the first index to uppercase. This ensures that the first letter of the string is capitalized.

3. `+ word.slice(1)`: This part of the expression concatenates the uppercase first letter obtained in the previous step with the remaining part of the original string `word`. The method `slice(1)` is used to extract the substring starting from the second character (index 1) to the end of the string. This effectively removes the first character from the original string, leaving the rest of the string unchanged.

Putting it all together, `word.charAt(0).toUpperCase() + word.slice(1)` effectively capitalizes the first letter of the string `word` and retains the rest of the string as is. This is a common technique used to capitalize the first letter of a word or sentence in JavaScript.

#### Exercise 9: Finding the Maximum Number in an Array

```javascript
const numbers = [10, 20, 5, 30, 15];

let maxNumber = numbers[0];

numbers.forEach(function (num) {
  if (num > maxNumber) {
    maxNumber = num;
  }
});

console.log("Maximum number:", maxNumber);
```

#### Exercise 10: Creating HTML List Items

```javascript
const names = ["John", "Jane", "Bob", "Alice"];

const listItems = [];

names.forEach(function (name) {
  listItems.push("<li>" + name + "</li>");
});

console.log(listItems.join(""));
```

#### Exercise 11: Counting Occurrences of Each Letter in a String

```javascript
const sentence = "The quick brown fox jumps over the lazy dog";
const letterCounts = {};

const letters = sentence.split('');

letters.forEach(function (letter) {
  if (letter !== ' ') {
    letter = letter.toLowerCase();
    letterCounts[letter] = (letterCounts[letter] || 0) + 1;
  }
});

console.log(letterCounts);
```

> This code snippet analyzes a sentence to count the occurrences of each letter, excluding spaces, and stores the counts in an object named `letterCounts`.

Let's break down the code:

1. `const sentence = "The quick brown fox jumps over the lazy dog";`: This line defines a string `sentence` containing the text to be analyzed.

2. `const letterCounts = {};`: This line initializes an empty object `letterCounts`, which will store the counts of each letter.

3. `const letters = sentence.split('');`: This line splits the `sentence` string into an array of individual characters, including spaces. Each character becomes an element in the `letters` array.

4. `letters.forEach(function (letter) { ... });`: This line iterates over each character in the `letters` array using the `forEach()` method. For each character (letter), the provided callback function is executed.

5. `if (letter !== ' ') { ... }`: This condition checks if the current character is not a space. If the character is not a space, the code inside the if block is executed.

6. `letter = letter.toLowerCase();`: This line converts the current character to lowercase. This step ensures that uppercase and lowercase versions of the same letter are treated as equivalent when counting occurrences.

7. `letterCounts[letter] = (letterCounts[letter] || 0) + 1;`: This line increments the count of the current letter in the `letterCounts` object. It uses the current letter as the key to access the corresponding count in `letterCounts`. If the letter has not been encountered before, `letterCounts[letter]` will be `undefined`, so `(letterCounts[letter] || 0)` evaluates to `0`. The count is then incremented by 1.

8. `console.log(letterCounts);`: After iterating over all characters in the `letters` array, this line prints the `letterCounts` object to the console, showing the counts of each letter in the sentence.

Overall, this code efficiently counts the occurrences of each letter in the sentence while ignoring spaces, and provides the counts in the `letterCounts` object for further analysis or display.


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

