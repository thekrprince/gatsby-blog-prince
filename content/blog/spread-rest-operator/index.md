---
title: Spread operator, Rest operator & Destructuring in JS
date: "2021-05-09T22:12:03.284Z"
description: "Difference b/w Spread operator, Rest operator and Destructuring"
---

Hi Everyone,

This is my first blog. And in this blog, I'm gonna talk about **Spread Operator, Rest Operator** and **Destructuring** in JavaScript, and as I have been working on JavaScript since 1 year, I used to think that spread operator is used for destructuring. While working on a project recently I found out that concept of destructuring is completely different and thought of sharing it here. So, Let's begin.

## Spread Operator

The spread operator is used to split up array elements or object properties. It does deep cloning of the array elements or object, so it doesn't affect the original values.
Let's see the Example of Array first-

```javascript
const arr1 = [1, 2, 3]
const arr2 = [...arr1, 4, 5]
console.log(arr1) // [1, 2, 3]
console.log(arr2) // [1, 2, 3, 4, 5]
arr1.push(6, 7)
console.log(arr1) // [1, 2, 3, 6, 7]
console.log(arr2) // [1, 2, 3, 4, 5]
```

You can see above that **arr2** hasn't changed after adding more values to **arr1**.
But what if I hadn't provided the "..." operator in **arr2**. Let's find out below-

```javascript
const arr1 = [1, 2, 3]
const arr2 = [arr1, 4, 5]
console.log(arr1) // [1, 2, 3]
console.log(arr2) // [[1, 2, 3], 4, 5]
```

Yes. It would create a nested array.

Same goes with the objects as well.

```javascript
const obj1 = {
  name: "Prince",
  Sex: "Male",
}
console.log(obj1) //{name: "Prince", sex: "male"}

const obj2 = {
  ...obj1,
  age: 25, //{age: 25, name: "Prince", sex: "male}
}
console.log(obj2)

obj1["height"] = "5'8 ft"
console.log(obj1) //{height: "5'8 ft",name: "Prince", sex: "male"}
console.log(obj2) //{age: 25, name: "Prince", sex: "male}
```

## Rest Operator

Rest operator is used in a function whenever multiple arguments are expected.

```javascript
const filter = (...args) => {
  return args.filter(val => val % 5 === 0)
}

console.log(filter(5, 10, 2, 4, 20)) // [5, 10, 20]
```

You can see above that we are passing 5 arguments while calling filter function and it's printing the value according to the condition and even we can pass **n number** of argument and it'll work just fine.

## Destructuring

It's also next gen javascript feature. Destructuring easily extract array elements or object properties and store them in variables.
By the above definition, you'd have been thinking that It works exactly as spread operator but It's work differently.
Let's find out below.-

```javascript
// Array
const num = [11, 22, 33]
;[x, y] = num
console.log(x) // 11
console.log(y) // 22
;[x, , y] = num
console.log(x) // 11
console.log(y) // 33
```

When destructuring array, It'll return the value of the index as per left key indexing. And yes, we're not creating any array when writing like [x,y] on the left side. I know, it seems strange but even I was confused earlier.

```javascript
// Object
{name} = {
    name: "Audi",
    model: "A8",
    price: "1.5 cr"
}

console.log(name);                          // "Audi"
console.log(age);                           // undefined
// Above output will be undefined as age is not destructured and aligned with the same key
```

You can see above that age is returning **undefined** as It's not destructured and aligned with the same key.

That's it for this article folks. 🙏Thanks For Reading.
