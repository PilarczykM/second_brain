#spread-operator

Three dots `...` is called spread operator in Javascript and Typescript. This is useful when we want to

- create a copy of an object
- destruct an array and pass them to parameters
- avoid the same definition

### E.g

```ts
const obj = { foo: 123, hoge: 44, name: "obj-name" };
console.log(obj);
// { foo: 123, hoge: 44, name: 'obj-name' }

const spread = { ...obj };
console.log(spread);
// { foo: 123, hoge: 44, name: 'obj-name' }
console.log(`original === spread: ${obj === spread}`);
// original === spread: false
```
