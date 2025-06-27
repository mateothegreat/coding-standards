---
description: 
globs: 
alwaysApply: false
---
# Debugging Standards

## Debug Logging

For Node.js/JavaScript environments with complex objects:

```js
console.log(inspect(complexObject, {
    colors: true,
    compact: false,
    depth: null, // Show full depth
    breakLength: 80
}));
```

For simple debugging:

```js
console.log('[ComponentName]', 'Action:', { relevantData });
```
