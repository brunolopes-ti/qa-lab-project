## Plano de Teste – QA Lab (SauceDemo)

### 1. Objetivo

Definir a estratégia, escopo e abordagem de testes aplicados à aplicação web SauceDemo, garantindo a validação do fluxo principal de autenticação e compra.

### 2. Escopo

Os testes serão aplicados nos seguintes módulos da aplicação:

### 2.1 Autenticação

- Login com credenciais válidas;
- Login com senha inválida;
- Login com usuário inválido;
- Validação de campos obrigatórios;
- Usuário bloqueado.

### 2.2 Carrinho

- Adição de produtos;
- Validação de contador de itens;
- Remoção de produtos.

### 2.3 Checkout

- Validação de campos obrigatórios;
- Conferência dos produtos e valores apresentados no Overview;
- Validação do subtotal pela soma dos itens;
- Verificação da taxa exibida;
- Validação do total pela soma do subtotal com a taxa exibida;
- Finalização da compra.

> A conferência da taxa exibida não representa validação de uma regra fiscal oficial da aplicação.

### 3. Fora de Escopo

- Testes de performance;
- Testes de segurança;
- Testes de carga;
- Integrações externas.

### 4. Estratégia de Teste

Os testes serão executados manualmente, com foco em:

- Testes funcionais;
- Testes positivos;
- Testes negativos;
- Testes de regressão básica.

A execução seguirá casos de teste previamente documentados.

Testes exploratórios podem ser utilizados como abordagem complementar, porém não há sessão exploratória formal documentada nesta versão do projeto.

### 5. Tipos de Teste Aplicados

- Teste Funcional;
- Teste Positivo;
- Teste Negativo;
- Teste de Regressão (básico).

### 6. Ambiente de Teste

- **Sistema Operacional:** Windows;
- **Navegador:** Google Chrome;
- **Modo inicialmente adotado:** janela anônima;
- **Execuções complementares:** também realizadas em janela normal, conforme documentação dos casos;
- **Editor:** Visual Studio Code;
- **Controle de Versão:** Git;
- **Repositório:** GitHub;
- **Aplicação Testada:** SauceDemo.

### 7. Critérios de Entrada

- Aplicação disponível;
- Ambiente configurado;
- Casos de teste documentados.

### 8. Critérios de Saída

- Todos os casos executados;
- Resultados documentados;
- Defeitos registrados, quando aplicável.

### 9. Riscos

- Ambiente público de demonstração pode não apresentar falhas reais;
- Limitação de acesso ao código-fonte.

### 10. Métricas de Execução

- Total de Casos de Teste: 15;
- Casos Aprovados: 13;
- Casos Reprovados: 2;
- Defeitos Encontrados: 2;
- Taxa de Aprovação: 86,7%.