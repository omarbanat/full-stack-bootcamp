# Step 1: Functions
```
function findMax(num1, num2) {
  if (num1 > num2) return num1;
  if (num2 > num1) return num2;
  return "Both are equal";
}
```
```
function compute(num1, num2, operation) {
  function add() {
    return num1 + num2;
  }

  function subtract() {
    return num1 - num2;
  }

  function multiply() {
    return num1 * num2;
  }

  function divide() {
    if(num2 !== 0) return num1 / num2;
    return "Division by zero!";
  }

  switch (operation) {
    case "add":
      return add();
    case "subtract":
      return subtract();
    case "multiply":
      return multiply();
    case "divide":
      return divide();
    default:
      return "Invalid operation";
  }
}

```
# Step 2: Arrow Functions and Scopes

```
let globalVar = "I'm a global variable";

const squareNumber = (number) => {
  console.log(globalVar); // Accessing global scope

  let localVar = "I'm a local variable";
  return number * number;
}

// console.log(localVar); // This will produce an error because localVar is not defined in the global scope.
```

# Step 3: Loops

For Loop

```
for(let i = 1; i <= 10; i++) {
  console.log(i);
}
```

While Loop

```
let count = 10;
while (count >= 1) {
  console.log(count);
  count--;
}
```

Do-While Loop with Conditionals

```
let num = 1;
do {
  if (num % 2 === 0) console.log(num);
  num++;
} while (num <= 10);
```

Advance loo

```
let fruits = ["Apple", "Strawberry", "Pineapple", "Orange", "Blueberry"];
for (let fruit of fruits) {
  if (fruit.length > 5) console.log(fruit);
}

fruits.forEach(function(fruit) {
  console.log(fruit);
});

```

# Bonus Step: Advanced Concepts

```
const numbers = [1, 2, 3, 4]
function double(num){
    return num * 2
}
function square(num){
    return num * num
}
function processArray(arrayNumbers, functionInput){
    let newArray = []
    for(let i = 0; i < arrayNumbers.length ; i++){
        newArray[i] = functionInput(arrayNumbers[i])
    }
    return newArray
}
console.log(processArray(numbers, double)) // [ 2, 4, 6, 8 ]
console.log(processArray(numbers, square)) // [ 4, 16, 36, 64 ]
```

```
function multiplier(num1) {
  return function(num2) {
    return num1 * num2;
  }
}

let multiplyBy3 = multiplier(3);
console.log(multiplyBy3(5)); // Outputs 15
```


