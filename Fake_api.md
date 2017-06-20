# Criando uma fake API com Json-Server

Bom galera, nas minhas andanças na internet, encontrei uma forma muito legal para gerar alguns endpoints para treinar a automação =).

Para criar o endpoint vamos precisar instalar o node e o json server via npm:

```ruby

Linux:

curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -

sudo apt-get install jq nodejs curl -qy

npm install -g json-server

Mac:

brew install npm

npm install -g json-server
```
Depois o json server instalado, o que vamos fazer é criar uma pasta com um nome qualquer (vou chamar de fakeapi) e dentro dessa pasta eu vou criar um arquivo chamado endpoints.json da seguinte maneira:

```ruby
{
  "clientes": [
    {
      "id": 1,
      "nome": "Nome Teste",
      "cpf": "123.456.789-0",
      "endereco": "Rua Teste dos teste",
      "usuario": "usuario",
      "senha": "senha"
    }
  ]
}
```

Então agora vamos rodar o servidor para validar se deu tudo certo:

```ruby
json-server --watch endpoints.json

O resultado será esse:

\{^_^}/ hi!

Loading db.json
Done

Resources
http://localhost:3000/clientes

Home
http://localhost:3000

Type s + enter at any time to create a snapshot of the database
Watching...
```

Então basta abrir o navegador e ver se o endpoint ta funcionando colocando 'http://localhost:3000/clientes' e o resultado será assim:

```ruby
{
  "id": 1,
  "nome": "Nome Teste",
  "cpf": "123.456.789-0",
  "endereco": "Rua Teste dos teste",
  "usuario": "usuario",
  "senha": "senha"
}
```

OK, com o endpoint funcionando, bora [automatizar](https://github.com/thiagomarquessp/httpartyforall/blob/master/Criando_arquivos_Feature.md).