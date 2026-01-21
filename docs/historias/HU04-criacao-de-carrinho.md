## HU04 – Criação de Carrinho / Compra

### História de Usuário
**Como usuário autenticado  
Quero criar um carrinho de compras  
Para realizar uma compra de produtos**

### Regras de Negócio
1. O carrinho deve aceitar:
   - Lista de produtos
   - Quantidade de cada produto

2. O usuário deve estar autenticado
3. O produto deve existir
4. A quantidade solicitada não pode exceder o estoque disponível
5. Ao criar o carrinho com sucesso:
   - Status code: **201**
   - Deve retornar mensagem de sucesso
6. Não deve permitir:
   - Carrinho vazio
   - Produto inexistente
   - Quantidade maior que o estoque

| ID | CT04.01 |
|------|----------|
| **Objetivo** | Criação de carrinho com sucesso |
| **Pré-condições** | Usuário autenticado / produto cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
"idProduto": "BeeJh5lz3k6kSIzA",
"quantidade": 1
"idProduto": "YaeJ455lz3k6kSIzA",
"quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade”|
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso|

| ID | CT04.02 |
|------|----------|
| **Objetivo** | Criação de carrinho com token expirado |
| **Pré-condições** | Usuário com token expirado / produto cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
"idProduto": "BeeJh5lz3k6kSIzA",
"quantidade": 1
"idProduto": "YaeJ455lz3k6kSIzA",
"quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade”| |
| **Resultado Esperado** |O sistema deve retornar o status code 201, mensagem de sucesso|

| ID | CT04.03 |
|------|----------|
| **Objetivo** | Criação de carrinho com produto inexistente |
| **Pré-condições** | Usuário com token expirado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
"idProduto": "BeeJh5lz3k6kSIzA",
"quantidade": 1
"idProduto": "YaeJ455lz3k6kSIzA",
"quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade”| |
| **Resultado Esperado** |O sistema deve retornar o status code 400, mensagem de erro|

| ID | CT04.04 |
|------|----------|
| **Objetivo** | Criação de carrinho com quantidade de produto maior que o estoque |
| **Pré-condições** | Usuário autenticado / produto cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
"idProduto": "BeeJh5lz3k6kSIzA",
"quantidade": 1
"idProduto": "YaeJ455lz3k6kSIzA",
"quantidade": 381 |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade”| |
| **Resultado Esperado** |O sistema deve retornar o status code 400, mensagem de erro|

| ID | CT04.04 |
|------|----------|
| **Objetivo** | Criação de carrinho com campos vazios |
| **Pré-condições** | Usuário autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |
| **Massa de Dados:** |
"idProduto": "",
"quantidade": 
"idProduto": "",
"quantidade":  |
| **Ação** |
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade”| |
| **Resultado Esperado** |O sistema deve retornar o status code 400, mensagem de erro|