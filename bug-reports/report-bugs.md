# Relatório de Bugs 

Este documento contém os bugs identificados durante a execução dos testes. 

---

## Bug 01 - O sistema permite finalizar uma compra sem itens no carrinho. 

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

Print

### Impacto 

Permite criação de pedidos sem itens, comprometendo a integridade do sistema e podendo gerar inconsistências operacionais e financeiras.

