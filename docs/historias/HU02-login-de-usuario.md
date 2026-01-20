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