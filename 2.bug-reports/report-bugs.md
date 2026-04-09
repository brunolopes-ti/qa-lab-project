# Relatório de Bugs 

Este documento contém os bugs identificados durante a execução dos testes. 

---

## Bug 01 - O sistema permite finalizar uma compra com o carrinho vazio. 

**ID:** BUG-001  
**Severidade:** Alta  
**Prioridade:** Alta  
**Status:** Aberto

### Ambiente 

- Navegador: Google Chrome 122.0.0.0
- Sistema Operacional: Windows 11 

### Pré-condição 

- Carrinho vazio

### Passos para reproduzir 

1. Acessar página do carrinho
2. Clicar em "Checkout" 
3. Inserir os dados: "First Name", "Last Name" e "Zip/Postal Code" 
4. Clicar em "Continue" 
5. Clicar em "Finish"  

### Resultado esperado 

Sistema deve impedir a finalização da compra com o carrinho vazio. 

### Resultado obtido 

O sistema permite finalizar a compra sem itens no carrinho e exibe a mensagem: "Thank you for your order! Your order has been dispatched, and will arrive just as fast as the pony can get there!"

### Evidências 

- Print

### Impacto 

Permite criação de pedidos sem itens, comprometendo a integridade do sistema e podendo gerar inconsistências operacionais e financeiras.


## Bug 02 - Falta de validação nos campos do formulário de checkout. 

**ID:** BUG-002  
**Severidade:** Média  
**Prioridade:** Alta  
**Status:** Aberto  

### Ambiente 

 - Navegador: Google Chrome 122.0.0.0  
 - Sistema Operacional: Windows 11  
 
 ### Pré-condição  
 
 - Usuário na etapa de checkout com carrinho contendo itens.  
 
 ### Passos para reproduzir  

 1. Acessar página de Checkout   
 2. Preencher as informações: "First Name", "Last Name" e "Zip/Postal Code" com dados inválidos  
 3. Clicar em "Continue"  
 4. Clicar em "Finish"  
 
 ### Cenários testados 

 - Nome com números 
 - Nome com caracteres especiais 
 - CEP com letras 
 - Campos combinados inválidos 
 
 ### Resultado esperado 
 
 Sistema deve validar os campos e exibir mensagens específicas indicando quais dados estão inválidos, impedindo o avanço no fluxo de checkout. 
 
 ### Resultado obtido 
 
 O sistema permite finalizar a compra com as informações de usuário inválidas e exibe a mensagem: "Thank you for your order! Your order has been dispatched, and will arrive just as fast as the pony can get there!" 
 
 ### Evidências 
 
 - Print 
 
 ### Impacto 
 
 Permite criação de pedidos com dados inválidos, comprometendo a integridade do sistema e podendo gerar inconsistências operacionais e financeiras.



