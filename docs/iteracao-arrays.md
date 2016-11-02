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
- teste lógico de parada: `i < arr.length`
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

![Bazinga](http://piratevinyldecals.com/wps/wp-content/uploads/2014/04/Bazinga-PV369.png)


> **Mas tenho boas notícias!**

> No ES6 isso nao acontece mais se usarmos o `let`.


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

![underground](http://ichef.bbci.co.uk/news/660/cpsprodpb/C2CB/production/_89976894_89976893.jpg)

## forEach

**agora sim chegamos onde deveríamos!**

O `forEach`, *para cada*, sim parece ser o `for`, mas nao é!

anteriormente vimos que o `for` além de podermos "iterar" no *array* ele também pode iterar sem precisar de um. Porém com o `forEach` nós **só podemos iterar em cima de um *array*.**

> Mas isso nao é ruim tio Suissa??

agora irei lhe explicar porque isso na real é **muito** bom!

Um pouco acima vimos que se você usar o `for` com `var` o contador ira "vazar", tudo bem que com `let` isso nao ira acontecer, porém o `for` nao foi feito, especificamente, para iterar em arrays.

Porém ha um caso bem especial quando trabalhamos com o `for` para gerar *arrays* ou fazer os exercícios sobre matriz da faculdade. :p

Sem mais delongas vamos ao código:

```js
> let arr = [1,2,3,4,5]
> arr.forEach((element, index) => console.log(element, index))
1 0
2 1
3 2
4 3
5 4
```

O `forEach` sempre recebe esses dois parametros:

- elemento: element
- índice: index

Perceba que agora nao precisamos mais do contador e nem de do teste lógico de parada.

> Por quê?

Porque ele foi criado pensando-se no *array* tanto que ele vem com o `prototype` do array.

É exatamente por estar no `prototype` que podemos chama-lo, como no exemplo acima, porém nao podemos encadear outras funções do `prototype` do *array* como porque o `forEach` nao retorna um *array* novo,

```js
let numeros = ["um", "dois", "três", "quatro"]
numeros.forEach(function(numero) {
  console.log(numero)
  if (numero === "dois") {
    numeros.shift()
  }
})
um
dois
quatro
```

## map

O método `map` serve para **transformar** um array em um novo array com
o **mesmo tamanho** (_length_), mas com novos dados.

A assinatura do método `map` é exatamente a mesma do `forEach`: Ele
sempre recebe uma função de _callback_ que é executada a cada iteração,
até que todos os itens do array sejam iterados.

Ao final da iteração, o método `map` retorna um novo array. Cada item
desse novo array será construído a partir do retorno da função de
_callback_ passada.

> Complicado? 
> 
> Nem tanto =)

Vamos ver um exemplo:

Temos um array de números - `[1, 2, 3]` - e queremos um novo array que
adicione `1` a cada item desse array. Podemos fazer isso utilizando o
método `map`:

```js
const array = [1, 2, 3]
const newArray = array.map((number) => {
  return number + 1
})

console.log(newArray) // [2, 3, 4]
```

> Olha só que simples! 

A função de _callback_ passada para o método `map`
return o primieiro parâmetro que ela recebe + 1.

Esses parâmetros são passados a cada iteração pelo método `map`. Além
do item que está sendo iterado, o método `map` ainda passa outros dois
parâmetros que podem ser usados nessa função:

- o primeiro parâmetro é o item que está sendo iterado;
- o segundo parâmetro é o índice do item sendo iterado;
- e o terceiro parâmetro é o array original, que está sendo iterado.

Fica muito claro que você pode usar o item que está sendo iterado e/ou
o seu índice para transformar o array em um novo.

Mas por que usar o terceiro parâmetro, já que você pode ter acesso
direto ao array que está sendo iterado através de uma variável
(no exemplo, a variável `array`)?

Bom, vai fazer sentido quando entendermos sobre o próximo método: o `filter`.

## filter