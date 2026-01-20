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


## Mind map

## Cenários de teste

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

## Evidências

