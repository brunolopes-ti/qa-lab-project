# QA Lab – Testes Manuais, Gestão de Testes e Validação de Bugs

![Manual Testing](https://img.shields.io/badge/Manual%20Testing-Functional%20QA-blue)
![Qase](https://img.shields.io/badge/Qase-Test%20Management-purple)
![Test Management](https://img.shields.io/badge/Test%20Management-Test%20Cases-blueviolet)
![Bug Tracking](https://img.shields.io/badge/Bug%20Tracking-Defects-red)
![Regression Testing](https://img.shields.io/badge/Regression%20Testing-QA-green)

Projeto prático de **Quality Assurance** desenvolvido para aplicar testes manuais, elaboração de casos de teste, execução funcional, identificação de defeitos, análise de impacto e gestão de testes utilizando **Qase**.

O projeto utiliza a aplicação SauceDemo para simular atividades de QA, desde o planejamento dos cenários até o registro de resultados, documentação de defeitos e acompanhamento de novas execuções.

---

## Objetivo

Validar funcionalidades de uma aplicação Web e demonstrar práticas de QA envolvendo:

- Planejamento de testes;
- Elaboração de casos de teste;
- Execução manual;
- Testes positivos e negativos;
- Testes funcionais e de regressão;
- Registro e documentação de bugs;
- Análise de impacto;
- Gestão de testes com Qase;
- Organização de casos em suítes;
- Registro de resultados em Test Runs;
- Rastreabilidade entre casos, execuções e defeitos;
- Nova execução de cenários para verificar a persistência de falhas.

---

## Tecnologias e ferramentas

- Qase;
- Google Chrome;
- SauceDemo;
- Visual Studio Code;
- Git;
- GitHub;
- Markdown.

---

## Testes manuais

### Métricas do projeto

Resultados registrados na matriz manual de 15 casos. As execuções direcionadas do Qase são apresentadas separadamente e não são somadas a essa matriz.

| Indicador | Valor |
| --- | ---: |
| Casos de teste manuais | 15 |
| Casos aprovados | 13 |
| Casos reprovados | 2 |
| Bugs documentados na versão atual do relatório | 2 |
| Taxa de aprovação | 86,7% |
| Maior severidade registrada na documentação manual | Alta |

### Escopo dos testes

Os testes manuais contemplam:

- Autenticação com credenciais válidas e inválidas;
- Usuário bloqueado;
- Validação de campos obrigatórios e mensagens de erro;
- Adição e consulta de produtos no carrinho;
- Validação do contador de itens;
- Acesso ao checkout;
- Validação dos campos obrigatórios do checkout;
- Conferência dos valores exibidos na página Overview;
- Conferência de subtotal, taxa exibida e valor total;
- Finalização da compra;
- Tentativa de finalização com carrinho vazio;
- Adição de produto utilizando `error_user`.

A conferência da taxa exibida não representa a validação de uma regra fiscal oficial da aplicação.

### Ambiente de teste

| Item | Ambiente registrado |
| --- | --- |
| Sistema operacional | Windows |
| Navegador | Google Chrome |
| Modo informado na documentação inicial | Janela anônima |
| Modo utilizado na execução R-3 de 16/09/2026 | Janela normal |
| Editor | Visual Studio Code |
| Controle de versão | Git e GitHub |
| Aplicação testada | SauceDemo |

As versões do sistema operacional e do navegador não foram registradas nesta documentação.

Aplicação: [SauceDemo](https://www.saucedemo.com/).

### Estrutura do projeto

| Caminho | Conteúdo |
| --- | --- |
| `1.manual-tests/01-test-plan.md` | Plano de testes |
| `1.manual-tests/02-test-cases-saucedemo.md` | Casos e resultados dos testes manuais |
| `2.bug-reports/report-bugs.md` | Relatório de defeitos |
| `3.evidencias/qase/` | Evidências históricas e da execução R-3 |
| `3.evidencias/checkout/` | Evidências da reprodução do BUG-001 no checkout vazio |
| `README.md` | Visão geral, resultados e rastreabilidade do projeto |

### Matriz de execução dos testes manuais

| ID | Cenário | Status |
| --- | --- | --- |
| CT-01 | Login válido | Aprovado |
| CT-02 | Senha inválida | Aprovado |
| CT-03 | Usuário inválido | Aprovado |
| CT-04 | Campos obrigatórios no login | Aprovado |
| CT-05 | Usuário bloqueado | Aprovado |
| CT-06 | Adição de produto ao carrinho | Aprovado |
| CT-07 | Validação de produtos no carrinho | Aprovado |
| CT-08 | Acesso ao checkout | Aprovado |
| CT-09 | First Name obrigatório | Aprovado |
| CT-10 | Last Name obrigatório | Aprovado |
| CT-11 | Postal Code obrigatório | Aprovado |
| CT-12 | Validação da página Overview | Aprovado |
| CT-13 | Finalização da compra | Aprovado |
| CT-14 | Finalizar compra com carrinho vazio | Reprovado |
| CT-15 | Adição de produto ao carrinho com `error_user` | Reprovado |

Os passos, as pré-condições e os resultados estão descritos no [documento de casos de teste](./1.manual-tests/02-test-cases-saucedemo.md).

### Bugs documentados nos testes manuais

A versão atual do relatório apresenta dois registros.

#### BUG-001 – Sistema permite finalizar compra com carrinho vazio

O comportamento documentado permite avançar pelo checkout e concluir uma compra sem produtos adicionados ao carrinho.

Esse registro está relacionado ao **CT-14 – Finalizar compra com carrinho vazio**.

> Como a SauceDemo é uma aplicação pública de demonstração e não há acesso aos requisitos oficiais do produto, o resultado esperado deste cenário foi definido como regra de negócio adotada para o exercício prático.

[Consultar documentação do BUG-001](./2.bug-reports/report-bugs.md).

#### BUG-002 – Produto Sauce Labs Fleece Jacket não é adicionado ao carrinho com error_user

Ao utilizar `error_user`, o produto **Sauce Labs Fleece Jacket** não é adicionado ao carrinho após clicar em `Add to cart`.

O registro inicial descreve que o contador não é atualizado e o botão permanece como `Add to cart`.

O comportamento foi registrado no Qase e reproduzido novamente em execuções posteriores. Na execução R-3, a tentativa de adição foi seguida pela abertura do carrinho, que permaneceu vazio.

Esse cenário corresponde ao **CT-15 da matriz manual** e ao **SAUCE-5 / CT-07 do Qase**. O defeito relacionado no Qase é o **D-1**.

[Consultar documentação do BUG-002](./2.bug-reports/report-bugs.md).

### Impacto de negócio

Em um produto real, comportamentos como os observados poderiam causar:

- Conclusão de pedidos sem produtos;
- Impedimento da compra de determinado produto;
- Inconsistências no fluxo de compra;
- Registros de pedidos inválidos;
- Prejuízo à experiência do usuário.

Essa análise é qualitativa e representa possíveis impactos. Não houve medição de impacto financeiro ou operacional em produção.

---

## Gestão de testes com Qase

Além da documentação manual armazenada no repositório, o projeto utiliza o **Qase** para organizar casos, registrar execuções e acompanhar um defeito.

A demonstração contempla a relação entre:

**caso de teste → suíte → execução → resultado → defeito → nova execução**

### Organização das suítes

Os sete casos estão distribuídos em três suítes:

| Suíte | Quantidade de casos |
| --- | ---: |
| Autenticação | 4 |
| Carrinho | 2 |
| Checkout | 1 |
| **Total** | **7** |

### Casos cadastrados no Qase

#### Autenticação

- CT-01 – Login com credenciais válidas;
- CT-02 – Login com credenciais inválidas;
- CT-03 – Validação de campos obrigatórios;
- CT-04 – Login com usuário bloqueado.

#### Carrinho

- CT-05 – Adicionar produto ao carrinho — **SAUCE-7**;
- CT-07 – Adicionar produto ao carrinho com `error_user` — **SAUCE-5**.

#### Checkout

- CT-06 – Finalizar compra com sucesso.

> A numeração CT utilizada nos títulos do Qase é diferente da numeração da matriz manual de 15 casos. Os identificadores SAUCE-5 e SAUCE-7 são os IDs dos registros na ferramenta.

### Propriedades utilizadas nos casos

Os casos foram classificados utilizando propriedades do Qase:

- Severity;
- Priority;
- Status;
- Type;
- Behavior;
- Layer;
- Automation Status;
- Flaky.

A documentação dos casos inclui:

- Pré-condições;
- Passos de execução;
- Dados de teste;
- Resultados esperados.

---

## Execução de regressão

Foi criado no Qase o Test Run **Execução de Regressão - SauceDemo**.

Essa execução histórica contemplou seis casos das suítes de Autenticação, Carrinho e Checkout.

### Resultado

| Indicador | Resultado |
| --- | ---: |
| Casos executados | 6 |
| Casos aprovados | 6 |
| Casos reprovados | 0 |
| Taxa de conclusão | 100% |
| Taxa de aprovação | 100% |

Os resultados dessa execução foram preservados como histórico. Eles não representam uma nova execução dos 15 casos da matriz manual.

### Evidência

![Execução de regressão no Qase](./3.evidencias/qase/qase-execucao-testes.png)

---

## Validação de defeito com error_user

Para demonstrar o registro e acompanhamento de um defeito, foi utilizado o seguinte cenário:

| Item | Valor |
| --- | --- |
| Usuário | `error_user` |
| Produto | Sauce Labs Fleece Jacket |
| Caso atual no Qase | SAUCE-5 / CT-07 |
| Caso na matriz manual | CT-15 |
| Defeito no Qase | D-1 |

### Comportamento esperado

Ao clicar em `Add to cart`, o sistema deveria:

- Adicionar o produto ao carrinho;
- Atualizar o contador de itens;
- Alterar o botão de `Add to cart` para `Remove`;
- Exibir o produto ao acessar o carrinho.

### Comportamento obtido

O registro inicial da execução descreve:

- Produto não adicionado ao carrinho;
- Botão sem alteração para `Remove`;
- Contador do carrinho sem atualização;
- Ausência de mensagem de erro visível na interface.

O caso foi registrado como **Failed**.

### Registro do defeito

O defeito foi cadastrado com o título:

**Carrinho - Produto Sauce Labs Fleece Jacket não é adicionado com error_user**

| Propriedade | Valor |
| --- | --- |
| Identificador no Qase | D-1 |
| Severidade no Qase | Major |
| Status | Open |
| Caso relacionado no Qase | SAUCE-5 / CT-07 |
| Caso relacionado na matriz manual | CT-15 |
| Resultado da execução relacionada | Failed |

O registro mantém a relação entre caso, execução e defeito.

### Evidência da execução com falha

![Execução com falha no Qase](./3.evidencias/qase/qase-execucao-defeito-failed.png)

### Evidência do defeito

![Defeito registrado no Qase](./3.evidencias/qase/qase-defeito-registrado.png)

---

## Nova execução pela funcionalidade Retest

Após o registro do defeito, o cenário foi executado novamente utilizando a funcionalidade **Retest** do Qase.

O termo identifica a funcionalidade utilizada na ferramenta. Essa execução confirmou a persistência da falha; não houve validação de uma correção disponibilizada pela aplicação.

### Resultado

O registro da nova execução informa que:

- O Fleece Jacket continuou sem ser adicionado ao carrinho;
- O contador não foi atualizado;
- O botão não mudou para `Remove`.

A execução foi vinculada ao **mesmo defeito existente**, evitando a criação de um registro duplicado.

O defeito permaneceu **Open**, e a evidência histórica apresenta o resultado **Failed +1**.

### Evidência

![Nova execução do cenário no Qase](./3.evidencias/qase/qase-reteste.png)

---

## Validação dos casos de carrinho — 16/09/2026

Na execução **R-3 — Validação dos casos de carrinho**, os dois cenários foram executados no Google Chrome, em janela normal.

Cada teste começou com o usuário correspondente autenticado e o carrinho vazio.

### Resultados

| Caso no Qase | Usuário | Produto | Resultado |
| --- | --- | --- | --- |
| SAUCE-7 / CT-05 | `standard_user` | Sauce Labs Backpack | Passed |
| SAUCE-5 / CT-07 | `error_user` | Sauce Labs Fleece Jacket | Failed |

Com `standard_user`, o Backpack foi adicionado, o contador exibiu **1** e o botão mudou para `Remove`. Ao abrir o carrinho, o produto estava presente com quantidade **1** e preço **$29.99**.

Com `error_user`, após clicar em `Add to cart` do Fleece Jacket e acessar o carrinho, o produto não estava presente. O carrinho permaneceu vazio.

O resultado com falha foi vinculado ao **D-1**, mantido como **Open**.

| Indicador da R-3 | Resultado |
| --- | ---: |
| Casos executados | 2 |
| Casos aprovados | 1 |
| Casos reprovados | 1 |
| Taxa de conclusão | 100% |
| Taxa de aprovação | 50% |

A execução foi finalizada com status geral **Failed**. Os 100% de conclusão indicam que os dois casos foram executados.

Esta execução abrange somente os dois cenários de carrinho. Ela não atualiza os resultados dos demais casos da matriz manual.

### Rastreabilidade dos casos

O **SAUCE-5** foi originalmente identificado como CT-05 e posteriormente alterado para CT-07, com `error_user`.

O cenário original foi preservado no clone **SAUCE-7**, identificado como CT-05. Os registros históricos foram mantidos; por isso, imagens antigas podem mostrar o SAUCE-5 com o título anterior.

| Cenário | Identificação atual no Qase | Correspondência na matriz manual |
| --- | --- | --- |
| Adicionar produto com `standard_user` | SAUCE-7 / CT-05 | CT-06 — cobertura parcial na R-3 |
| Adicionar Fleece Jacket com `error_user` | SAUCE-5 / CT-07 | CT-15 |

O histórico do defeito D-1 mantém os resultados anteriores da **R-2** e o resultado **Failed da R-3**.

### Evidências da validação

- [Backpack no carrinho com standard_user](./3.evidencias/qase/qase-sauce-7-backpack-carrinho.png);
- [Carrinho vazio após tentativa com error_user](./3.evidencias/qase/sauce-5-error-user-carrinho-vazio.png);
- [Resultado da execução R-3](./3.evidencias/qase/qase-validacao-carrinho-2026-09-16.png);
- [Defeito D-1 vinculado à execução R-3](./3.evidencias/qase/qase-defeito-d1-vinculo-r3.png).

---

## Fluxo de gestão demonstrado

A etapa com Qase demonstra:

1. Planejamento e criação dos casos;
2. Organização em suítes;
3. Criação de Test Runs;
4. Execução e registro dos resultados;
5. Identificação e registro da falha;
6. Vinculação entre caso, execução e defeito;
7. Nova execução para verificar a persistência da falha;
8. Manutenção do defeito como Open.

O acompanhamento documentado termina com a falha ainda reproduzível. Não houve validação de correção nem encerramento do defeito.

---

## Evidências do Qase

As evidências estão armazenadas em **`3.evidencias/qase/`**.

| Arquivo | Conteúdo |
| --- | --- |
| `qase-suite-autenticacao.png` | Organização dos casos de autenticação |
| `qase-execucao-testes.png` | Resultado da regressão histórica |
| `qase-execucao-defeito-failed.png` | Execução com falha |
| `qase-defeito-registrado.png` | Registro do defeito |
| `qase-reteste.png` | Nova execução pela funcionalidade Retest |
| `qase-sauce-7-backpack-carrinho.png` | Backpack no carrinho com standard_user |
| `sauce-5-error-user-carrinho-vazio.png` | Carrinho vazio após tentativa com error_user |
| `qase-validacao-carrinho-2026-09-16.png` | Resultado final da execução R-3 |
| `qase-defeito-d1-vinculo-r3.png` | Histórico do D-1 com vínculo à R-3 |

As imagens históricas foram preservadas para manter a rastreabilidade da evolução do projeto.

---

## Metodologia utilizada

Durante o projeto foram aplicadas práticas como:

- Identificação dos casos de teste;
- Definição de pré-condições e dados;
- Separação entre resultado esperado e resultado obtido;
- Preparação do estado inicial conforme as pré-condições;
- Utilização de cenários positivos e negativos;
- Registro das mensagens retornadas pela aplicação;
- Organização dos testes por fluxo funcional;
- Documentação de defeitos;
- Classificação de severidade;
- Organização dos casos em suítes;
- Registro de resultados em Test Runs;
- Execução de regressão;
- Nova execução de cenários com falha;
- Rastreabilidade entre caso, execução e defeito;
- Organização de evidências;
- Versionamento com Git e GitHub.

---

## Competências demonstradas

- Quality Assurance;
- Testes manuais e funcionais;
- Testes positivos e negativos;
- Testes de regressão;
- Planejamento e elaboração de casos;
- Gestão de testes com Qase;
- Test Suites e Test Runs;
- Registro e acompanhamento de defeitos;
- Classificação de severidade;
- Reprodução de falhas;
- Rastreabilidade;
- Análise qualitativa de impacto;
- Coleta de evidências;
- Documentação técnica;
- Git e GitHub.

---

## Status do projeto

**Execução R-3 finalizada em 16/09/2026. O defeito D-1 permanece aberto.**

### Documentação manual

- 15 casos documentados;
- 13 casos registrados como aprovados;
- 2 casos registrados como reprovados;
- 2 bugs descritos na versão atual do relatório;
- Análise qualitativa de impacto.

### Gestão de testes com Qase

- 3 suítes;
- 7 casos cadastrados;
- Regressão histórica com 6 de 6 casos aprovados;
- Cenário com falha reproduzível;
- Defeito D-1 registrado com severidade Major;
- Novas execuções vinculadas ao mesmo defeito;
- Execução R-3 com 2 casos executados: 1 Passed e 1 Failed;
- Evidências do comportamento da aplicação e dos resultados no Qase;
- Histórico preservado.

---

## Próximas melhorias possíveis

- Expandir a quantidade de casos gerenciados no Qase;
- Criar novos Test Runs por funcionalidade;
- Explorar planos de teste;
- Ampliar os cenários de regressão;
- Detalhar critérios de prioridade e severidade;
- Registrar versões do ambiente nas próximas execuções;
- Integrar a gestão manual com cenários automatizados.

---

## Autor

**Bruno Ramos Lopes**

LinkedIn: [linkedin.com/in/brunolopes-ti](https://linkedin.com/in/brunolopes-ti)

GitHub: [github.com/brunolopes-ti](https://github.com/brunolopes-ti)