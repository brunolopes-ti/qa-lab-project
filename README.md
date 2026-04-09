## QA Lab – Testes Manuais em Aplicação Web (SauceDemo)

###  Objetivo

Este projeto tem como objetivo validar funcionalidades críticas de uma aplicação web, identificar falhas e garantir a qualidade do fluxo de compra sob a perspectiva do usuário final.

---

###  Escopo dos Testes

Os testes contemplam:

- Autenticação (login válido e inválido)
- Validação de mensagens de erro
- Manipulação de carrinho (adição de produtos)
- Validação de contador de itens
- Fluxo de checkout
- Validação de campos obrigatórios
- Validação de cálculo de valores (subtotal, taxa e total)
- Finalização da compra

---

###  Ambiente de Teste

- Sistema Operacional: Windows
- Navegador: Google Chrome (modo anônimo)
- Editor: Visual Studio Code
- Controle de versão: Git
- Repositório hospedado no GitHub
- Aplicação testada: SauceDemo

---

###  Estrutura do Projeto  

```
qa-lab-project/
│
├── manual-tests/
├── bug-reports/
└── README.md/
```
---

###  Resumo de Execução

|   ID   |               Cenário                     |   Status   |
|--------|-------------------------------------------|------------|
| CT-01  | Login válido                              |  Aprovado  |
| CT-02  | Senha inválida                            |  Aprovado  |
| CT-03  | Usuário inválido                          |  Aprovado  |
| CT-04  | Campos obrigatórios no login              |  Aprovado  |
| CT-05  | Usuário bloqueado                         |  Aprovado  |
| CT-06  | Adição de produto ao carrinho             |  Aprovado  |
| CT-07  | Validação de produtos no carrinho         |  Aprovado  |
| CT-08  | Acesso ao checkout                        |  Aprovado  |
| CT-09  | First Name obrigatório                    |  Aprovado  |
| CT-10  | Last Name obrigatório                     |  Aprovado  |
| CT-11  | Postal Code obrigatório                   |  Aprovado  |
| CT-12  | Validação da página Overview              |  Aprovado  |
| CT-13  | Finalização da compra                     |  Aprovado  |
| CT-14  | Finalizar compra com carrinho vazio       |  Reprovado |  
| CT-15  | Validação de dados inválidos no checkout  |  Reprovado |
---

### Bugs Encontrados

Durante a execução dos testes, foram identificados defeitos críticos que afetam diretamente a integridade do sistema.  

- BUG-001: Sistema permite finalizar compra com carrinho vazio   
- BUG-002: Falta de validação nos campos do checkout  

Os bugs detalhados estão documentados na pasta '/bug-reports'.

### Impacto de Negócio

Os defeitos encontrados podem impactar diretamente:

- Geração de pedidos inválidos   
- Inconsistência em dados de clientes   
- Problemas operacionais e financeiros   
- Experiência negativa do usuário   

Este tipo de análise reforça a importância da qualidade no ciclo de desenvolvimento.

###  Metodologia Utilizada

- Elaboração de casos de teste estruturados com ID único.
- Separação clara entre Resultado Esperado e Resultado Obtido.
- Execução controlada em ambiente limpo (modo anônimo).
- Registro literal das mensagens retornadas pelo sistema.
- Organização dos cenários por fluxo funcional.

---