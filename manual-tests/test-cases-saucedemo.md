## CT-01 - Login com credenciais válidas

**ID:** CT-01  
**Descrição:** Validar compotarmento do sistema ao inserir credenciais corretas.  
**Pré-condição:** Usuário na página de login.

### Passos:  
1. Inserir usuário válido.  
2. Inserir senha válida.  
3. Clicar em Login.

### Resultado Esperado:  
O sistema deve permitir o login e seguir para a página seguinte.

### Resultado Obtido:  
Usuário redirecionado para a página de produtos.

### Status:  
Aprovado

### Observação de Ambiente:  

Em ambiente corporativo com extensões habilitadas, o sistema apresentou erro de renderização na etapa de checkout.  
Em ambiente limpo (aba anônima), o fluxo ocorreu normalmente.  

**Conclusão:** Indício de interferência externa (extensão ou política de rede), não caracterizando defeito funcional da aplicação.


## CT-02 - Login com credenciais inválidas

**ID:** CT-02  
**Descrição:** Validar comportamento do sistema ao inserir senha incorreta.  
**Pré-condição:** Usuário na página de login.

### Passos:  
1. Inserir usuário inválido.  
2. Inserir senha inválida.  
3. Clicar em Login.

### Resultado Esperado:  
O sistema deve impedir o login e exibir mensagem informando ao usuário que as credenciais são inválidas.

### Resultado Obtido:  
Mensagem exibida: "Epic sadface: Username and password do not match any user in this service."  
Usuário permaneceu na tela de login.

### Status:  
Aprovado


## CT-03 - Login com usuário inválido

**ID:** CT-03  
**Descrição:** Validar comportamento do sistema ao inserir usuário inexistente.  
**Pré-condição:** Usuário na página de login.  

### Passos:  
1. Inserir usuário inválido.  
2. Inserir senha válida.  
3. Clicar em login.  

### Resultado Esperado:  
O sistema deve impedir o login e exibir mensagem informando que as credenciais são inválidas.  

### Resultado Obtido:  
Mensagem exibida: "Epic sadface: Username and password do not match any user in this service."  
Usuário permanceu na tela de login.  

### Status:  
Aprovado


## CT-04 - Tentativa de login com campos em branco

**ID:** CT-04  
**Descrição:** Validar comportamento do sistema ao tentar realizar login sem preencher usuário e senha.  
**Pré-condição:** Usuário na página de login.

### Passos:  
1. Deixar os campos de usuário e senha vazios.  
2. Clicar em Login.  

### Resultado Esperado:  
O sistema deve impedir o login e exibir mensagem solicitando o preenchimento dos campos obrigatórios.

### Resultado Obtido:  
Mensagem exibida: "Epic sadface: Username is required." e "Epic sadface: Password is required."  
Usuário permaneceu na tela de login.  

### Status:  
Aprovado

### Observação de Ambiente:  
Durante a execução inicial, o navegador realizou tradução automática das mensagens do sistema, alterando o texto exibido. 
Os testes foram reexecutados com a tradução desativada para garantir fidelidade às mensagens originais da aplicação.  


## CT-05 – Login com usuário bloqueado
 
**ID:** CT-05  
**Descrição:** Validar comportamento do sistema ao tentar login com usuário bloqueado.  
**Pré-condição:** Usuário na página de login.

### Passos:  
1. Inserir usuário locked_out_user.
2. Inserir senha válida (secret_sauce).
3. Clicar em Login.

### Resultado Esperado:  
O sistema deve impedir o login e exibir mensagem informando que o usuário está bloqueado.

### Resultado Obtido:  
Mensagem exibida: "Epic sadface: Sorry, this user has been locked out."
Usuário permaneceu na tela de login.

### Status:  
Aprovado


## CT-06 – Adicionar produtos ao carrinho

**ID:** CT-06  
**Descrição:** Validar se o sistema permite adicionar um ou mais produtos ao carrinho e atualizar o contador corretamente.  
**Pré-condição:** Usuário logado com credenciais válidas.

### Passos:
1. Realizar login com usuário válido.
2. Clicar em "Add to cart" em um produto.
3. Adicionar um segundo produto.
4. Remover um dos produtos.

### Resultado Esperado:
- Ao adicionar um produto, o contador do carrinho deve exibir "1".
- Ao adicionar mais produtos, o contador deve incrementar conforme a quantidade adicionada.
- Ao remover um produto, o contador deve decrementar corretamente.

### Resultado Obtido:
Ao adicionar um produto, o contador exibiu "1".
Ao adicionar múltiplos produtos, o contador foi incrementando corretamente.
Ao remover produtos, o contador decrementou conforme esperado.

### Status:
Aprovado

### Ambiente de Teste:  
Execução realizada em aba anônima para evitar interferência de extensões ou tradução automática.  


## CT-07 – Validação dos produtos no carrinho

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


## CT-08 – Acesso à página de Checkout

**ID:** CT-08  
**Descrição:** Validar navegação para a página de checkout após adicionar produto ao carrinho.  
**Pré-condição:** Usuário logado com ao menos um produto no carrinho.

### Passos:
1. Adicionar produto ao carrinho.
2. Clicar no ícone do carrinho.
3. Clicar no botão "Checkout".

### Resultado Esperado:
- O sistema deve redirecionar para a página de checkout.
- Devem existir os campos:
  - First Name
  - Last Name
  - Zip/Postal Code
- Devem existir os botões:
  - "Cancel"
  - "Continue"

### Resultado Obtido:
A navegação ocorreu corretamente.
Os campos obrigatórios e botões foram exibidos conforme esperado.

### Status:
Aprovado


## CT-09 – Validação de campo obrigatório no Checkout

**ID:** CT-09  
**Descrição:** Validar mensagem de erro ao tentar prosseguir no checkout sem preencher campos obrigatórios.  
**Pré-condição:** Usuário na página de checkout.

### Passos:
1. Deixar todos os campos vazios.
2. Clicar no botão "Continue".

### Resultado Esperado:
O sistema deve impedir o avanço e exibir mensagem de erro informando campo obrigatório.

### Resultado Obtido:
Mensagem exibida: "Error: First Name is required"

### Status:
Aprovado