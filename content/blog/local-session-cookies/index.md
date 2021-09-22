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
localStorage.setItem("healthyFruit", "Apple")
```

> **localStorage.getItem()** method is used to get the data from local storage.

```javascript
const myFruit = localStorage.getItem("healthyFruit")
```

> **localStorage.removeItem()** method can be used while removing the exact data with the help of key.

```javascript
localStorage.removeItem("myFruit")
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

Cookies are small strings of data that are stored directly in the browser. They are a part of the HTTP protocol, defined by the RFC 6265 specification. Cookies are usually set by a web-server using the response **Set-Cookie** HTTP-header. Then, the browser automatically adds them to (almost) every request to the same domain using the **Cookie** HTTP-header.

> One of the most widespread use cases is authentication:

1. Upon sign in, the server uses the **Set-Cookie** HTTP-header in the response to set a cookie with a unique “session identifier”.
2. Next time when the request is sent to the same domain, the browser sends the cookie over the net using the **Cookie** HTTP-header.
3. So the server knows who made the request.

##### Few main points about cookie-

- Cookies has the capacity of 4KB.
- It's compatible with HTML4/5.
- Accessible from any window.
- Expiry is set manually. If the expiry is not set then it's gonna be deleted when session overs.
- It's stored on the browser and server both.
- Cookies are sent to the server on every request whenever you load any html, css or image file.
- Cookies are best for data or anything that has to be accessed by the server in the local machine or anything we want to set an expiration date on.

> We can also access cookies from the browser, using document.cookie property.

```javascript
document.cookie = "hello=true"

// To set the expiry
document.cookie = "cookie=set;expires=Fri, 1 Dec 2099 23:59:59 GMT"

// You can set the path as well. Path is just which path on your website the cookie is associated with
document.cookie = "greetings=hey;expires=Fri, 1 Dec 2099 23:59:59 GMT; path=/"
```

> All the cookies get assigned to **document.cookie**, to use it you can directly access the **document.cookie** and it will fetch all the data in one string file. So when you get the cookies you get them all at once and then you would have to write extra code to parse out exactly what cookie you want to use.

To **delete** the cookie you need to set an expiry date which is gonna expire soon or you can use the past date.

```javascript
document.cookie = "greetings=;expires=Fri, 1 Dec 2020 23:59:59 GMT; path=/"
```

This code will delete the **greetings** and it's value which was set as **'hey'** in previous code.
