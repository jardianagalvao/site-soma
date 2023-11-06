# Entregavel03-Ambientes
Terceiro entregável da disciplina de Ambiente e Desenvolvimento de Software, Prof. Alzir

## Criar um novo projeto
1. Crie uma pasta chamada `site-soma`.
2. Abra essa nova pasta no Visual Studio Code (Arquivo > Abrir e selecione a pasta).
3. Em seguida, abra o terminal e execute o comando a seguir `npm init -y` para criar um novo **projeto NPM**.

## Instalar o Express
No terminal do Visual Studio Code, execute o comando para instalar o Express `npm install express`.

## Criar servidor
Com o **Express** instalado, deve-se criar um servidor.
1. Crie primeiro um arquivo chamado `app.js`
2. Copie o código a seguir nele:

```
var express = require('express');
var app = express();

app.get('/', function(req, res) {
  res.send('Oi, mundo :-)');
});

var port = 3001;

// iniciando o processo do servidor
app.listen(port, function() {
  console.log(`App de Exemplo escutando na porta http://localhost:${port}/`);
});
```

## Executando o servidor
1. No terminal do Vs Code, execute o comando `node app.js` 
2. Abra o seu navegador na url [http://localhost:3001](http://localhost:3001).

## Criar uma requisição POST
Copie e cole no arquivo que foi criado recente esse código:

```
app.post('/soma', function (req, res) {
  res.send('Response da requisição POST');
});
```

## Consumir dados do POST
Instale a biblioteca `body-parser`. Essa biblioteca nos ajuda a fazer a leitura dos dados via ***POST***

Para instalar, execute o comando `npm install body-parser` no terminal do Visual Studio Code.

Logo após a declaração da variável app, cole o código a seguir:

```
var bodyParser = require('body-parser');
app.use(bodyParser.json());
```

Em seguida, no corpo da função post, cole o seguinte código:

```
var body = req.body;
console.log(body);
res.send('via post');
```

Pronto. Salve o arquivo, execute `npm app.js` no terminal! Isso faz com que ele execute.

## Criando uma função soma
- Veja a função soma a seguir e como integrá-la em seu site.

```
function soma(a, b) {
  return a + b;
}
```

Copie e cole essa função para o arquivo `app.js` e em seguida substitua o código a seguir no corpo da função `post`.
```
var body = req.body;
var resultado = soma(body.a, body.b);

res.send(`O resultado da soma de ${body.a} e ${body.b} é ${resultado}`);
```
## Criando uma função substração
- Veja a função subtração a seguir e como integrá-la em seu site.

```
function subtracao(a, b) {
  return a - b;
}
```
Copie e cole essa função para o arquivo `app.js` e em seguida substitua o código a seguir no corpo da função `post`.
```
var body = req.body;
var resultado = subtracao(body.a, body.b);
  
res.send(`O resultado da subtração de ${body.a} e ${body.b} é ${resultado}`);
});
```
## Criando uma função multiplicação
- Veja a função multiplicação a seguir e como integrá-la em seu site.

```
function multiplicacao(a, b) {
  return a * b;
}
```
Copie e cole essa função para o arquivo `app.js` e em seguida substitua o código a seguir no corpo da função `post`.
```
var body = req.body;
var resultado = multiplicacaocao(body.a, body.b);
  
res.send(`O resultado da multiplicação de ${body.a} e ${body.b} é ${resultado}`);
});
```
## Criando uma função divisão
- Veja a função divisão a seguir e como integrá-la em seu site.

```
function divisao(a, b) {
  return a / b;
}
```
Copie e cole essa função para o arquivo `app.js` e em seguida substitua o código a seguir no corpo da função `post`.
```
var body = req.body;
var resultado = divisao(body.a, body.b);
  
res.send(`O resultado da divisão de ${body.a} e ${body.b} é ${resultado}`);
});
```

## Indo para o POSTMAN testar verificar o código:
1. Depois de já ter executado a porta no terminal do vs code
2. Vá para o postman e rode a porta http://localhost:3001/ e clique em "send". Assim como na imagem abaixo:
   
![image](https://github.com/jardianagalvao/site-soma/assets/145692852/81074325-529e-47be-ad98-fe9c3915c8fb)


3. Depois teste cada um dessa forma:
## SOMA
![image](https://github.com/jardianagalvao/site-soma/assets/145692852/2ee3db55-5d3b-47e3-b524-929b525517e5)

## SUBTRAÇÃO

![image](https://github.com/jardianagalvao/site-soma/assets/145692852/f13b4cbf-aa34-46d9-9562-7d2ef50fe888)

## MULTIPLICAÇÃO
![image](https://github.com/jardianagalvao/site-soma/assets/145692852/342289a5-1f2f-48a9-8c8f-abb195dddced)

## DIVISÃO
![image](https://github.com/jardianagalvao/site-soma/assets/145692852/f36ee6be-0e1b-4ab3-8457-406cc62d6033)

