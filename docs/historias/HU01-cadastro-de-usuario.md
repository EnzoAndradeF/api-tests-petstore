# HU01 - Cadastro de Usuário

### História de Usuário
**Como um visitante do sistema  
Quero me cadastrar como usuário  
Para que eu possa acessar e utilizar a aplicação**

### Regras de Negócio
1. O cadastro deve aceitar os seguintes campos:
   - nome
   - email
   - password
   - administrador (true ou false)

2. Todos os campos são obrigatórios
3. O campo **email deve ser único**
4. A senha deve conter no mínimo **5 caracteres**
5. Ao cadastrar com sucesso:
   - Status code: **201**
   - Deve retornar mensagem de sucesso
   - Deve retornar o **_id do usuário**
6. Não deve permitir cadastro com:
   - Email já existente
   - Campos vazios
   - Dados inválidos

## Casos de teste

| ID | CT01.01 |
|------|----------|
| **Objetivo** | Realizar o cadastro com credenciais válidas |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "enzo comum",
  "email": "enzocomum@qa.com.br",
 "password": "teste",
  "administrador": "true" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e Id do usuário|

| ID | CT01.02 |
|------|----------|
| **Objetivo** | Realizar o cadastro com email já cadastrado |
| **Pré-condições** | Email já cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "Fulano da Silva",
  "email": "beltrano@qa.com.br",
 "password": "teste",
  "administrador": "true" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |
| **Resultado Esperado** |status code 400|

| ID | CT01.03 |
|------|----------|
| **Objetivo** | Realizar o cadastro com senha de 4 caracteres |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "Fulano da Silva",
  "email": "beltrano@qa.com.br",
 "password": "abcd",
  "administrador": "true" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |
| **Resultado Esperado** |Senha inválida|

| ID | CT01.04 |
|------|----------|
| **Objetivo** | Realizar o cadastro com senha de 5 caracteres |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "Fulano da Silva",
  "email": "beltrano@qa.com.br",
 "password": "abcde",
  "administrador": "true" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e Id do usuário|

| ID | CT01.05 |
|------|----------|
| **Objetivo** | Realizar o cadastro com senha de 6 caracteres |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "Fulano da Silva",
  "email": "beltrano@qa.com.br",
 "password": "abcdef",
  "administrador": "true" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso e Id do usuário|

| ID | CT01.06 |
|------|----------|
| **Objetivo** | Realizar o cadastro com campos vazios |
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
 "nome": "",
  "email": "",
 "password": "",
  "administrador": "" |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint  |
| **Resultado Esperado** |status code 400|

## Evidências

