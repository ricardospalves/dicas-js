# Dicas JavaScript

Arquivo com dicas JavaScript para auxiliar minha (ou de outros desenvolvedores) trajetória na linguagem. Esse arquivo será atualizado indeterminadamente.

## Índice

* [Valores *falsy*](#valores-falsy)
* [Funções sempre retornam algo](#funções-sempre-retornam-algo)
* [Laço `while` e valores *falsy*](#laço-while-e-valores-falsy)
* [`typeof null`](#typeof-null)
* [Omissão de chaves](#omissão-de-chaves)

## Dicas

### Valores *falsy*

Valores *falsy* em JavaScript são valores que são avaliados como `false`, que são:

* `false`
* `0`, `+0` ou `-0`
* `''` ou `""` (string vazia)
* `null`
* `undefined`
* `NaN`

Qualquer outro valor, diferente dos valores acima, são avaliados como `true`, mesmo valores como `[]` (array vazio), `{}` (objeto vazio), `' '` ou `" "` (espaço em branco) e `0` ou `"0"` (string zero).

```js
if(false)
  console.log('Não serei executado')

if(0)
  console.log('Não serei executado')

if('')
  console.log('Não serei executado')

if(null)
  console.log('Não serei executado')

if(undefined)
  console.log('Não serei executado')

if(NaN)
  console.log('Não serei executado')
```

### Funções sempre retornam algo

Funções **sempre** retornam algum valor. Caso uma função não tenha `return` explicitamente ou nenhum `return` seja executado, será retornado `undefined`.

```js
function funcaoSemRetorno() {}

function funcaoComRetorno() {
  return 'Valor retornado';
}

function funcaoComRetornoQueNaoSeraExecutado() {
  if(false)
    return 'Não serei retornado';
}

funcaoSemRetorno(); // undefined
funcaoComRetorno(); // 'Valor retornado'
funcaoComRetornoQueNaoSeraExecutado(); // undefined
```

### Laço `while` e valores *falsy*

Valores [*falsy*](#valores-falsy) não executam o laço `while`.

```js
while(false) {
  console.log('Não serei executado');
}

while(0) {
  console.log('Não serei executado');
}

while('') {
  console.log('Não serei executado');
}

while(null) {
  console.log('Não serei executado');
}

while(undefined) {
  console.log('Não serei executado');
}

while(NaN) {
  console.log('Não serei executado');
}
```

### `typeof null`

O `typeof null` no JavaScript é `object`, isso é um erro desde a primeira implementação.

### Omissão de chaves

Em estruturas condicionais como `if` e `else if`; e laços como `for` e `while`, caso elas possuam apenas uma expressão internamente, as chaves podem ser omitidas.

```js

if(true)
  console.log('Só serei executado se o `if` for verdadeiro');
```

Caso haja mais de uma expressão internamente e as chaves forem omitidas, somente a primeria expressão imediatamente após será considerada como sendo parte da estrutura condicional ou do laço, as outras serão executadas incondicionamente.

```js

if(true)
  console.log('Só serei executado se o `if` for verdadeiro');
  console.log('Sempre serei executado, independente do valor de `if`');
```
