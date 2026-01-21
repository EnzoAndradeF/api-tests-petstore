### HU03 – Cadastro de Produto (Usuário Administrador)

### História de Usuário
**Como usuário administrador  
Quero cadastrar um produto  
Para que ele possa ser vendido no sistema**

### Regras de Negócio
1. O cadastro deve aceitar:
   - nome
   - preco
   - descricao
   - quantidade

2. Apenas usuários com perfil **administrador** podem cadastrar produtos
3. A requisição deve conter:
   - Header `Authorization` com token válido
4. Ao cadastrar com sucesso:
   - Status code: **201**
   - Deve retornar o **_id do produto**
5. Não deve permitir cadastro com:
   - Token inválido ou ausente
   - Campos obrigatórios vazios
   - Valores inválidos (ex: preço negativo)

## Casos de teste

| ID | CT03.01 |
|------|----------|
| **Objetivo** | Cadastro de produto com usuário comum |
| **Pré-condições** | Usuário comum autenticado / produto não deve estar cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "Logitech MX Vertical",
  "preco": 470,
  "descricao": "Mouse",
  "quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade "preco"
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|

| ID | CT03.02 |
|------|----------|
| **Objetivo** | Cadastro de produto com usuário administrador |
| **Pré-condições** | Usuário administrador autenticado / produto não deve estar cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "Logitech MX Vertical",
  "preco": 470,
  "descricao": "Mouse",
  "quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade "preco"
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e Id do produto|

| ID | CT03.03 |
|------|----------|
| **Objetivo** | Cadastro de produto com token expirado |
| **Pré-condições** | Usuário administrador com token expirado / produto não deve estar cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "Logitech MX Vertical",
  "preco": 470,
  "descricao": "Mouse",
  "quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade “password” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|

| ID | CT03.04 |
|------|----------|
| **Objetivo** | Cadastro de produto com campos vazios |
| **Pré-condições** | Usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "",
  "preco": ,
  "descricao": "",
  "quantidade":  |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade "preco"
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e Id do produto|

| ID | CT03.05 |
|------|----------|
| **Objetivo** | Cadastro de produto com preço negativo |
| **Pré-condições** | Usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "Logitech MX Vertical",
  "preco": -50,
  "descricao": "Mouse",
  "quantidade": 381  |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade "preco"
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|

| ID | CT03.06 |
|------|----------|
| **Objetivo** | Cadastro de produto com quantidade negativo |
| **Pré-condições** | Usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
   "nome": "Logitech MX Vertical",
  "preco": 50,
  "descricao": "Mouse",
  "quantidade": -381  |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade "preco"
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |
| **Resultado Esperado** |O sistema deve retornar o status code 401, mensagem de erro|