# HU02 - Consulta de Pet por ID

## História de usuário

**Como usuário
Quero consultar um pet pelo seu ID
Para visualizar suas informações**

## Regras de negócio

1. Deve retornar o pet quando o ID existir
2. Deve retornar 404 quando o ID não existir
4. O response deve conter:
    - id
    - name
    - status

5. O formato da resposta deve estar em JSON válido

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