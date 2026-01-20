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