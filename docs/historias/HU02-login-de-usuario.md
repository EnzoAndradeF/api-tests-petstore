# HU02 - Login de Usuário

### História de Usuário
**Como usuário cadastrado  
Quero realizar login no sistema  
Para acessar funcionalidades restritas**

### Regras de Negócio
1. O login deve aceitar:
   - email
   - password

2. O email e senha devem corresponder a um usuário válido
3. Ao logar com sucesso:
   - Status code: **200**
   - Deve retornar um **token de autenticação**
4. O token deve ser utilizado nas requisições protegidas
5. Não deve permitir login com:
   - Email inexistente
   - Senha incorreta
   - Campos vazios

## Casos de teste

| ID | CT02.01 |
|------|----------|
| **Objetivo** | Login com credenciais válidas |
| **Pré-condições** |  Usuário cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
  "email": "fulano@qa.com",
  "password": "teste" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint login
 Preencher a propriedade “nome”
 Preencher a propriedade “password” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e token de autorização|

## Casos de teste

| ID | CT02.02 |
|------|----------|
| **Objetivo** | Login com email inexistente |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
  "email": "inexistente@email.com",
  "password": "teste" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint login
 Preencher a propriedade “nome”
 Preencher a propriedade “password” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|

| ID | CT02.02 |
|------|----------|
| **Objetivo** | Login com senha incorreta |
| **Pré-condições** | Usuário cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
  "email": "teste",
  "password": "teste" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint login
 Preencher a propriedade “nome”
 Preencher a propriedade “password” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|

| ID | CT02.03 |
|------|----------|
| **Objetivo** | Login com campos vazios |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
  "email": "",
  "password": "" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint login |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|