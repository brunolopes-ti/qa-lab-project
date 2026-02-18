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
Mensagem exibida: "O nome de usuário e a senha não correspondem a nenhum usuário neste serviço."  
Usuário permaneceu na tela de login.

### Status:  
Aprovado

### Observação: 

A palavra **"correspondem"** no **Resultado Obtido** foi alterada automaticamente pelo sistema para **"exigem"**, resultando em uma frase gramaticalmente estranha. Apesar dessa alteração, a funcionalidade do sistema foi atendida corretamente.


## CT-03 - Login com usuário inválido

**ID:** CT-03  
**Descrição:** Validar comportamento do sistema oa inserir usuário inexistente.  
**Pré-condição:** Usuário na página de login.  

### Passos:  
1. Inserir usuário inválido.  
2. Inserir senha válida.  
3. Clicar em login.  

### Resultado Esperado:  
O sistema deve impedir o login e exibir mensagem informando que as credenciais são inválidas.  

### Resultado Obtido:  
Mensagem exibida: "O nome de usuário e a senha não correspondem a nenhum usuário neste serviço."  
Usuário permanceu na tela de login.  

### Status:  
Aprovado