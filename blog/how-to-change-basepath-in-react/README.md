---
title: How to change basepath in react
author: harshraj8843
date: 2022-02-12
hero: images/hero.png
description: A basepath is the route at which a react web app can be accessed.In general case, the basepath is / i.e. the app can be accessed at http://localhost:3000 If we want to access the web app at something like http://localhost:3000/app1 Here the basepath will be /app1 How to change basepath ? The basepath can be changed easily by homepage property of package.json Just add homepage property to package.json like this. Now the react app can be accessed at http://localhost:3000/app1 If we want to change the basepath of all links of a react app like, http://localhost:3000/link1 => http://localhost:3000/app1/link1 http://localhost:3000/link2 => http://localhost:3000/app1/link2 then we just have to pass a basename property to the router like this
tags:
  - react
contributors:
---

## What is basepath ?

A basepath is the route at which a react web app can be accessed.

In general case, the basepath is '**/**' i.e. the app can be accessed at **_http://localhost:3000_**

If we want to access the web app at something like **_http://localhost:3000/app1_**

Here the basepath will be '**/app1**'

## How to change basepath ?

The basepath can be changed easily by **homepage** property of **package.json**

Just add **_homepage_** property to **_package.json_** like this.

```js
"homepage": "/app1",
```

Now the react app can be accessed at **_http://localhost:3000/app1_**

---

### How to change react router basepath ?

If we want to change the basepath of all links of a react app like,

**_http://localhost:3000/link1_** => **_http://localhost:3000/app1/link1_**

**_http://localhost:3000/link2_** => **_http://localhost:3000/app1/link2_**

then we just have to pass a **_basename_** property to the `router` like this :-

```js
import React from "react";

// routing components
import { BrowserRouter as Router, Switch, Route } from "react-router-dom";

function App() {
  return (
    <Router basename="/app1">
      <Switch>
        <Route path="/link1">...</Route>
        <Route path="/link2">...</Route>
      </Switch>
    </Router>
  );
}

export default App;
```

---
