# Dicas JavaScript

Arquivo com dicas JavaScript para auxiliar minha (ou de outros desenvolvedores) trajetória na linguagem. Esse arquivo será atualizado indeterminadamente.

## Índice

* [Valores *falsy*](#valores-falsy)
* [Funções sempre retornam algo](#funções-sempre-retornam-algo)
* [Laço `while` e valores *falsy*](#laço-while-e-valores-falsy)

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
