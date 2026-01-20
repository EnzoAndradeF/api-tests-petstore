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

## Mind map



## Casos de teste
|**ID**|**Descrição**|**Pré-condições**|
|:-----|:------------|:------------|
| | | |


**Dados da requisição:**

| Campo | Descrição |
|------|----------|
| **Objetivo** | Validar o cadastro de um pet com dados válidos |
| **Pré-condições** | API Petstore disponível |
| **Método HTTP** | POST |
| **Endpoint** | /pet |
| **Headers** | Content-Type: application/json |
| **Massa de Dados** | `{ "id": 123, "name": "Rex", "status": "available" }` |
| **Ação** | Enviar requisição POST com payload válido |
| **Resultado Esperado** | Status 200 e retorno dos dados do pet cadastrado |