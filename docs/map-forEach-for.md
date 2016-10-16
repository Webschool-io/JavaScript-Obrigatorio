# Hora da Iteraçao!

Uma das coisas que um desenvolvedor mais utiliza diariamente é a **iteração** em Arrays.

![](https://media.giphy.com/media/P4Gz8k7nq9cQ0/giphy.gif)

Primeiramente quero perguntar para você:

> Quais sao as funções que o JavaScript nos provê para isso?


**Vamos iniciar pelo mundialmente reconhecido...** 

![](http://imguol.com/c/noticias/2014/09/30/comediante-e-deputado-federal-tiririca-pr-sp-1412101756570_956x500.jpg)

## for

```js
var arr = [1, 2, 3];
.map():

arr.map(function(i) {
  console.log(i);
});
// 43 characters

.forEach():

arr.forEach(function(i) {
  console.log(i);
});
// 47 characters

for():

for (var i = 0, arr.length; i < l; i++) {
  console.log(arr[i]);
}
// 70 characters
```

```js
var arr = [1, 3, 2];

console.log(
  // This one works:
  arr
  .map(function (i) {
    return i + i;
  })
  // Chaining!
  .sort()
);
// => [ 2, 4, 6 ]

console.log(
  // This one does not:
  arr
  .forEach(function (i) {
    return i + i;
  })
  // This is where forEach breaks:
  .sort()
);
// => TypeError: Cannot read property 'sort' of undefined
```
