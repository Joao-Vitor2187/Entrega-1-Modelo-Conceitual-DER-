# Entrega-1-Modelo-Conceitual-DER
Modelagem de um sistema de gestão de informações para uma organização de pequeno porte    
## Metadados
**João Vitor Silva Alves Araujo RGM: 46905570**

**Raimundo Walter RGM: 46852042**

**Kaique Vieira Santos RGM: 47022493**

**Vítor Bezerra Marques RGM: 47538775**
****
## 1. Caracterização da Organização

- **Nome e natureza da organização:** Peg Vest Jeans — empresa especializada na comercialização de jeans feminino no segmento de atacado.
- **Contexto e porte:** Com fins lucrativos; pequena empresa; 20 pessoas envolvidas, volume de atividades média 
- **Problemas e necessidades identificados:** Dificuldade de controle de estoque, padronizações e processos, necessidade do uso de outros sistemas para diferentes canais de vendas, não totalmente compatíveis 
- **Justificativa da escolha:** A Peg Vest Jeans foi escolhida porque um membro de nossa equipe trabalha no local e possui proximidade com a área e facil acesso ao local e, também, por se encaixar nos parâmetros estabelecidos para a escolha da organização.
- **Evidências da organização:**
  
    Endereço : R. Rodrigues dos Santos, 718
  
    Link Google Maps: https://share.google/DAEpR3k6h6TCqBPD0

    Link site da loja: https://pegvest.com.br/
  
    Contato: (11) 96173-2019
  
    Imagens Do local:

  <img width="382" height="510" alt="image" src="https://github.com/user-attachments/assets/eb38a776-4753-43cc-a795-d5f32b7f5d3a" />

  
## 2. Processos de Negócio

- **Principais processos mapeados:** cadastro de clientes, controle de estoque, vendas, emissão de pedidos e solicitações, entregas e transferências
---
## 3. Requisitos do Sistema
*(esta seção e a Seção 4 "Regras de Negócio" DIVIDEM 7,5% na dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na organização/documentação)*

### 3.1 Requisitos Funcionais
- **Cadastrar clientes → O sistema deve permitir cadastrar nome, CPF, telefone e endereço do cliente.**
- **Cadastrar produtos → O sistema deve permitir cadastrar produtos com nome, preço e quantidade em estoque.**
- **Realizar vendas → O sistema deve permitir que o funcionário registre uma venda para um cliente.**
- **Consultar estoque → O sistema deve permitir consultar a quantidade disponível de cada produto.**
- **Atualizar estoque → Após uma venda, o sistema deve diminuir automaticamente a quantidade do produto no estoque**
- **Gerar nota fiscal → O sistema deve permitir gerar a nota fiscal referente à venda.**
- **Realizar login → O sistema deve permitir que funcionários façam login utilizando usuário e senha.**
- **Gerar relatórios → O sistema deve permitir gerar relatórios de vendas por período.**
- **Cancelar uma venda → O sistema deve permitir que um funcionário autorizado cancele uma venda.**
- **Enviar notificações → O sistema deve enviar uma notificação quando determinado produto estiver com estoque baixo**


---
### 3.2 Requisitos Não Funcionais
*Características de qualidade (ex.: desempenho, segurança, usabilidade, disponibilidade).*

---
## 4. Regras de Negócio

- ## 4.1 Regras operacionais:
- #### Cadastro 
  *O cadastro de clientes deve possuir os dados obrigatórios definidos pela empresa, incluindo CPF para clientes pessoa física e CNPJ para clientes pessoa jurídica.*
- #### Pagamento
  *Uma compra somente pode ser considerada efetuada após a confirmação do pagamento.*
  
  *O pedido não deve ser liberado para as etapas seguintes enquanto o pagamento não estiver confirmado.*
- #### Desconto
  *Compras realizadas por meio de Pix possuem desconto de 5% sobre o valor da compra.*
  
  *O desconto deve ser aplicado somente quando a forma de pagamento selecionada for Pix.*
  
  *Funcionários não possuem permissão para conceder descontos diferentes dos definidos pela empresa.*
- #### Estoque 
  *Um produto não pode ser vendido quando não houver quantidade disponível em estoque.*
  
  *Após a confirmação de uma venda, a quantidade correspondente deve ser atualizada no estoque.*
  
  *A quantidade disponível de um produto não pode assumir valores negativos.*
- #### Cancelamento
  *Um pedido pode ser cancelado somente enquanto não tiver sido enviado.*
  
  *Após o envio do pedido, o cancelamento não poderá ser realizado pelo fluxo normal do sistema.*
- #### Vendas no atacado e varejo
  *Nas vendas realizadas no atacado, os pedidos devem respeitar uma quantidade mínima de 15 peças.*
  
  *As vendas no varejo não possuem quantidade mínima de peças.*
  
  *Os preços praticados no varejo são superiores aos preços utilizados nas vendas no atacado, conforme a política comercial da empresa.*
- #### Funcionarios
- *Funcionários não podem alterar os preços dos produtos.*
  
-*Funcionários não podem conceder descontos que não estejam previamente definidos pela empresa.*
  
-*Vendedores somente podem liberar uma entrega mediante autorização da gerência.*
  
-*Alterações que afetem configurações ou regras comerciais do sistema devem ser realizadas somente por usuários autorizados*
  
- ## Restrições organizacionais:
- ### Permissões de acesso
- *Cada usuário deve possuir acesso somente aos módulos do sistema correspondentes à sua função, como vendas, estoque, financeiro ou administração.*
- *O acesso às funcionalidades do sistema deve ser controlado de acordo com o nível de permissão de cada usuário.*
-*Funcionários do setor de vendas, por exemplo, não devem possuir acesso às configurações administrativas ou informações restritas do setor financeiro.*

---

## 5. Dicionário de Dados Conceitual (Preliminar)
*(vale 10% — Dimensão Procedimental - Segue o modelo do arquivo 02-03g_Exemplo_Dicionario_Dados.pdf)*

Para cada entidade identificada, liste:

| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| *nome do atributo* | *o que ele representa* | *se houver alguma regra (obrigatoriedade, valores possíveis, etc.)* |

*Mantenha o dicionário organizado e padronizado (mesmo formato de tabela para todas as entidades).*

**Atenção à privacidade:** se forem usados exemplos de valores para ilustrar os atributos, esses exemplos devem ser **fictícios** — não utilize dados reais de clientes, fiéis, beneficiários, doadores ou funcionários da organização (nomes, CPFs, contatos etc.), mesmo que tenham sido observados durante a pesquisa de campo. Os exemplos devem apenas ser **coerentes com as operações reais** observadas.

---

## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
*(vale 7,5% na dimensão conceitual)*
| Entidade | Relaciona-se com | Justificativa |
|---|---|---|
| Empresa | Cliente | 1:N - Uma empresa atende vários clientes.  |
| Empresa | Funcionário | 1:N - Uma empresa emprega vários funcionários |
| Funcionário | Cliente | 1:N - Um funcionário atende vários clientes. |
| Funcionário | Empresa | 1:1 - Um fun |
| Fornecedor | d |  |
| Produto | c | |
| Estoque | d  | |
| Pedido | s | |
| Pagamento | d |  |



- **Entidades reconhecidas:** *liste e justifique brevemente cada uma.*
- **Atributos e classificações:** *quais atributos pertencem a cada entidade.*
- **Relacionamentos pertinentes:** *como as entidades se conectam.*
- **Restrições e políticas organizacionais aplicadas ao modelo.**

---

## 7. Diagrama Entidade-Relacionamento (DER)
*(vale 20% — é o item de maior peso da entrega)*

- Anexe o DER (em imagem).
- O diagrama deve representar corretamente:
  - Entidades
  - Atributos
  - Relacionamentos
  - **Cardinalidades**
- O modelo deve ser **consistente** e já demonstrar potencial de **escalabilidade e integração** (pensando nas próximas etapas do projeto).

---

## 8. Justificativa Técnica
*(vale 7,5% — sozinho, é o subcritério de maior peso dentro da Dimensão Conceitual)*

*Explique e defenda as decisões de abstração e modelagem tomadas: por que essas entidades, esses atributos, esses relacionamentos e essas cardinalidades — e não outras alternativas possíveis?*

---

## 9. Uso de Inteligência Artificial
*(documentação obrigatória — não é opcional se o grupo usou IA em qualquer etapa: pesquisa, escrita, organização de ideias ou revisão de texto)*

Se o grupo usou alguma ferramenta de IA (ChatGPT, Claude, Gemini, Perplexity etc.) em qualquer parte do trabalho, registre **para cada uso relevante**:

| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | Qual IA foi usada e em qual parte do trabalho (ex.: pesquisa sobre o setor da organização, redação do README, organização dos requisitos, revisão ortográfica/gramatical). |
| **Motivação** | Por que o grupo recorreu à IA nesse ponto específico. |
| **Prompt(s) utilizados** | Texto exato (ou muito próximo) do que foi perguntado/pedido à IA. |
| **Resposta recebida** | Resumo ou trecho relevante da resposta da IA. |
| **Fontes consultadas e verificadas** | Se a IA citou fontes/dados, quais foram checadas pelo grupo e como (ex.: comparação com o que foi observado na visita de campo). |
| **Trechos rejeitados ou corrigidos** | O que da resposta da IA foi descartado, editado ou corrigido manualmente, e por quê. |
| **Justificativa da escolha final** | Por que o grupo manteve, adaptou ou rejeitou o que a IA sugeriu. |
| **Reflexão crítica** | Limites, vieses ou erros identificados no uso da IA nessa etapa (ex.: informação desatualizada, alucinação, generalização incorreta sobre o tipo de organização). |

*Se o grupo não usou nenhuma ferramenta de IA, declare isso explicitamente nesta seção.*

---

## Critérios Atitudinais (20%)
**Estes critérios NÃO constam explicitamente como item de entrega no README.** Eles são avaliados por meio de **Avaliação 360º entre os integrantes do grupo** (cada membro avalia os colegas de equipe) e, no caso da Colaboração, também pela **colaboração equilibrada no histórico de commits** do repositório GitHub — não pela leitura do restante do repositório nem pela apresentação:

- **Participação (5%):** envolvimento nas discussões técnicas e nas decisões do grupo.
- **Comprometimento (5%):** cumprimento de prazos e responsabilidades assumidas.
- **Colaboração (5%):** respeito às contribuições dos colegas, cooperação na construção do projeto e colaboração equilibrada no histórico de commits do repositório GitHub.
- **Autonomia (5%):** busca independente de soluções e proposta de melhorias.

---

## Resumo dos Pesos

| Dimensão | Peso total |
|----------|-----------|
| Conceitual (contexto, requisitos/regras, modelagem, justificativa técnica) | 30% |
| Procedimental (requisitos, fluxogramas, dicionário de dados, DER) | 50% |
| Atitudinal (participação, comprometimento, colaboração, autonomia) | 20% |

**Entrega final:** README.md completo + DER + Dicionário de Dados em HTML (com exceção dos cursos GTI) anexado no repositório GitHub do grupo.
