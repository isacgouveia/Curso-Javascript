# Estudo sobre JavaScript

###### Index
- [O que é javascript?](#page1)
- [Variáveis](#page2)
- [Tipos de dados](#page3)
    - [string](#page4)
    - [number](#page5)
    - [boolean](#page6)
    - [undefined null](#page7)
    - [Conversão e Coerção de Tipos](#page8)
        - [Conversão](#page9)
        - [Coerção](#page10)
- [Escopo](#page11)
- [Hoisting](#page12)

<a id="page1"></a>

## O que é javascript? 
È uma linguagem de programação que permite implementar **interatividade** e **funcionalidades** nas páginas web.
O javascript é client-side (lado do usuário). Isso significa que o código é executado no navegador do usuário.
Permite acessar e manipular os elementos HTML, interações do usuário e comunicação com servidores.

## Tipos de dados

JavaScript é uma **linguagem dinâmica com tipos dinâmicos.** Isso significa que o tipo da variável é definida dinamicamente pelo tipo do valor atribuído (não é necessário declarar o tipo).
Além disso, é possível reatribuir uma mesma variável com um tipo diferente.

*Exemplo:*
```js
    let whatever

    whatever = 1
    console.log(whatever) = 1 (number)

    whatever = "isac"
    console.log(whatever) = Isac (string)

    whatever = true
    console.log(whatever) = TRUE (boolean)

    whatever = null
    console.log(whatever) = null

    whatever
    console.log(whatever) = undefined

```

## Case sensitive
O javascript assim como algumas outras linguagens são case sensitive, sendo assim ela é sensível a letras maiúsculas e minusculas.

*exemplo:*
```js
    let username = "Isac"
    let userName = "Geovana"

    console.log(username) = Isac
    console.log(userName) = Geovana
```

**Estrutura do JS**
Para referenciar o javascript no HTML inserimos o código "<script src="script.js"></script>" no corpo do HTML.

```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initicla-scale=1.0" />
        <title>Estrutura HTML + Javascriot</title> 
    </head>
    <body>
        <script src="script.js"></script>
    </body>
    </html>
```

```js
    console.log("Referenciado!")
```

<a id="page2"></a>

## Variáveis
### O que são variáveis?
Variável na programação é um **espaço reservado na memória** RAM (random Access Memory) do computador para **armazenar algo** temporariamente.

### Quais são os tipos de variáveis?
- Var
- Let
- Const

**Var** - tem escopo de função ou global e pode ser redeclarada e reatribuída.

*Exemplo de variável VAR* 
```js

    // Situação 1
    var user
    console.log(user)

    // Situação 2
    var email = "isac.gouveia@gmail.com"
    console.log(email)

    // Situação 3
    email = "teste@gmail.com"
    console.log(email)
```

**output**
```html
    Output da primeira situação é UNDEFINED.
    Pois, não foi declarado nenhuma informação na variável USER

    Output da segunda situação é isac.gouveia@gmail.com.
    Pois, foi declarado o e-mail.

    Output da terceira situação é teste@gmail.com.
    Pois, substituimos a informação declarada na variável anterior email.

    Após declarada, não há necessidade de utilizar VAR para atualizar uma informação. (situação 3).
    Para exibirmos o resultado utiliza-se o console.log()
```

**let** - tem escopo de bloco, não pode ser redeclarada, mas pode ser reatribuída.

*Exemplo de variável LET*
```js

    // Situação 1
    let user
    console.log("Isac Gouveia")

    // Situação 2
    let user
    console.log("Geovana Gouveia")

    // Situação 3
    let email = "isac.gouveia@gmail.com"
    console.log(email)

    // Situação 4
    email = "test@gmail.com"
    console.log(email)

```

**output**
```html
    Output da primeira situação é Isac Gouveia

    Output da segunda situaçao é ERROR.
    Pois, a variável LET não permite utilizar o mesmo nome.

    Output da terceira situação é Isac.gouveia@gmail.com.

    Output da quarta situação é test@gmail.com.
    Mas detalhe, caso não existisse o console.log da terceira situação o valor isac.gouveia@gmail.com, seria substituído por test@gmail.com

```

**Const** - tem escopo de bloco e não pode ser reatribuída ou redeclarada, exigindo que seja inicializada ao ser declarada.

*Exemplo de variável CONST*
```js

    // Situação 1
    const number = 42
    console.log(number)

    // Situação 2
    number = 55
    console.log(number)

```

**output**
```html
    Output da primeira situação é 42

    Output da segunda situação é ERROR.
    Pois, a variável const não pode ser redeclarada sendo assim, é um valor fixo.
```

*Tabela das variáveis e suas permissões*

|Keyword|const|Let|Var|
|:---|:---:|:---:|:---:|
|Global Scope|NO|NO|YES|
|function Scope|YES|YES|YES|
|block Scope|YES|YES|NO|
|can be reassigned|NO|YES|YES|

<a id="page3"></a>

## Tipos de dados

### <a id="page4">**String**</a>
```js
    let username = "Isac"
    console.log(username) = Isac
    console.log(typeof username) = string

    console.log("Uma string com aspas")
    console.log('Uma string com apóstrofo')
```
typeof é para indicar qual o tipo de dado.

Quando utilizar aspas ou apôstrofo?
Caso queira destacar algo, utiliza-se apôstrofo.

```js
console.log("Destaque "aqui"") = erro
console.log('Destaque "aqui"') = Destaque "aqui"

// acento grave permite escrever múltiplas linhas
console.log(`
    Primeira linha
    Segunda linha
`)
```

### Concatenar o texto
```js
    let name = "Isac"
    let surname = "Gouveia"

    let message = "Seja bem vindo" + name + "seu sobrenome é" + surname
    console.log(message)

```

### Template Literals
Recurso para manipular string de forma mais eficiente. (acento agúdo)
```js
    console.log(`Seja bem vindo ${name} ${surname}`)
```

### <a id="page5">**Number**</a>
```js
    // Number
    console.log(5)

    // Inteiro positivo.
    console.log(5)

    // Inteiro negativo.
    console.log(5)

    // Número decimal (float).
    console.log(7.5)

    // Nan - Not a number
    console.log(12.5 / "isac")

```

### <a id="page6">**Boolean**</a>
```js
    console.log(true)
    console.log(false)

    let isLoading = true
    console.log(isLoading) = true
    console.log(typeof isLoading) = boolean
```

### <a id="page7">**undefined & null**</a>
```js
    let emptiness
    console.log("O valor é:", emptiness) = O valor é UNDEFINED

    let empty = null
    console.log("O valor é:", empty) = O valor é NULL

```

### <a id="page8">**Conversão e coerção de Tipos**</a>
#### <a id="page9">Conversão de tipos (type casting ou type conversion):</a>
Ocorre quando você explicitamente transforma um valor de um tipo para outro. Isso é feito de forma consciente, usando funções ou métodos especificos para realizar a conversão.

```js
    let value = 9
    console.log(typeof value) = number
    console.log(value.toString()) = string 
    console.log(string(value)) = string

    let age = "18"
    console.log(number(age)) = number

    let option = 1
    console.log(boolean(option)) = true
    console.log(typeof boolean(option)) = boolean

```

#### <a id="page10">Coerção de tipos:</a>
Acontece de forma automática (implicitamente). O javaScript tenta automaticamente converter um dos valores para um tipo compatível antes de realizar a operação.

```js
    console.log("10" + 5) = 105 (converteu o 5 para texto)

```

<a id="page11"></a>

## Escopo

É a regição do código onde uma determinada viarável **é acessível ou vísivel**.
O escopo define o **contexto** no qual uma variável pode ser **referenciada e modificada**.

*Exemplo: Tente pensar no contexto como cômodos de uma casa. Por exemplo, para utilizar o fogão você deve estar na cozinha*

### Tipos de Escopos
- **Global:** variáveis declaradas fora de qualquer função ou bloco de código (var).
- **Bloco:** acessíveis apenas dentro do bloco de código onde foram declaradas (let e const).
- **Local:** variáveis declaradas dentro de uma função.

*Exemplo: A cidade São Paulo (bloco/local) pertence ao contexto Brasil (global).*

<a id ="page12"></a>

## Hoisting

Hoisting (**levantar ou içar**) se refere ao comportamento do interpretador de **mover as declarações** de variáveis e funções para o **topo do escopo em que foram definidas**. antes mesmo da execução do código.
Esse comportamento possibilita usar uma variável ou função antes que ela esteja definida.

### Hoisting de variáveis
Todas as declarações de variáveis são movidas para o tipo do seu escopo independentemente de onde tenha sido declara, ela estará disponível para uso em todo o escopo em que foi definida.

**Importante:** mesmo que as declarações de variáveis sejam movidas para o topo do escopo, elas ainda precisam ser declaradas antes de serem utilizadas. Caso contrário, você receberá uma refere^ncia indefinida (undenifed).

### Hoisting de funções
Todas as declarações de funções também são movidas para o topo do seu escopo. Isso significa que você pode chamar uma função antes mesmo de declará-la.
Essa cracterística do JavaScript permite que você organize seu código de forma mais intuitiva. definindo as funções em qualquer ordem que desejar.


|Keyword|const|Let|Var|
|:---|:---:|:---:|:---:|
|Global Scope|NO|NO|YES|
|function Scope|YES|YES|YES|
|block Scope|YES|YES|NO|
|can be reassigned|NO|YES|YES|
