# Hora da Iteração!

Uma das coisas que um desenvolvedor mais utiliza diariamente é a **iteração** em Arrays.

![](http://2.bp.blogspot.com/-qCGrD75WMDk/VNjgHBQ_YDI/AAAAAAAACoA/qzwZ1Fa690c/s1600/png_hora_de_aventura_echo_por_micatinistaa_by_micatinistaa-d6led9j.png)

Primeiramente quero perguntar para você:

> Quais sao as funções que o JavaScript nos provê para isso?


**Vamos iniciar pelo mundialmente reconhecido...** 

![](http://imguol.com/c/noticias/2014/09/30/comediante-e-deputado-federal-tiririca-pr-sp-1412101756570_956x500.jpg)

## for

### Essa funçao é uma das mais basicas que temos na programaçao e ela serve para *para*.

![](https://media.giphy.com/media/l2YWA6DdmkcJplQwE/giphy.gif)

> Sim o `for` significa **para** ou para cada faça.

Entao pela lógica ele ira executar algo para cada iteraçao, correto? 

> *Talk is cheap, show me the code!*

```js
for (var i = 0; i < arr.length; i++) {
  console.log(rr[i]);
}
```

*Se você ja manja dos paranaues aguarde um pouco.*

Percebeu que para executarmos o `for` precisamos, basicamente, de 3 coisas:

- instanciaçao: `var i = 0`
- teste lógico: `i < arr.length`
- contador: `i++`

> Primeiramente quero deixar claro que eles **nao sao obrigatório**, como veremos abaixo:


```js
var i = 0
for (; i < 5; i++) {
  console.log(i);
}
```

```js
for (var i = 0; ; i++) {
  console.log(i);
  if (i > 5) break;
}
```

```js
for (var i = 0; i < 5; ) {
  i++
  console.log(i);
}
```

Porém temos um *probleminha* de efeitos colaterais com ele, utilizando o `var` para instanciar o `i` ele ira *vazar* do `for`:

```js
> var arr = [1,2,3,4,5];
undefined
> for (var i = 0; i < arr.length; i++) {
...   console.log(arr[i]);
... }
1
2
3
4
5
undefined
> i
5
> i
5
> i
5
> i
5
> WTF?
... 
```

> Mas tenho boas notícias!

> No ES6 isso nao acontece mais se usarmos o `let`. 

![Bazinga](http://piratevinyldecals.com/wps/wp-content/uploads/2014/04/Bazinga-PV369.png)

```js
> let arr = [1,2,3,4,5]
undefined
> for (let i = 0; i < arr.length; i++) {
...     console.log(arr[i]);
... }
1
2
3
4
5
undefined
> i
ReferenceError: i is not defined
    at repl:1:1
    at sigintHandlersWrap (vm.js:22:35)
    at sigintHandlersWrap (vm.js:96:12)
    at ContextifyScript.Script.runInThisContext (vm.js:21:12)
    at REPLServer.defaultEval (repl.js:313:29)
    at bound (domain.js:280:14)
    at REPLServer.runBound [as eval] (domain.js:293:12)
    at REPLServer.<anonymous> (repl.js:513:10)
    at emitOne (events.js:101:20)
    at REPLServer.emit (events.js:188:7)

```


**Essa foi uma breve introduçao ao `for`, pois ele é o mais conhecido.** agora iremos entrar no mundo *underground* da iteracao!


