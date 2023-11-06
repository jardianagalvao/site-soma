# Entregavel03-Ambientes
Terceiro entregável da disciplina de Ambiente e Desenvolvimento de Software, Prof. Alzir

## Criar um novo projeto
Crie uma pasta chamada 'site-soma'.
Abra essa nova pasta no Visual Studio Code (Arquivo > Abrir e selecione a pasta).
Em seguida, abra o terminal e execute o comando a seguir npm init -y para criar um novo projeto NPM.

## Instalar o Express
No terminal do Visual Studio Code, execute o comando para instalar o Express npm install express.

## Criar servidor
Com o Express instalado, deve-se criar um servidor.
Crie primeiro um arquivo chamado app.js
Copie o código a seguir nele:

'var express = require('express');
var app = express();

app.get('/', function(req, res) {
  res.send('Oi, mundo :-)');
});

var port = 3001;

// iniciando o processo do servidor
app.listen(port, function() {
  console.log(`App de Exemplo escutando na porta http://localhost:${port}/`);
});' 

## Executando o servidor
No terminal do Vs Code, execute o comando `node app.js` 
Abra o seu navegador na url [http://localhost:3001](http://localhost:3001).

## Criar uma requisição POST
Copie e cole no arquivo que foi criado recente esse código:

'app.post('/soma', function (req, res) {
  res.send('Response da requisição POST');
});'

## Consumir dados do POST
Instale a biblioteca body-parser. Essa biblioteca nos ajuda a fazer a leitura dos dados via POST

Para instalar, execute o comando npm install body-parser no terminal do Visual Studio Code.

Logo após a declaração da variável app, cole o código a seguir:

'var bodyParser = require('body-parser');
app.use(bodyParser.json());'

Em seguida, no corpo da função post, cole o seguinte código:

'var body = req.body;
console.log(body);
res.send('via post');'

Pronto. Salve o arquivo, execute 'npm app.js' no terminal! Isso faz com que ele execute.

## Criando uma função soma
Veja a função soma a seguir e como integrar ela em seu site.

'function soma(a, b) {
  return a + b;
}'

Copie e cole essa função para o arquivo 'app.js' e em seguida substitua o código a seguir no corpo da função post.

'var body = req.body;
var resultado = soma(body.a, body.b);

res.send(`O resultado da soma de ${body.a} e ${body.b} é ${resultado}`);'

Para criar as outras funções de subtração, divisão e multiplicação, basta se basear em como foi feito a função soma conforme poderemos ver a seguir

## Indo para o POSTMAN testar verificar o código:
Depois de já ter executado a porta no terminal do vs code
Vá para o postman e rode a porta http://localhost:3001/ e clique em "send". Assim como na imagem abaixo: 

image

Depois teste cada um dessa forma: image
