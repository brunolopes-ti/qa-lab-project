# Casos de Teste – QA Lab (SauceDemo)

Este documento apresenta os 15 casos manuais do projeto, seus procedimentos, resultados registrados e evidências disponíveis.

## Ambiente e dados de teste

- Aplicação: SauceDemo;
- Sistema operacional: Windows;
- Navegador: Google Chrome;
- Credenciais públicas de demonstração:
  - Usuário padrão: `standard_user`;
  - Usuário bloqueado: `locked_out_user`;
  - Usuário utilizado na reprodução da falha de adição: `error_user`;
  - Senha: `secret_sauce`.

As versões do navegador e do sistema operacional não foram registradas.

Os procedimentos abaixo adotam `standard_user` para os cenários comuns, `locked_out_user` para o CT-05 e `error_user` para o CT-15. Quando o registro histórico não identifica os dados utilizados, essa limitação é indicada.

## Leitura dos resultados

Os status históricos foram preservados. A revisão dos procedimentos não representa uma nova execução de todos os casos.

Em 16/09/2026, foram documentados:

- Adição de Backpack com `standard_user`, na execução R-3 do Qase, cobrindo parte do CT-06;
- Reprodução do CT-14, fora da R-3;
- Reprodução do CT-15, na execução R-3.

Datas e dados ausentes nos registros antigos não foram preenchidos retroativamente.

---

## CT-01 - Login com credenciais válidas

**Descrição:** Validar o acesso com credenciais corretas.

### Pré-condições

- Página de login aberta;
- Usuário sem sessão autenticada.

### Dados do procedimento

- Usuário: `standard_user`;
- Senha: `secret_sauce`.

### Passos

1. Preencher o usuário.
2. Preencher a senha.
3. Clicar em `Login`.
4. Verificar a página apresentada.

### Resultado esperado

A aplicação deve permitir o login e apresentar a página de produtos.

### Resultado obtido registrado

O usuário foi redirecionado para a página de produtos.

### Status registrado

**Aprovado.**

O registro histórico informa credenciais válidas, sem especificar o usuário utilizado naquela execução.

---

## CT-02 - Login com senha inválida

**Descrição:** Validar a rejeição de uma senha incorreta para um usuário válido.

### Pré-condições

- Página de login aberta;
- Usuário sem sessão autenticada.

### Dados

- Usuário: `standard_user`;
- Senha: valor não vazio diferente de `secret_sauce`.

O valor exato da senha inválida não foi preservado no registro histórico.

### Passos

1. Preencher `standard_user`.
2. Preencher uma senha inválida.
3. Clicar em `Login`.
4. Verificar a mensagem e a permanência na página de login.

### Resultado esperado

A aplicação deve impedir o acesso e informar que as credenciais não correspondem a um usuário válido.

### Resultado obtido registrado

O usuário permaneceu na página de login. A mensagem foi transcrita no registro original como:

```text
Epic sadface: Username and password do not match any user in this service.
```

### Status registrado

**Aprovado.**

---

## CT-03 - Login com usuário inválido

**Descrição:** Validar a rejeição de um usuário inexistente.

### Pré-condições

- Página de login aberta;
- Usuário sem sessão autenticada.

### Dados

- Usuário: valor não vazio que não corresponda a uma conta de demonstração;
- Senha: `secret_sauce`.

O usuário inválido exato não foi preservado no registro histórico.

### Passos

1. Preencher um usuário inexistente.
2. Preencher a senha.
3. Clicar em `Login`.
4. Verificar a mensagem e a permanência na página de login.

### Resultado esperado

A aplicação deve impedir o acesso e informar que as credenciais são inválidas.

### Resultado obtido registrado

O usuário permaneceu na página de login. A mensagem foi transcrita no registro original como:

```text
Epic sadface: Username and password do not match any user in this service.
```

### Status registrado

**Aprovado.**

---

## CT-04 - Validação de campos obrigatórios no login

**Descrição:** Validar as mensagens de obrigatoriedade dos campos de login.

### Pré-condições

- Página de login aberta;
- Usuário sem sessão autenticada;
- Tradução automática desativada.

### Passos

#### Execução 1 — Campos vazios

1. Deixar usuário e senha vazios.
2. Clicar em `Login`.
3. Verificar a mensagem apresentada.

#### Execução 2 — Senha vazia

1. Preencher o usuário com `standard_user`.
2. Manter a senha vazia.
3. Clicar em `Login`.
4. Verificar a mensagem apresentada.

### Resultado esperado

- Execução 1: impedir o login e informar que o usuário é obrigatório;
- Execução 2: impedir o login e informar que a senha é obrigatória.

A primeira execução verifica a mensagem prioritária quando ambos os campos estão vazios.

### Resultado obtido registrado

As mensagens foram transcritas no registro original como:

**Execução 1:**

```text
Epic sadface: Username is required.
```

**Execução 2:**

```text
Epic sadface: Password is required.
```

O usuário permaneceu na página de login nas duas execuções.

### Status registrado

**Aprovado.**

### Observação

Na execução inicial, a tradução automática alterou o texto apresentado. O registro informa que os testes foram repetidos com a tradução desativada.

---

## CT-05 - Login com usuário bloqueado

**Descrição:** Validar a rejeição de acesso de uma conta bloqueada.

### Pré-condições

- Página de login aberta;
- Usuário sem sessão autenticada.

### Dados

- Usuário: `locked_out_user`;
- Senha: `secret_sauce`.

### Passos

1. Preencher o usuário.
2. Preencher a senha.
3. Clicar em `Login`.
4. Verificar a mensagem e a permanência na página de login.

### Resultado esperado

A aplicação deve impedir o acesso e informar que o usuário está bloqueado.

### Resultado obtido registrado

O usuário permaneceu na página de login. A mensagem foi transcrita no registro original como:

```text
Epic sadface: Sorry, this user has been locked out.
```

### Status registrado

**Aprovado.**

---

## CT-06 - Adicionar produtos ao carrinho

**Descrição:** Validar a atualização do contador ao adicionar e remover produtos.

### Pré-condições do procedimento

- Usuário autenticado com `standard_user`;
- Página de produtos aberta;
- Carrinho vazio.

### Passos

1. Selecionar dois produtos distintos e registrar seus nomes.
2. Clicar em `Add to cart` no primeiro produto.
3. Verificar se o contador exibe `1`.
4. Adicionar o segundo produto.
5. Verificar se o contador exibe `2`.
6. Remover um dos produtos.
7. Verificar se o contador volta a exibir `1`.

### Resultado esperado

O contador deve refletir a quantidade de produtos: `1`, depois `2` e, após a remoção, `1`.

### Resultado obtido histórico

O registro informa que o contador foi incrementado ao adicionar produtos e decrementado após a remoção.

Os nomes dos produtos e o usuário da execução histórica não foram especificados. O modo informado foi janela anônima.

### Status registrado

**Aprovado.**

### Verificação complementar — 16/09/2026

Na execução R-3 do Qase, o SAUCE-7 / CT-05 verificou a adição de um Sauce Labs Backpack com `standard_user`, em janela normal e com carrinho inicialmente vazio.

Foram confirmados:

- Contador com valor `1`;
- Botão alterado para `Remove`;
- Backpack presente no carrinho;
- Quantidade `1`;
- Preço `$29.99`.

Essa verificação cobre a adição de um produto. Não representa nova execução das etapas de adição do segundo produto e remoção.

[Evidência do Backpack no carrinho](../3.evidencias/qase/qase-sauce-7-backpack-carrinho.png)

---

## CT-07 - Validação dos produtos no carrinho

**Descrição:** Validar os produtos e os elementos apresentados na página do carrinho.

### Pré-condições do procedimento

- Usuário autenticado com `standard_user`;
- Dois produtos distintos já adicionados ao carrinho;
- Nomes e preços dos produtos registrados para comparação.

### Passos

1. Clicar no ícone do carrinho.
2. Conferir os dois produtos listados.
3. Comparar nomes e preços com os produtos selecionados.
4. Verificar a presença dos botões `Checkout` e `Continue Shopping`.

### Resultado esperado

- Os dois produtos devem estar presentes;
- Nomes e preços devem corresponder aos produtos selecionados;
- Os botões `Checkout` e `Continue Shopping` devem estar visíveis.

### Resultado obtido registrado

Os dois produtos foram exibidos, com nomes e preços correspondentes aos selecionados. Os botões estavam visíveis.

### Status registrado

**Aprovado.**

### Limite do registro

Os produtos e preços históricos não foram detalhados. Este caso verifica a presença dos botões; o funcionamento de ambos não está demonstrado pelos passos registrados.

---

## CT-08 - Acesso à página de Checkout

**Descrição:** Validar a navegação do carrinho para a identificação do comprador.

### Pré-condições do procedimento

- Usuário autenticado com `standard_user`;
- Pelo menos um produto já adicionado ao carrinho.

### Passos

1. Acessar o carrinho.
2. Clicar em `Checkout`.
3. Verificar a página apresentada.
4. Conferir os campos e botões disponíveis.

### Resultado esperado

A aplicação deve apresentar os campos:

- `First Name`;
- `Last Name`;
- `Zip/Postal Code`.

Também deve apresentar os botões:

- `Cancel`;
- `Continue`.

### Resultado obtido registrado

A navegação ocorreu e os campos e botões foram exibidos.

### Status registrado

**Aprovado.**

---

## CT-09 - Validação de campo obrigatório no Checkout

**Descrição:** Validar a mensagem prioritária ao enviar o formulário com todos os campos vazios.

### Pré-condição

Página de identificação do comprador aberta.

### Passos

1. Deixar `First Name`, `Last Name` e `Zip/Postal Code` vazios.
2. Clicar em `Continue`.
3. Verificar a mensagem apresentada e se houve avanço.

### Resultado esperado

A aplicação deve impedir o avanço e informar que `First Name` é obrigatório.

### Resultado obtido registrado

Mensagem registrada:

```text
Error: First Name is required
```

### Status registrado

**Aprovado.**

### Limite do cenário

Este teste verifica a mensagem prioritária com todos os campos vazios. Ele não isola a ausência de First Name com os outros dois campos preenchidos.

---

## CT-10 - Validação de campo obrigatório (Last Name)

**Descrição:** Validar a obrigatoriedade de Last Name.

### Pré-condição

Página de identificação do comprador aberta.

### Passos

1. Preencher `First Name`.
2. Deixar `Last Name` vazio.
3. Preencher `Zip/Postal Code`.
4. Clicar em `Continue`.
5. Verificar a mensagem e se houve avanço.

### Resultado esperado

A aplicação deve impedir o avanço e informar que Last Name é obrigatório.

### Resultado obtido registrado

```text
Error: Last Name is required
```

### Status registrado

**Aprovado.**

Os valores preenchidos nos demais campos não foram preservados no registro histórico.

---

## CT-11 - Validação de campo obrigatório (Postal Code)

**Descrição:** Validar a obrigatoriedade de Zip/Postal Code.

### Pré-condição

Página de identificação do comprador aberta.

### Passos

1. Preencher `First Name`.
2. Preencher `Last Name`.
3. Deixar `Zip/Postal Code` vazio.
4. Clicar em `Continue`.
5. Verificar a mensagem e se houve avanço.

### Resultado esperado

A aplicação deve impedir o avanço e informar que Postal Code é obrigatório.

### Resultado obtido registrado

```text
Error: Postal Code is required
```

### Status registrado

**Aprovado.**

Os valores preenchidos nos demais campos não foram preservados no registro histórico.

---

## CT-12 - Validação da página Checkout: Overview

**Descrição:** Conferir os produtos, os valores e os elementos apresentados no resumo da compra.

### Pré-condições do procedimento

- Usuário autenticado com `standard_user`;
- Produtos já adicionados ao carrinho;
- Nomes, quantidades e preços registrados para comparação;
- Página de identificação do comprador aberta.

### Passos

1. Preencher os campos obrigatórios do checkout.
2. Clicar em `Continue`.
3. Conferir os produtos e os preços na página Overview.
4. Calcular a soma dos preços considerando as quantidades.
5. Comparar essa soma com `Item total`.
6. Verificar a exibição de `Tax`.
7. Somar o subtotal e a taxa exibida.
8. Comparar a soma com `Total`.
9. Verificar a presença do botão `Finish`.

### Resultado esperado

- Produtos e preços correspondentes aos selecionados;
- Subtotal igual à soma dos itens;
- Taxa apresentada;
- Total igual ao subtotal mais a taxa exibida;
- Botão `Finish` visível.

### Resultado obtido histórico

O registro informa que os produtos e preços correspondiam aos selecionados, o subtotal e o total estavam corretos, a taxa era exibida e o botão Finish estava visível.

### Status registrado

**Aprovado — conforme registro histórico.**

### Limites da comprovação

Os produtos, quantidades, preços e valores calculados não foram preservados na documentação original. Por isso, a conferência aritmética histórica não pode ser reconstruída a partir deste documento.

A verificação da taxa abrange sua apresentação e inclusão na soma. Não valida uma regra fiscal oficial.

O acionamento de Finish pertence ao CT-13. A presença do botão neste caso não comprova seu funcionamento.

---

## CT-13 - Finalização da compra

**Descrição:** Validar a confirmação da compra e o retorno à página de produtos.

### Pré-condições

- Usuário na página Checkout: Overview;
- Pelo menos um produto no pedido;
- Dados obrigatórios do checkout preenchidos.

### Passos

1. Clicar em `Finish`.
2. Verificar a página de confirmação e as mensagens apresentadas.
3. Verificar a presença de `Back Home`.
4. Clicar em `Back Home`.
5. Verificar o retorno à página de produtos.

### Resultado esperado

- Página de confirmação apresentada;
- Mensagem de sucesso exibida;
- Botão `Back Home` visível;
- Retorno à página de produtos após o clique.

### Resultado obtido registrado

Foram registradas as mensagens:

```text
Thank you for your order!
```

```text
Your order has been dispatched, and will arrive just as fast as the pony can get there!
```

O botão Back Home estava visível. O registro informa que, após seu acionamento, a aplicação retornou à página de produtos.

### Status registrado

**Aprovado.**

A validação abrange a interface da aplicação de demonstração, sem confirmação de processamento real de pagamento ou entrega.

---

## CT-14 - Finalização da compra com carrinho vazio

**Descrição:** Verificar a tentativa de concluir uma compra sem produtos.

### Pré-condições

- Usuário autenticado com `standard_user`;
- Carrinho vazio.

### Dados da reprodução de 16/09/2026

| Campo | Valor |
| --- | --- |
| First Name | Teste |
| Last Name | QA |
| Zip/Postal Code | 70000000 |

### Ambiente da reprodução

- Windows;
- Google Chrome;
- Janela normal.

### Passos

1. Acessar o carrinho e confirmar a ausência de produtos.
2. Clicar em `Checkout`.
3. Preencher os dados indicados.
4. Clicar em `Continue`.
5. Verificar os itens e valores na página Overview.
6. Clicar em `Finish`.
7. Verificar a página e a mensagem apresentadas.

### Resultado esperado

Conforme a regra de negócio adotada neste exercício, a aplicação deveria impedir a conclusão de uma compra sem produtos.

Essa regra não foi obtida de requisitos oficiais da SauceDemo.

### Resultado obtido

Na reprodução de 16/09/2026, a aplicação apresentou o Overview sem produtos e com os valores:

| Campo | Valor exibido |
| --- | --- |
| Item total | $0 |
| Tax | $0.00 |
| Total | $0.00 |

Após clicar em Finish, foi apresentada a página `checkout-complete.html` com a mensagem:

```text
Thank you for your order!
```

### Status

**Reprovado em relação à regra adotada no exercício.**

### Evidências

- [Carrinho vazio](../3.evidencias/checkout/bug-001-carrinho-vazio.png);
- [Overview sem produtos](../3.evidencias/checkout/bug-001-overview-sem-produtos.png);
- [Confirmação após checkout vazio](../3.evidencias/checkout/bug-001-compra-finalizada-sem-produtos.png).

### Defeito relacionado

[BUG-001 — consultar relatório](../2.bug-reports/report-bugs.md)

Esta reprodução foi realizada separadamente da execução R-3 do Qase.

---

## CT-15 - Adição de produto ao carrinho com error_user

**Descrição:** Validar a adição do Sauce Labs Fleece Jacket com `error_user`.

### Pré-condições

- Usuário autenticado com `error_user`;
- Página de produtos aberta;
- Carrinho vazio;
- Sauce Labs Fleece Jacket disponível com o botão `Add to cart`.

### Passos

1. Localizar o Sauce Labs Fleece Jacket.
2. Clicar em `Add to cart`.
3. Verificar o contador do carrinho.
4. Verificar o botão do produto.
5. Acessar o carrinho.
6. Verificar a presença do produto.

### Resultado esperado

- Produto adicionado;
- Contador exibindo `1`;
- Botão alterado para `Remove`;
- Fleece Jacket presente na página do carrinho.

### Resultado obtido histórico

O registro inicial informa:

- Produto não adicionado;
- Contador sem atualização;
- Botão mantido como `Add to cart`;
- Nenhuma mensagem de erro apresentada na interface.

### Reprodução de 16/09/2026

A execução R-3 foi realizada no Google Chrome, em janela normal, com `error_user` e carrinho inicialmente vazio.

Após tentar adicionar o Fleece Jacket e abrir o carrinho, o produto não estava presente e o carrinho permanecia vazio.

### Status

**Reprovado.**

No Qase, o SAUCE-5 / CT-07 foi registrado como **Failed** e vinculado ao defeito existente **D-1**, mantido como **Open**.

### Evidências

- [Carrinho vazio após tentativa de adição](../3.evidencias/qase/sauce-5-error-user-carrinho-vazio.png);
- [Resultado da R-3](../3.evidencias/qase/qase-validacao-carrinho-2026-09-16.png);
- [Vínculo do D-1 com a R-3](../3.evidencias/qase/qase-defeito-d1-vinculo-r3.png).

### Defeito relacionado

[BUG-002 / D-1 — consultar relatório](../2.bug-reports/report-bugs.md)

A nova execução confirmou a persistência da falha. Não houve validação de uma correção.

---

## Resumo dos resultados registrados

| Indicador | Resultado |
| --- | ---: |
| Casos documentados | 15 |
| Casos registrados como aprovados | 13 |
| Casos registrados como reprovados | 2 |
| Bugs relacionados na documentação atual | 2 |
| Taxa de aprovação registrada | 86,7% |

Este resumo consolida os status documentados. Não representa uma única execução dos 15 casos em 16/09/2026.

As limitações dos registros históricos, incluindo a ausência de dados numéricos no CT-12, permanecem descritas nos respectivos casos.

## Correspondência com o Qase

| Cenário | Caso manual | Identificação atual no Qase |
| --- | --- | --- |
| Adição de produto com standard_user | CT-06, cobertura parcial na R-3 | SAUCE-7 / CT-05 |
| Adição de Fleece Jacket com error_user | CT-15 | SAUCE-5 / CT-07 |

A R-3 possui dois casos executados: um Passed e um Failed.

O CT-14 foi reproduzido separadamente e não faz parte dessa execução.

## Observações históricas de ambiente

Foi relatado um erro de renderização no checkout em ambiente corporativo com extensões habilitadas. O registro informa que o comportamento não foi reproduzido em janela anônima.

A causa não foi determinada. Essa comparação, isoladamente, não permite atribuir o problema a extensões ou políticas corporativas, nem descartar um defeito da aplicação.

O uso de janela anônima também não garante, por si só, um ambiente controlado.

## Limites e manutenção dos registros

- As datas das execuções históricas não foram preservadas neste documento;
- As versões do sistema operacional e do navegador não foram registradas;
- Dados históricos não especificados não foram inventados;
- As mensagens de login foram mantidas conforme a transcrição original, sem nova validação literal nesta revisão;
- Os procedimentos foram ajustados para eliminar duplicidade entre preparação e execução;
- Os resultados históricos não devem ser interpretados como comprovação de etapas adicionais;
- Nas próximas execuções, registrar dados, versões, valores esperados e obtidos junto às evidências.