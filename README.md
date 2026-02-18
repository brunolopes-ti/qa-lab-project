# QA Lab – Testes Manuais em Aplicação Web (SauceDemo)

##  Objetivo

Este projeto tem como objetivo aplicar e demonstrar conhecimentos em testes manuais de software, utilizando uma aplicação web de e-commerce como estudo de caso.

Foi realizado o planejamento, elaboração e execução de casos de teste cobrindo o fluxo completo do usuário, desde autenticação até finalização de compra.

O projeto simula um cenário real de validação funcional, com documentação estruturada e controle de versionamento.

---

##  Escopo dos Testes

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

##  Ambiente de Teste

- Sistema Operacional: Windows
- Navegador: Google Chrome (modo anônimo)
- Editor: Visual Studio Code
- Controle de versão: Git
- Repositório hospedado no GitHub
- Aplicação testada: SauceDemo

---

##  Estrutura do Projeto  

qa-lab-project/
│
├── README.md  
└── manual-tests/  
├── README.md  
└── test-cases-saucedemo.md  

---

##  Resumo de Execução

| ID     | Cenário                             | Status   |
|--------|--------------------------------------|----------|
| CT-01  | Login válido                         | Aprovado |
| CT-02  | Senha inválida                       | Aprovado |
| CT-03  | Usuário inválido                     | Aprovado |
| CT-04  | Campos obrigatórios no login         | Aprovado |
| CT-05  | Usuário bloqueado                    | Aprovado |
| CT-06  | Adição de produto ao carrinho        | Aprovado |
| CT-07  | Validação de produtos no carrinho    | Aprovado |
| CT-08  | Acesso ao checkout                   | Aprovado |
| CT-09  | First Name obrigatório               | Aprovado |
| CT-10  | Last Name obrigatório                | Aprovado |
| CT-11  | Postal Code obrigatório              | Aprovado |
| CT-12  | Validação da página Overview         | Aprovado |
| CT-13  | Finalização da compra                | Aprovado |

---

##  Metodologia Utilizada

- Elaboração de casos de teste estruturados com ID único
- Separação clara entre Resultado Esperado e Resultado Obtido
- Execução controlada em ambiente limpo (modo anônimo)
- Registro literal das mensagens retornadas pelo sistema
- Organização dos cenários por fluxo funcional

---

##  Próximos Passos

- Elaboração de Plano de Teste formal
- Ampliação da cobertura para novos cenários
- Implementação futura de automação de testes

