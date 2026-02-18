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

