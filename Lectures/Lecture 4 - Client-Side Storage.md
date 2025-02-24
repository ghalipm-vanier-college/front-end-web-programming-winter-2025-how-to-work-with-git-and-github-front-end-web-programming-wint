# **Lecture 4: Client-Side Storage**

## Table of Contents

1. [Storing Data with Client-side Data Storage](#1-storing-data-with-client-side-data-storage)
2. [Using Cookies](#2-using-cookies)  
   2.1 [The Cookie String](#21-the-cookie-string)  
   2.2 [Creating a Cookie](#22-creating-a-cookie)  
   2.3 [Getting a Cookie’s Value](#23-getting-a-cookies-value)  
   2.4 [Cookie Limitations](#24-cookie-limitations)  
3. [Using Web Storage API](#3-using-web-storage-api)  
   3.1 [Setting Data](#31-setting-data)  
   3.2 [Getting Data](#32-getting-data)  
   3.3 [Removing Data](#33-removing-data)  
   3.4 [Storing Data as Strings](#34-storing-data-as-strings)  
   3.5 [Viewing Web Storage Content](#35-viewing-web-storage-content)  
4. [Using IndexedDB](#4-using-indexeddb)

## 1. Storing Data with Client-side Data Storage

Client-side data storage refers to the various ways JavaScript can store data in the user’s browser. It allows you to save data locally, so it persists between page loads and browser sessions. The main methods of client-side data storage in JavaScript include:

- **Cookies**: Small pieces of data stored in key-value pairs, often used for session management and user preferences.
- **Web Storage API**: Comprises two types of storage: `localStorage` and `sessionStorage`, used to store data as strings.
- **IndexedDB**: A low-level API for storing large amounts of structured data, supporting transactions and queries.

## 2. Using Cookies

Cookies are a popular way to store small pieces of information on the client side, usually in the form of key-value pairs.

### 2.1 The Cookie String

Cookies are stored as a single string in the browser, where multiple cookies are separated by semicolons. A typical cookie string looks like this:

```
username=JohnDoe; expires=Thu, 18 Dec 2024 12:00:00 UTC; path=/;
```

### 2.2 Creating a Cookie

To create a cookie in JavaScript, you assign a string to the `document.cookie` property:

```javascript
document.cookie = "username=JohnDoe; expires=Thu, 18 Dec 2024 12:00:00 UTC; path=/";
```

- **Key-Value Pair**: Stores data as `key=value`.
- **Expires**: Defines the expiration date of the cookie.
- **Path**: Specifies the scope of the cookie (which pages can access it).

### 2.3 Getting a Cookie’s Value

To get the value of a specific cookie, you need to parse the `document.cookie` string:

```javascript
function getCookie(name) {
  let cookies = document.cookie.split(';');
  for (let cookie of cookies) {
    let [key, value] = cookie.trim().split('=');
    if (key === name) return value;
  }
  return null;
}

let username = getCookie('username');
```

### 2.4 Cookie Limitations

- **Size Limit**: Each cookie can only store up to 4KB of data.
- **Security**: Cookies are sent with every HTTP request, which can affect performance and privacy.
- **Expiration**: Cookies are automatically deleted after their expiration date or when the user clears their browser data.

## 3. Using Web Storage API

The Web Storage API provides a more efficient and versatile way to store data on the client side compared to cookies. It consists of two main storage mechanisms: `localStorage` and `sessionStorage`.

- **`localStorage`**: Persists across browser sessions and page reloads.
- **`sessionStorage`**: Data is stored for the duration of the page session and cleared when the page is closed.

### 3.1 Setting Data

To store data in `localStorage` or `sessionStorage`, use the `setItem()` method:

```javascript
// Setting data in localStorage
localStorage.setItem('theme', 'dark');

// Setting data in sessionStorage
sessionStorage.setItem('sessionID', 'abc123');
```

### 3.2 Getting Data

To retrieve data, use the `getItem()` method:

```javascript
// Getting data from localStorage
let theme = localStorage.getItem('theme');

// Getting data from sessionStorage
let sessionID = sessionStorage.getItem('sessionID');
```

### 3.3 Removing Data

You can remove individual items or clear all data:

```javascript
// Remove a single item
localStorage.removeItem('theme');

// Clear all items
sessionStorage.clear();
```

### 3.4 Storing Data as Strings

Data stored in `localStorage` and `sessionStorage` is always saved as strings. If you need to store objects or arrays, you must serialize the data using `JSON.stringify()` and deserialize it using `JSON.parse()`:

```javascript
// Storing an object
let user = { name: 'John', age: 30 };
localStorage.setItem('user', JSON.stringify(user));

// Retrieving and parsing the object
let userData = JSON.parse(localStorage.getItem('user'));
```

### 3.5 Viewing Web Storage Content

You can view the contents of `localStorage` or `sessionStorage` directly from the browser’s developer tools under the **Application** tab in Chrome or **Storage** in Firefox.

## 4. Using IndexedDB

IndexedDB is a low-level API for storing large amounts of structured data on the client-side. Unlike Web Storage, IndexedDB allows you to store data in more complex structures, and it supports indexing and transactions.

### 4.1 Opening a Database

To use IndexedDB, you first need to open a database:

```javascript
let request = indexedDB.open('myDatabase', 1);

request.onupgradeneeded = function(event) {
  let db = event.target.result;
  db.createObjectStore('users', { keyPath: 'id' });
};
```

### 4.2 Adding Data

To add data to an IndexedDB store, you need to use a transaction:

```javascript
let db;
let request = indexedDB.open('myDatabase', 1);

request.onsuccess = function(event) {
  db = event.target.result;

  let transaction = db.transaction(['users'], 'readwrite');
  let store = transaction.objectStore('users');

  let user = { id: 1, name: 'Alice', age: 25 };
  store.add(user);
};
```

### 4.3 Retrieving Data

To retrieve data from IndexedDB, you use the `get()` method:

```javascript
let transaction = db.transaction(['users']);
let store = transaction.objectStore('users');

let request = store.get(1);
request.onsuccess = function(event) {
  console.log(request.result); // { id: 1, name: 'Alice', age: 25 }
};
```

### 4.4 Updating and Deleting Data

- **Updating Data**: Use the `put()` method to update a record.
  
  ```javascript
  store.put({ id: 1, name: 'Alice', age: 26 });
  ```

- **Deleting Data**: Use the `delete()` method to remove a record.

  ```javascript
  store.delete(1);
  ```
