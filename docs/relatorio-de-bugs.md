#  Relatório de Bugs

**Software:**  
**QA responsável:**  
**Data:** 


## Bug 01: 

### Informações do Bug

| Campo | Detalhe |
|------|--------|
| **ID** | BUG-001 |
| **Descrição** | Quando o usuário não adiciona produtos no carrinho e clica em checkout, ele avança de página quando deveria permanecer na mesma |
| **Severidade** | Alta |
| **Prioridade** | Alta |
| **Status** | Aberto |

### Passo a passo para simular

| Passo |
|------|
| 1. Estar logado no sistema com um usuário válido |
| 2. Acessar a página catálogo de compras |
| 3. Acessar a página carrinho de compras clicando no ícone do carrinho |
| 4. Clicar no botão **Checkout** |

### Resultado

| Comportamento Esperado | Comportamento Obtido |
|------------------------|---------------------|
| Exibir mensagem de erro e permanecer na página| Usuário é redirecionado para a tela de checkout |



| Ambiente |
|---------|
| Ambiente de homologação |
| Desktop – Windows 11 |
| Google Chrome V143.0.7 |
| SauceDemo |



| Caso de Teste relacionado |
|---------------|
|   |

| Funcionalidade relacionado |
|---------------|
|   |