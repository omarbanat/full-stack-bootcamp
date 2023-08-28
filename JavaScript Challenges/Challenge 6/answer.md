# Part 1: Introduction to Asynchronous JS

## 1. Simple Timers

### Delayed Execution:

```javascript
setTimeout(() => {
  console.log("Hello after 5 seconds!");
}, 5000);
```

Real-life example: You might want to display a notification to the user after they've been on a page for a certain amount of time, or show a tooltip after a delay.

### Repeated Execution:

```javascript
setInterval(() => {
  let currentTime = new Date().toLocaleTimeString();
  console.log(currentTime);
}, 1000);
```

Real-life example: Digital clocks on websites or applications, periodic data refresh.

## 2. Playing with Promises

### Delayed Promise:

```javascript
const delayedPromise = new Promise((resolve) => {
  setTimeout(() => {
    resolve("Promise resolved!");
  }, 2000);
});
```

### Chaining Promises:

```javascript
delayedPromise.then((message) => {
  alert(message);
  console.log("Chained message!");
});
```

Real-life example: After a user signs up on a website, you might want to first save their data (1st promise) and then send them a welcome email (2nd promise).

# Part 2: Diving Deeper into Async Operations

## 1. Making your Own Promise

```javascript
const networkRequestPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const randomNum = Math.random();
    if (randomNum > 0.5) {
      resolve("Data fetched successfully!");
    } else {
      reject("Network Error!");
    }
  }, 3000);
});

networkRequestPromise
  .then((response) => console.log(response))
  .catch((error) => console.error(error));
```

Real-life example: Any network request, like fetching data from an API, where there's a possibility of success or failure.

## 2. Using Async/Await with Fetch API

```javascript
async function fetchData() {
  try {
    let response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}
fetchData();

// using promise 

fetch('https://jsonplaceholder.typicode.com/posts/1')
    .then(response => response.json())
    .then(postData => {
        console.log(postData);
    })
    .catch(error => {
        console.error(`Error fetching post ${post}:`, error);
    });


```

Real-life example: Fetching user profile data when they log in to an application.

# Part 3: Advanced Async Patterns

## 1. Multiple Requests at Once

```javascript
async function fetchMultiple() {
    try {
        let [data1, data2, data3] = await Promise.all([
            fetch('https://jsonplaceholder.typicode.com/posts/1').then(response => response.json()),
            fetch('https://jsonplaceholder.typicode.com/posts/2').then(response => response.json()),
            fetch('https://jsonplaceholder.typicode.com/posts/3').then(response => response.json())
        ]);

        console.log(data1, data2, data3);
    } catch (error) {
        console.log("Error fetching data:", error);
    }
}

fetchMultiple();

```

Real-life example: Loading multiple pieces of content on a dashboard from different sources at once.

## 2. Looping Through Promises with Async Iteration

```javascript
const postsToFetch = [4, 5, 6, 7, 8];

async function logPostsSequentially() {
    for(let post of postsToFetch) {
        try {
            const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${post}`);
            const postData = await response.json();
            console.log(postData);
        } catch(error) {
            console.error(`Error fetching post ${post}:`, error);
        }
    }
}

logPostsSequentially();

```

Real-life example: Loading a series of images in a slideshow one by one.
