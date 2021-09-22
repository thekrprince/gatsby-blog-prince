---
title: Local Storage, Session Storage and Cookies
date: "2021-09-17T22:12:03.284Z"
description: "A short explanation on HTML5 Web Storage and Cookies."
---

**Local storage, Session storage** and **Cookies** are pretty important in Web Development. But still many developers get confused about their functionality and properties frequently. So, I thought of writing a blog and trust me this blog will give you a better understanding about them.

## Local Storage

- It has the capacity of 10MB.
- Compatible with HTML5.
- Accessible from any window.
- Never expires until you delete it manually or clear it using JavaScript.
- It's stored in browser.

With the help of below examples, you can access the current domain's local storage object and adds data to it.👇

> Using **localStorage.setItem()** method you can set the data into local storage.

```javascript
localStorage.setItem("storage", "Local")
```

> **localStorage.getItem()** method is used to get the data from local storage.

```javascript
const cat = localStorage.getItem("storage")
```

> **localStorage.removeItem()** method can be used while removing the exact data with the help of key.

```javascript
localStorage.removeItem("myCat")
```

> To remove all the the items from localStorage, you can use **localStorage.clear()** method.

```javascript
localStorage.clear()
```

## Session Storage

- It has the capacity of 5MB.
- Compatible with HTML5.
- Accessible same tab only.
- Expires when tab closes cause it's just for the session the user is on.
- It's also stored in browser.

We can access it using **_window.sessionStorage()_**. Session storage has the same method as Local's storage. Examples are as below.👇

```javascript
// Save data to sessionStorage
sessionStorage.setItem("key", "value")

// Get saved data from sessionStorage
let data = sessionStorage.getItem("key")

// Remove saved data from sessionStorage
sessionStorage.removeItem("key")

// Remove all saved data from sessionStorage
sessionStorage.clear()
```

## Cookies

- Cookies has the capacity of 4KB.
- It's compatible with HTML4/5.
- Accessible from any window.
- Expiry is set manually.
- It's stored on the browser and server both.
- Cookies are sent to the server on every request whenever you load any html, css or image file.
- Cookies are best for data or anything that has to be accessed by the server in the local machine or anything we want to set an expiration date on.
