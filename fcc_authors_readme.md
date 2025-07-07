# 📰 FreeCodeCamp News Authors Project

This project demonstrates how to fetch and display author data from the [FreeCodeCamp News](https://freecodecamp.org/news) API. It focuses on using `fetch()` for HTTP requests, handling promises, and dynamically rendering data in a performant way using pagination.

---

## 📌 Project Steps

### ✅ Step 1: Introduction

This project retrieves data about authors from the **FreeCodeCamp News** platform using a publicly available API.

---

### ✅ Step 2: Make a GET Request

To get data from an online source, we use an **API (Application Programming Interface)**. JavaScript provides the `fetch()` method to send a GET request and receive data:

```js
fetch("https://cdn.freecodecamp.org/curriculum/news-author-page/authors.json")
```

Do **not** end this line with a semicolon yet.

---

### ✅ Step 3: Handle the Response Promise

The `fetch()` method returns a **Promise**. If fulfilled, the promise returns a `Response` object:

```js
fetch("https://cdn.freecodecamp.org/curriculum/news-author-page/authors.json")
  .then((res) => res)
```

---

### ✅ Step 4: Convert the Response to JSON

The raw response isn't usable directly. Convert it to JSON format:

```js
  .then((res) => res.json())
```

---

### ✅ Step 5: Access and Inspect the Data

Chain another `.then()` to access the parsed JSON data:

```js
  .then((data) => {
    console.log(data); // inspect the structure of the author data
  })
```

---

### ✅ Step 6: Handle Errors Gracefully

Use `.catch()` to log any errors that occur during the fetch request:

```js
  .catch((err) => {
    console.error(`There was an error: ${err}`);
  });
```

Now you can terminate the code with a semicolon.

---

### ✅ Step 7: Setup Pagination Variables

To avoid rendering all 26 authors at once, display 8 authors at a time. Create the following variables:

```js
let startingIndex = 0;
let endingIndex = 8;
let authorDataArr = [];
```

---

### ✅ Step 8: Create a UI Display Function

Define a function that will be called once the data is ready:

```js
const displayAuthors = (authors) => {
  // populate UI with author data here
};
```

---

### ✅ Step 9–10: Loop and Destructure Author Data

Use `.forEach()` to loop through the sliced author data and destructure it:

```js
authors.slice(startingIndex, endingIndex).forEach(({ author, image, url, bio }, index) => {
  // Render each author
});
```

Use `index` to keep track of pagination.

---

### ✅ Step 11: Add "Show More" Button Functionality

To improve the user experience, implement a "Show More" button that loads the next 8 authors on each click:

```js
document.getElementById("show-more-btn").addEventListener("click", () => {
  startingIndex += 8;
  endingIndex += 8;
  displayAuthors(authorDataArr);
});
```

Make sure to hide or disable the button when all authors are displayed.

---

## 💠 Features

- Fetch data from external API
- Use Promises (`fetch`, `.then()`, `.catch()`)
- Display data in chunks (8 at a time)
- Add "Show More" button for pagination
- Handle errors properly
- Dynamic rendering with destructured objects

---

## 📌 API Used

```
https://cdn.freecodecamp.org/curriculum/news-author-page/authors.json
```

---

## ✅ Next Steps

- Add search or filter functionality
- Improve UI/UX with animations or transitions
- Add loader/spinner during data fetch

---

## 💻 Author

Created as part of the **FreeCodeCamp JavaScript Projects**.

