## Plano de Teste – QA Lab (SauceDemo)


### 1. Objetivo  

Definir a estratégia, escopo e abordagem de testes aplicados à aplicação web SauceDemo, garantindo a validação do fluxo principal de autenticação e compra.

### 2. Escopo  

Os testes serão aplicados nos seguintes módulos da aplicação:  

### 2.1 Autenticação

- Login com credenciais válidas  

- Login com senha inválida  

- Login com usuário inválido  

- Validação de campos obrigatórios  

- Usuário bloqueado  

### 2.2 Carrinho  

- Adição de produtos  

- Validação de contador de itens

- Remoção de produtos

### 2.3 Checkout  

- Validação de campos obrigatórios  

- Validação de cálculo (Subtotal, taxa, total)  

- Finalização da compra  

### 3. Fora de Escopo  

- Testes de performance  

- Testes de segurança  

- Testes de carga  

- Integrações externas  

### 4. Estratégia de Teste  

Os testes serão executados manualmente, com foco em:

- Testes funcionais  

- Testes positivos  

- Testes negativos  

- Testes exploratórios  

A execução seguirá casos de teste previamente documentados.  

### 5. Tipos de Teste Aplicados

- Teste Funcional  

- Teste Negativo  

- Teste Exploratório  

- Teste de Regressão (básico)  

### 6. Ambiente de Teste  

- **Sistema Operacional:** Windows  

- **Navegador:** Google Chrome (modo anônimo)  

- **Editor:** Visual Studio Code  

- **Controle de Versão:** Git  

- **Repositório:** GitHub  

- **Aplicação Testada:** SauceDemo  

### 7. Critérios de Entrada

- Aplicação disponível  

- Ambiente configurado  

- Casos de teste documentados  

### 8. Critérios de Saída  

- Todos os casos executados  

- Resultados documentados  

- Defeitos registrados (quando aplicável)  

### 9. Riscos  

- Ambiente público de demonstração pode não apresentar falhas reais  

- Limitação de acesso ao código-fonte  

### 10. Métricas de Execução  

- Total de Casos de Teste: 13  

- Casos Aprovados: 13  

- Casos Reprovados: 0  

- Defeitos Encontrados: 0  