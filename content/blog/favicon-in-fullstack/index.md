---
title: Updating favicon in Fullstack(React + Django) Application
date: "2021-12-14T22:12:03.284Z"
description: "A guide on how you can make favicon visible on browser while deploying fullstack application on Cloud server."
---

**Hello everyone,**

This blog is about how to change your **_favicon in React_** while deploying your **full-stack application** on **cloud server.**

I actually struggled a bit on fixing this issue in my **_full-stack (React+Django) application_** while deploying on Azure and Heroku. The tab was not displaying any icon after the deployment but was showing using local server. Looked for answers on the internet, none was helpful.

Well I tried so many methods which didn't work, first one was copying the favicon into public folder of React app and changing the path simply. No luck.😥
Then moved the favicon in **_/assets_** folder under **_src_** and then took the reference path of that in **_index.html_** file under **_public_** folder. Still no luck.

Googled the issue, read blogs, nothing worked.

### Now what anyone can do in this situation?

Yeah, you're right, taking help from someone. So, I talked to a friend and he suggested something and I applied. Voila, worked now. <br />Awesome feeling.😄

### So what was the thing I had to do to make this work?

It's no rocket science. All I had to do was to write a **_useEffect_** hook with empty array dependency and in that pick the id using **_document.getElementById('<<Id>>')_**, yeah you can use **_querySelector_** too and then pass the same **_id_** in **_index.html_** file in element related to **_favicon_**. So now you just need to import the favicon in App.js file and set the attribute and you're done.
<br />See, how easy this was.✌️

#### Below are the steps mentioned with code.

**Step 1 - Import icon and write useEffect in App.js**

```javascript
// App.js
import icon from "./images/favicon.ico"

useEffect(() => {
  const favicon = document.getElementById("favicon")
  favicon.setAttribute("href", icon)
}, [])
```

**Step 2 - Add an id to favicon element in index.html file under public folder.**

```javascript
<link rel="shortcut icon" id="favicon" href="%PUBLIC_URL%/favicon.ico" />
```

So this solution worked.🎉
