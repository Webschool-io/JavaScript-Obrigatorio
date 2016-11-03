# Operações de bit

Poucos programadores utilizam operações com bits, na maioria das vezes por não ter o conhecimento necessário.

Como você **deve** ser um programador eu não vou lhe explicar, quero que você **DEDUZA** (sem olhar na documentação né!).

Antes de tudo preciso lhe ensinar como visualizar o valor de um número em bits:

```js
> 3..toString(2)
'11'
> 2..toString(2)
'10'
> 1..toString(2)
'1'
> 0..toString(2)
'0'
```

Logo você entendeu que o `0` em bits é `"0"`, que o `1` é `"1"`, que o `2` é `"10"` e que o `3` é `"11"`, sabendo disso o que você consegue inferir sobre os valores binários?


Agora vamos analisar as operações abaixo:

```js
> 20..toString(2)
'10100'
> 20 >> 1
10
> 20 >> 2
5
> 20 >> 3
2
> 10..toString(2)
'1010'
> 5..toString(2)
'101'
> 2..toString(2)
'10'
```

Podemos inferir que o valor em bits de `20` é `"10100"` e quando utilizo o operador `>>` com o valor `1` ele se resulta no número `10` que é representado binariamente por `"1010"`, quando usamos o mesmo operador com o número `2` ele resulta em `5` sendo representado por `"101"` e quando usamos o operador com o número `3` temos como resultado `2`, representado por `"10"`.

Então agora eu lhe pergunto:

> O que esse operador faz (binariamente)?

Analise novamente essa sequência focando apenas nos valores binários:

```js
> 20..toString(2)
'10100'
> 10..toString(2) // >> 1
'1010'
> 5..toString(2) // >> 2
'101'
> 2..toString(2) // >> 3
'10'
```

> Ficou fácil né?!


**Agora quero que você envie um PULL REQUEST com a sua resposta.**
