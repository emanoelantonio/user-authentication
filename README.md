# User Authentication
Este é um projeto de autenticação de usuário usado para estudo, tendo como meta a Prova de Conhecimentos Aplicados da __SERPRO 2023__.
## Introdução
Esta documentação descreve a API desenvolvida em Nodejs, que segue as práticas de desenvolvimento de software como TDD(Test-Driven Development), Clean Code e boas práticas recomendadas.
## Configurando o Ambiente
Para configurar o ambiente de desenvolvimento, siga os passos abaixo:
> 1. Instale o Node.js e o npm em sua máquina.
> 2. Clone este repositório.
> 3. Na pasta do projeto, execute o comando `npm install` para instalar as dependências.
## Estrutura do Projeto
```
/user-authentication
  | - /src
    | - /controllers
    | - /middlewares
    | - /models
    | - /routes
  | - /_testes_
    | - /unit
```
## Executando os Testes
Para executar os teste unitários em Jest, utilize o seguinte comando: `npm test`
## TDD (Test-Driven Development)
O desenvolvimento nesta API segue a abordagem de TDD, onde os testes são escritos antes da implementação das funcionalidades. Isso garante que o código seja mais confiável e esteja bem testado.
## Clean Code e Boas Práticas
Ao desenvolver esta API, foram seguidos princípios de Clean Code e boas Práticas recomendadas, como:
> * Uso de nomes descritivos para funções e variáveis.
> * Funções pequenas e coesas.
> * Modularização do código em componentes reutilizáveis.
## Endpoints
A seguir, estão listados os endpoints disponíveis na API:</br>
#### GET /users/:email 
> * Esta rota deve retornar um usuário, caso exista, a partir do email passado como parâmetro da rota.</br>
#### POST /login/:email 
> * Esta rota possui um middleware que recebe o password, via header da requisição, e faz uma comparação do password criptografado com o password recebido, via função comparePassword. Este middleware deve atribuir a requisição o usuário encontrado se houver, ou lançar um erro.
#### POST /users -> 
> * Esta recebe os parâmtros de cadastro (firstName, lastName, email, password) do usuário pelo body da requisição. Os campos id, createdAt e updatedAt, são criados e atualizados, no caso do updatedAt, pelo banco de dados.
#### PUT /users/:id -> 
> * Esta rota pode receber os parâmetros de cadastro (firstName, lastName, e password) do usuário pelo body da requisição. Deve-se efetuar o tratamento de dados para update e verificar se há ou não atualização do password.
#### DELETE /users/:id -> 
> * Esta rota tem a função de apagar em definitivo um registro de usuário no banco de dados. Além disso, ela deve receber como parâmetro o id do usuário.
## Exemplo de Requisição e Resposta
Requisição:
```
POST /api/users
Content-Type: application/json
{
  "name": "Jhon",
  "email": "example@email.com",
  "password": "xzy1281"
}
```
Resposta:
```
Status: 201 Created
Content-Type: application/json
{
  "id": "12345678",
  "name": "Jhon",
  "email": "example@email.com",
}
```
## Considerações Finais
Esta documentação fornece uma visão geral da API desenvolvida em Nodejs, seguindo as práticas de **TDD**, **Clean Code** e Boas práticas de desenvolvimento. Certifique-se de consultar os _testes unitários_ para entender melhor o funcionamento e os cenários testados.
