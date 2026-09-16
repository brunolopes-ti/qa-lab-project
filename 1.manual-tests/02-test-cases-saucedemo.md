# Casos de Teste – QA Lab (SauceDemo)

## CT-01 - Login com credenciais válidas

**ID:** CT-01  
**Descrição:** Validar o comportamento do sistema ao inserir credenciais corretas.  
**Pré-condição:** Usuário na página de login.

### Passos:
1. Inserir usuário válido.
2. Inserir senha válida.
3. Clicar em Login.

### Resultado Esperado:
O sistema deve permitir o login e redirecionar o usuário para a página de produtos.

### Resultado Obtido:
Usuário redirecionado para a página de produtos.

### Status:
Aprovado

### Observação de Ambiente:
Em ambiente corporativo com extensões habilitadas, o sistema apresentou erro de renderização na etapa de checkout.

Em ambiente limpo, utilizando aba anônima, o fluxo ocorreu normalmente.

**Conclusão:** indício de interferência externa, como extensão ou política do ambiente, não caracterizando defeito funcional da aplicação.

---

## CT-02 - Login com senha inválida

**ID:** CT-02  
**Descrição:** Validar o comportamento do sistema ao inserir um usuário válido com senha incorreta.  
**Pré-condição:** Usuário na página de login.

### Passos:
1. Inserir usuário válido (`standard_user`).
2. Inserir senha inválida.
3. Clicar em Login.

### Resultado Esperado:
O sistema deve impedir o login e exibir mensagem informando que as credenciais são inválidas.

### Resultado Obtido:
Mensagem exibida:

`Epic sadface: Username and password do not match any user in this service.`

Usuário permaneceu na tela de login.

### Status:
Aprovado

---

## CT-03 - Login com usuário inválido

**ID:** CT-03  
**Descrição:** Validar o comportamento do sistema ao inserir usuário inexistente.  
**Pré-condição:** Usuário na página de login.

### Passos:
1. Inserir usuário inválido.
2. Inserir senha válida.
3. Clicar em Login.

### Resultado Esperado:
O sistema deve impedir o login e exibir mensagem informando que as credenciais são inválidas.

### Resultado Obtido:
Mensagem exibida:

`Epic sadface: Username and password do not match any user in this service.`

Usuário permaneceu na tela de login.

### Status:
Aprovado

---

## CT-04 - Validação de campos obrigatórios no login

**ID:** CT-04  
**Descrição:** Validar as mensagens apresentadas quando os campos obrigatórios do login não são preenchidos.  
**Pré-condição:** Usuário na página de login.

### Passos:

#### Execução 1 - Usuário em branco
1. Deixar usuário e senha vazios.
2. Clicar em Login.

#### Execução 2 - Senha em branco
1. Informar um usuário válido (`standard_user`).
2. Deixar a senha vazia.
3. Clicar em Login.

### Resultado Esperado:
- Na primeira execução, o sistema deve impedir o login e informar que o usuário é obrigatório.
- Na segunda execução, o sistema deve impedir o login e informar que a senha é obrigatória.

### Resultado Obtido:
**Execução 1:**

`Epic sadface: Username is required.`

**Execução 2:**

`Epic sadface: Password is required.`

O usuário permaneceu na tela de login em ambas as execuções.

### Status:
Aprovado

### Observação de Ambiente:
Durante a execução inicial, o navegador realizou tradução automática das mensagens do sistema, alterando o texto exibido.

Os testes foram reexecutados com a tradução desativada para garantir fidelidade às mensagens originais da aplicação.

---

## CT-05 - Login com usuário bloqueado

**ID:** CT-05  
**Descrição:** Validar o comportamento do sistema ao tentar login com usuário bloqueado.  
**Pré-condição:** Usuário na página de login.

### Passos:
1. Inserir usuário `locked_out_user`.
2. Inserir senha válida (`secret_sauce`).
3. Clicar em Login.

### Resultado Esperado:
O sistema deve impedir o login e exibir mensagem informando que o usuário está bloqueado.

### Resultado Obtido:
Mensagem exibida:

`Epic sadface: Sorry, this user has been locked out.`

Usuário permaneceu na tela de login.

### Status:
Aprovado

---

## CT-06 - Adicionar produtos ao carrinho

**ID:** CT-06  
**Descrição:** Validar se o sistema permite adicionar produtos ao carrinho e atualizar o contador corretamente.  
**Pré-condição:** Usuário logado com credenciais válidas.

### Passos:
1. Realizar login com usuário válido.
2. Clicar em "Add to cart" em um produto.
3. Adicionar um segundo produto.
4. Remover um dos produtos.

### Resultado Esperado:
- Ao adicionar um produto, o contador do carrinho deve exibir `1`.
- Ao adicionar mais produtos, o contador deve incrementar conforme a quantidade adicionada.
- Ao remover um produto, o contador deve decrementar corretamente.

### Resultado Obtido:
Ao adicionar um produto, o contador exibiu `1`.

Ao adicionar múltiplos produtos, o contador foi incrementado corretamente.

Ao remover um produto, o contador foi decrementado conforme esperado.

### Status:
Aprovado

### Ambiente de Teste:
Execução realizada em aba anônima para evitar interferência de extensões ou tradução automática.

---

## CT-07 - Validação dos produtos no carrinho

**ID:** CT-07  
**Descrição:** Validar se os produtos adicionados são exibidos corretamente na página do carrinho.  
**Pré-condição:** Usuário logado com dois produtos adicionados ao carrinho.

### Passos:
1. Adicionar dois produtos ao carrinho.
2. Clicar no ícone do carrinho.

### Resultado Esperado:
- Os dois produtos devem estar listados.
- Nome e preço devem corresponder aos produtos selecionados.
- Deve existir botão "Checkout".
- Deve existir botão "Continue Shopping".

### Resultado Obtido:
Os dois produtos foram exibidos corretamente na página do carrinho.

Os nomes e preços corresponderam aos produtos selecionados.

Os botões "Checkout" e "Continue Shopping" estavam visíveis e funcionais.

### Status:
Aprovado

---

## CT-08 - Acesso à página de Checkout

**ID:** CT-08  
**Descrição:** Validar a navegação para a página de checkout após adicionar produto ao carrinho.  
**Pré-condição:** Usuário logado com ao menos um produto no carrinho.

### Passos:
1. Adicionar produto ao carrinho.
2. Clicar no ícone do carrinho.
3. Clicar no botão "Checkout".

### Resultado Esperado:
O sistema deve redirecionar para a página de checkout.

Devem existir os campos:

- First Name
- Last Name
- Zip/Postal Code

Devem existir os botões:

- Cancel
- Continue

### Resultado Obtido:
A navegação ocorreu corretamente.

Os campos obrigatórios e botões foram exibidos conforme esperado.

### Status:
Aprovado

---

## CT-09 - Validação de campo obrigatório no Checkout

**ID:** CT-09  
**Descrição:** Validar a mensagem de erro ao tentar prosseguir no checkout sem preencher os campos obrigatórios.  
**Pré-condição:** Usuário na página de checkout.

### Passos:
1. Deixar todos os campos vazios.
2. Clicar no botão "Continue".

### Resultado Esperado:
O sistema deve impedir o avanço e exibir mensagem informando o primeiro campo obrigatório não preenchido.

### Resultado Obtido:
Mensagem exibida:

`Error: First Name is required`

### Status:
Aprovado

---

## CT-10 - Validação de campo obrigatório (Last Name)

**ID:** CT-10  
**Descrição:** Validar a mensagem de erro ao tentar prosseguir no checkout sem preencher o campo Last Name.  
**Pré-condição:** Usuário na página de checkout.

### Passos:
1. Preencher o campo First Name.
2. Deixar o campo Last Name vazio.
3. Preencher o campo Zip/Postal Code.
4. Clicar no botão "Continue".

### Resultado Esperado:
O sistema deve impedir o avanço e exibir mensagem informando que o campo Last Name é obrigatório.

### Resultado Obtido:
Mensagem exibida:

`Error: Last Name is required`

### Status:
Aprovado

---

## CT-11 - Validação de campo obrigatório (Postal Code)

**ID:** CT-11  
**Descrição:** Validar a mensagem de erro ao tentar prosseguir no checkout sem preencher o campo Zip/Postal Code.  
**Pré-condição:** Usuário na página de checkout.

### Passos:
1. Preencher First Name.
2. Preencher Last Name.
3. Deixar o campo Zip/Postal Code vazio.
4. Clicar no botão "Continue".

### Resultado Esperado:
O sistema deve impedir o avanço e exibir mensagem informando que o campo Postal Code é obrigatório.

### Resultado Obtido:
Mensagem exibida:

`Error: Postal Code is required`

### Status:
Aprovado

---

## CT-12 - Validação da página Checkout: Overview

**ID:** CT-12  
**Descrição:** Validar se as informações exibidas na página de resumo da compra estão corretas.  
**Pré-condição:** Usuário logado com produto(s) no carrinho e dados de checkout preenchidos corretamente.

### Passos:
1. Adicionar produto(s) ao carrinho.
2. Acessar o carrinho.
3. Clicar em "Checkout".
4. Preencher todos os campos obrigatórios.
5. Clicar em "Continue".

### Resultado Esperado:
- Os produtos devem estar listados corretamente.
- Os preços individuais devem corresponder aos valores exibidos na loja.
- O subtotal deve ser a soma correta dos produtos.
- O valor da taxa deve estar informado.
- O total deve ser calculado corretamente: subtotal + taxa.
- Deve existir o botão "Finish".

### Resultado Obtido:
Os produtos foram exibidos corretamente.

Os preços individuais corresponderam aos valores da loja.

O subtotal foi calculado corretamente.

O valor da taxa foi exibido.

O total foi calculado corretamente.

O botão "Finish" estava visível e funcional.

### Status:
Aprovado

---

## CT-13 - Finalização da compra

**ID:** CT-13  
**Descrição:** Validar se o sistema finaliza a compra corretamente após confirmação.  
**Pré-condição:** Usuário na página Checkout: Overview com produto(s) no pedido.

### Passos:
1. Na página Overview, clicar no botão "Finish".

### Resultado Esperado:
- O sistema deve redirecionar para a página de confirmação.
- Deve ser exibida mensagem de sucesso da compra.
- Deve existir botão "Back Home".

### Resultado Obtido:
Mensagem exibida:

`Thank you for your order!`

`Your order has been dispatched, and will arrive just as fast as the pony can get there!`

O botão "Back Home" estava visível.

Ao clicar em "Back Home", o sistema retornou à página inicial exibindo os produtos.

### Status:
Aprovado

---

## CT-14 - Finalização da compra com carrinho vazio

**ID:** CT-14  
**Descrição:** Verificar o comportamento da aplicação ao tentar concluir uma compra sem produtos no carrinho.  
**Pré-condição:** Usuário autenticado com o carrinho vazio.

### Passos:
1. Acessar o carrinho sem adicionar produtos.
2. Clicar em "Checkout".
3. Preencher First Name, Last Name e Zip/Postal Code.
4. Clicar em "Continue".
5. Clicar em "Finish".

### Resultado Esperado:
Considerando a regra de negócio adotada neste exercício, o sistema deveria impedir a conclusão de uma compra sem produtos no carrinho.

### Resultado Obtido:
O sistema permitiu avançar por todas as etapas do checkout e finalizar a compra mesmo com o carrinho vazio.

Mensagem exibida:

`Thank you for your order!`

### Status:
Reprovado

### Defeito Relacionado:
**BUG-001 – Sistema permite finalizar compra com carrinho vazio.**

---

## CT-15 - Adição de produto ao carrinho com error_user

**ID:** CT-15  
**Descrição:** Validar o comportamento da aplicação ao adicionar o produto Sauce Labs Fleece Jacket ao carrinho utilizando o usuário `error_user`.  
**Pré-condição:** Usuário autenticado com `error_user`.

### Passos:
1. Realizar login com o usuário `error_user`.
2. Localizar o produto "Sauce Labs Fleece Jacket".
3. Clicar em "Add to cart".
4. Verificar o contador do carrinho.
5. Verificar o estado do botão do produto.

### Resultado Esperado:
- O produto deve ser adicionado ao carrinho.
- O contador do carrinho deve ser atualizado.
- O botão deve mudar de "Add to cart" para "Remove".

### Resultado Obtido:
O produto não foi adicionado ao carrinho.

O contador não foi atualizado.

O botão permaneceu como "Add to cart".

Nenhuma mensagem de erro foi apresentada pela aplicação.

### Status:
Reprovado

### Defeito Relacionado:
**BUG-002 – Produto Sauce Labs Fleece Jacket não é adicionado ao carrinho com error_user.**

---

# Resumo da Execução

| Indicador | Resultado |
|---|---:|
| Casos documentados | 15 |
| Casos aprovados | 13 |
| Casos reprovados | 2 |
| Bugs relacionados | 2 |
| Taxa de aprovação | 86,6% |

Os dois casos reprovados possuem defeitos documentados e rastreáveis no projeto.