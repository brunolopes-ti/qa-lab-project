# Relatório de Bugs – QA Lab (SauceDemo)

Este documento reúne os defeitos identificados durante a execução dos testes manuais do projeto.

Os defeitos estão relacionados aos casos de teste documentados em:

[`1.manual-tests/02-test-cases-saucedemo.md`](../1.manual-tests/02-test-cases-saucedemo.md)

---

# BUG-001 – Sistema permite finalizar compra com carrinho vazio

**ID:** BUG-001  
**Caso relacionado:** CT-14  
**Severidade:** Alta  
**Prioridade:** Alta  
**Status:** Aberto

## Ambiente

- Aplicação: SauceDemo
- Navegador: Google Chrome
- Sistema Operacional: Windows
- Execução: ambiente limpo / aba anônima

## Pré-condição

- Usuário autenticado.
- Carrinho sem produtos.

## Passos para reproduzir

1. Realizar login na aplicação.
2. Acessar o carrinho sem adicionar produtos.
3. Clicar em "Checkout".
4. Preencher os campos:
   - First Name
   - Last Name
   - Zip/Postal Code
5. Clicar em "Continue".
6. Clicar em "Finish".

## Resultado Esperado

Considerando a regra de negócio adotada neste exercício, o sistema deveria impedir a conclusão de uma compra sem produtos no carrinho.

## Resultado Obtido

O sistema permite avançar pelo processo de checkout e concluir a compra mesmo sem produtos adicionados ao carrinho.

A aplicação exibe a mensagem:

`Thank you for your order!`

## Evidência

A execução e o resultado estão documentados no caso:

[CT-14 – Finalização da compra com carrinho vazio](../1.manual-tests/02-test-cases-saucedemo.md#ct-14---finalização-da-compra-com-carrinho-vazio)

## Impacto

A conclusão de um pedido sem itens pode gerar registros inconsistentes e comprometer a integridade do fluxo de compra.

## Observação

Como a aplicação utilizada é um ambiente público de demonstração e não há acesso aos requisitos oficiais do produto, o comportamento esperado foi definido como regra de negócio adotada para fins deste exercício prático de QA.

---

# BUG-002 – Produto Sauce Labs Fleece Jacket não é adicionado ao carrinho com error_user

**ID:** BUG-002  
**Caso relacionado:** CT-15  
**Severidade:** Major  
**Prioridade:** Alta  
**Status:** Aberto

## Ambiente

- Aplicação: SauceDemo
- Usuário: `error_user`
- Navegador: Google Chrome
- Sistema Operacional: Windows
- Execução: ambiente limpo / aba anônima

## Pré-condição

- Usuário autenticado utilizando `error_user`.
- Produto "Sauce Labs Fleece Jacket" disponível na página de produtos.

## Passos para reproduzir

1. Realizar login utilizando `error_user`.
2. Localizar o produto "Sauce Labs Fleece Jacket".
3. Clicar em "Add to cart".
4. Verificar o contador do carrinho.
5. Verificar o estado do botão do produto.

## Resultado Esperado

Ao clicar em "Add to cart", o sistema deveria:

- adicionar o produto ao carrinho;
- atualizar o contador do carrinho;
- alterar o botão de "Add to cart" para "Remove".

## Resultado Obtido

O produto não é adicionado ao carrinho.

O contador do carrinho não é atualizado.

O botão permanece como "Add to cart".

Nenhuma mensagem de erro é apresentada pela aplicação.

## Evidências

Caso relacionado:

[CT-15 – Adição de produto ao carrinho com error_user](../1.manual-tests/02-test-cases-saucedemo.md#ct-15---adição-de-produto-ao-carrinho-com-error_user)

Execução com falha no Qase:

![Execução do cenário com falha](../3.evidencias/qase/qase-execucao-defeito-failed.png)

Defeito registrado no Qase:

![Defeito registrado no Qase](../3.evidencias/qase/qase-defeito-registrado.png)

Reteste:

![Reteste do defeito](../3.evidencias/qase/qase-reteste.png)

## Impacto

A falha impede que o usuário adicione um produto específico ao carrinho, comprometendo diretamente uma funcionalidade essencial do fluxo de compra.

## Reteste

O cenário foi executado novamente após o registro do defeito.

O problema foi reproduzido novamente nas mesmas condições:

- o produto continuou não sendo adicionado;
- o contador continuou sem atualização;
- o botão permaneceu como "Add to cart".

Como não houve correção na aplicação, o defeito permaneceu com status:

`Open`

---

# Resumo dos Defeitos

| ID | Defeito | Caso | Severidade | Status |
|---|---|---|---|---|
| BUG-001 | Compra concluída com carrinho vazio | CT-14 | Alta | Aberto |
| BUG-002 | Produto não é adicionado com `error_user` | CT-15 | Major | Aberto |

---

# Fluxo aplicado

Os defeitos foram tratados seguindo o fluxo:

```text
Execução do caso
      ↓
Identificação da divergência
      ↓
Reprodução do comportamento
      ↓
Comparação entre esperado e obtido
      ↓
Registro do defeito
      ↓
Vinculação ao caso de teste
      ↓
Reteste