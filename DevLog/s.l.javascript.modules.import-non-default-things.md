---
id: yzdbnorg7vao2f40wku3tb9
title: Import Non Default Things
desc: ''
updated: 1641407892998
created: 1641407892998
---


### To import non-default things

if we want the functions we defined in the `user.js` file and also exported, we can also import them with the following syntax:

```js
import U, { printName, printAge } from '/user.js'
```

basically, the default import can just be declared as `U` in this instance, where as non default imports have to be imported with the brace syntax. We can also change the name of those items too in this following was: 

```js
import U, { printName as printUsername, printAge as printUserAge } from '/user.js'
```

For more browser support a common method of dealing with imports is to use the `babel` tool to convert these newer features into older and supported javascript code
