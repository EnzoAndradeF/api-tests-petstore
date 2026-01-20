# HU03 - Atualização de Status do Pet

## História de usuário

**Como usuário
Quero atualizar o status de um pet
Para refletir sua situação atual**

## Regras de negócio

1. Deve permitir atualizar o status do pet

4. O status só pode ser:
    - available
    - pending
4. Após atualização:
    - O pet deve refletir o novo status na consulta

5. Deve retornar erro ao tentar atualizar pet inexistente

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