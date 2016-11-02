# () => {}

```js
var calculate = {  
  array: [1, 2, 3],
  sum() {
    console.log(this === calculate); // => true
    return this.array.reduce((result, item) => result + item);
  }
};
calculate.sum(); // => 6  
```

*fonte: [https://rainsoft.io/when-not-to-use-arrow-functions-in-javascript/](https://rainsoft.io/when-not-to-use-arrow-functions-in-javascript/)*

Eu, pessoalmente, prefiro assim:

```js
var calculate = {  
  array: [1, 2, 3],
  sum() {
    console.log(this === calculate); // => true
    return this.array.reduce((result, item) => result + item);
  }
};
calculate.sum(); // => 6  
```