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

---
## 4. Regras de Negócio

- ## 4.1 Regras operacionais:
- #### Cadastro 
  O cadastro de clientes deve possuir os dados obrigatórios definidos pela empresa, incluindo CPF para clientes pessoa física e CNPJ para clientes pessoa jurídica.*
- #### Pagamento
  Uma compra somente pode ser considerada efetuada após a confirmação do pagamento.*
  
  O pedido não deve ser liberado para as etapas seguintes enquanto o pagamento não estiver confirmado.
- #### Desconto
  Compras realizadas por meio de Pix possuem desconto de 5% sobre o valor da compra.
  
  O desconto deve ser aplicado somente quando a forma de pagamento selecionada for Pix.
  
  Funcionários não possuem permissão para conceder descontos diferentes dos definidos pela empresa.
- #### Estoque 
  Um produto não pode ser vendido quando não houver quantidade disponível em estoque.
  
  Após a confirmação de uma venda, a quantidade correspondente deve ser atualizada no estoque.
  
  A quantidade disponível de um produto não pode assumir valores negativos.
- #### Cancelamento
  Um pedido pode ser cancelado somente enquanto não tiver sido enviado.
  
  Após o envio do pedido, o cancelamento não poderá ser realizado pelo fluxo normal do sistema.
- #### Vendas no atacado e varejo
  Nas vendas realizadas no atacado, os pedidos devem respeitar uma quantidade mínima de 15 peças.
  
  As vendas no varejo não possuem quantidade mínima de peças.
  
  Os preços praticados no varejo são superiores aos preços utilizados nas vendas no atacado, conforme a política comercial da empresa.
- #### Funcionarios
  Funcionários não podem alterar os preços dos produtos.
  
  Funcionários não podem conceder descontos que não estejam previamente definidos pela empresa.
  
  Vendedores somente podem liberar uma entrega mediante autorização da gerência.
  
  Alterações que afetem configurações ou regras comerciais do sistema devem ser realizadas somente por usuários autorizados*
  
- ## Restrições organizacionais:
- ### Permissões de acesso
  Cada usuário deve possuir acesso somente aos módulos do sistema correspondentes à sua função, como vendas, estoque, financeiro ou administração.
  
  O acesso às funcionalidades do sistema deve ser controlado de acordo com o nível de permissão de cada usuário.
  
  Funcionários do setor de vendas, por exemplo, não devem possuir acesso às configurações administrativas ou informações restritas do setor financeiro.
  
- ### Administração do sistema
  Somente o administrador possui permissão para alterar determinadas configurações do sistema.
  
  Usuários comuns não podem modificar configurações administrativas sem autorização.
  
  Alterações relacionadas às configurações do sistema, permissões de usuários e regras internas devem ser realizadas somente por funcionários autorizados
  
- ### Backup
  Os dados do sistema devem possuir backup realizado diariamente, conforme a política interna da empresa.
  
  Os backups devem preservar informações como clientes, produtos, estoque, pedidos, vendas e pagamentos.
  
  Os backups têm como objetivo possibilitar a recuperação dos dados em caso de falhas, perda de informações ou problemas no sistema.
  
- ### Dados dos clientes
  Somente funcionários autorizados podem acessar os dados cadastrais dos clientes.
  
  O acesso às informações dos clientes deve respeitar as permissões definidas pela empresa.
  
  Funcionários que não necessitam dessas informações para realizar suas atividades não devem possuir acesso aos dados cadastrais dos clientes.
  
  As informações dos clientes devem ser utilizadas somente para as atividades relacionadas ao funcionamento da loja.

---

## 5. Dicionário de Dados Conceitual (Preliminar)

### 5.1 Funcionário

| Atributo         | Descrição                                       | Regra de negócio associada                          |
| ---------------- | ----------------------------------------------- | --------------------------------------------------- |
| `id_funcionario` | Identificador único do funcionário              | Deve ser único e obrigatório                        |
| `nome`           | Nome completo do funcionário                    | Obrigatório                                         |
| `cpf`            | CPF utilizado para identificação do funcionário | Obrigatório e não deve ser duplicado                |
| `cargo`          | Função exercida pelo funcionário na empresa     | Define as permissões de acesso ao sistema           |
| `telefone`       | Telefone de contato do funcionário              | Deve ser informado no cadastro                      |
| `email`          | E-mail do funcionário                           | Deve possuir formato válido                         |
| `data_admissao`  | Data em que o funcionário foi contratado        | Obrigatória                                         |
| `status`         | Situação atual do funcionário                   | Deve indicar se o funcionário está ativo ou inativo |

### 5.2 Cliente

| Atributo       | Descrição                                           | Regra de negócio associada                                          |
| -------------- | --------------------------------------------------- | ------------------------------------------------------------------- |
| `id_cliente`   | Identificador único do cliente                      | Deve ser único e obrigatório                                        |
| `nome`         | Nome ou razão social do cliente                     | Obrigatório                                                         |
| `cpf_cnpj`     | Documento de identificação do cliente               | Obrigatório e não deve ser duplicado                                |
| `telefone`     | Telefone de contato do cliente                      | Utilizado para contato e cadastro                                   |
| `email`        | E-mail do cliente                                   | Deve possuir formato válido                                         |
| `endereco`     | Endereço cadastrado do cliente                      | Deve ser informado quando necessário para entrega                   |
| `tipo_cliente` | Identifica se o cliente é pessoa física ou jurídica | Deve permitir diferenciar clientes de acordo com o tipo de cadastro |
| `status`       | Situação do cadastro do cliente                     | Deve indicar se o cadastro está ativo ou inativo                    |

### 5.3 Empresa

| Atributo        | Descrição                             | Regra de negócio associada                      |
| --------------- | ------------------------------------- | ----------------------------------------------- |
| `id_empresa`    | Identificador único da empresa        | Deve ser único e obrigatório                    |
| `razao_social`  | Nome empresarial da empresa           | Obrigatório                                     |
| `cnpj`          | Cadastro Nacional da Pessoa Jurídica  | Obrigatório e não deve ser duplicado            |
| `nome_fantasia` | Nome comercial utilizado pela empresa | Pode ser utilizado para identificação comercial |
| `endereco`      | Endereço da empresa                   | Obrigatório                                     |
| `telefone`      | Telefone comercial da empresa         | Deve ser informado no cadastro                  |
| `email`         | E-mail comercial da empresa           | Deve possuir formato válido                     |

### 5.4 Estoque

| Atributo                | Descrição                                           | Regra de negócio associada                        |
| ----------------------- | --------------------------------------------------- | ------------------------------------------------- |
| `id_estoque`            | Identificador único do registro de estoque          | Deve ser único e obrigatório                      |
| `id_produto`            | Identifica o produto relacionado ao estoque         | Deve corresponder a um produto cadastrado         |
| `quantidade_disponivel` | Quantidade disponível do produto em estoque         | Não pode ser negativa                             |
| `quantidade_minima`     | Quantidade mínima definida para controle do estoque | Deve ser igual ou maior que zero                  |
| `localizacao`           | Local onde o produto está armazenado                | Deve identificar o local de armazenamento         |
| `data_atualizacao`      | Data da última atualização do estoque               | Deve ser atualizada após movimentações de estoque |

### 5.5 Pedido

| Atributo         | Descrição                                             | Regra de negócio associada                                                       |
| ---------------- | ----------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id_pedido`      | Identificador único do pedido                         | Deve ser único e obrigatório                                                     |
| `id_cliente`     | Identifica o cliente responsável pelo pedido          | O pedido deve estar associado a um cliente cadastrado                            |
| `id_funcionario` | Identifica o funcionário responsável pelo atendimento | Deve corresponder a um funcionário autorizado                                    |
| `data_pedido`    | Data em que o pedido foi realizado                    | Obrigatória                                                                      |
| `status`         | Situação atual do pedido                              | Deve representar etapas como pendente, pago, enviado, concluído ou cancelado     |
| `tipo_venda`     | Identifica se o pedido é de atacado ou varejo         | Deve permitir diferenciar as regras comerciais                                   |
| `valor_total`    | Valor total do pedido                                 | Deve ser calculado de acordo com os produtos, quantidades e descontos aplicáveis |
| `data_envio`     | Data em que o pedido foi enviado                      | Deve ser registrada quando o pedido for enviado                                  |

**Regras relacionadas:** pedidos de atacado devem possuir no mínimo 15 peças; pedidos de varejo não possuem quantidade mínima. Um pedido somente pode ser cancelado antes do envio.

### 5.6 Fornecedor

| Atributo        | Descrição                          | Regra de negócio associada                  |
| --------------- | ---------------------------------- | ------------------------------------------- |
| `id_fornecedor` | Identificador único do fornecedor  | Deve ser único e obrigatório                |
| `nome`          | Nome ou razão social do fornecedor | Obrigatório                                 |
| `cnpj`          | CNPJ do fornecedor                 | Obrigatório e não deve ser duplicado        |
| `telefone`      | Telefone de contato do fornecedor  | Deve ser informado no cadastro              |
| `email`         | E-mail do fornecedor               | Deve possuir formato válido                 |
| `endereco`      | Endereço do fornecedor             | Deve ser registrado para controle cadastral |
| `status`        | Situação do fornecedor             | Deve indicar se está ativo ou inativo       |

### 5.7 Produto

| Atributo        | Descrição                                        | Regra de negócio associada                                  |
| --------------- | ------------------------------------------------ | ----------------------------------------------------------- |
| `id_produto`    | Identificador único do produto                   | Deve ser único e obrigatório                                |
| `nome`          | Nome do produto                                  | Obrigatório                                                 |
| `descricao`     | Descrição das características do produto         | Deve permitir identificar o produto                         |
| `categoria`     | Categoria à qual o produto pertence              | Obrigatória                                                 |
| `tamanho`       | Tamanho disponível do produto                    | Deve corresponder aos tamanhos comercializados pela empresa |
| `cor`           | Cor do produto                                   | Deve ser informada no cadastro                              |
| `preco_venda`   | Preço do produto para venda no varejo            | Deve ser maior que zero                                     |
| `preco_atacado` | Preço utilizado nas vendas por atacado           | Deve ser maior que zero e seguir a política comercial       |
| `id_fornecedor` | Identifica o fornecedor responsável pelo produto | Deve corresponder a um fornecedor cadastrado                |
| `status`        | Situação do produto                              | Deve indicar se o produto está ativo ou inativo             |

**Regras relacionadas:** um produto não pode ser vendido quando não houver quantidade disponível em estoque. Produtos inativos não devem ser utilizados em novas vendas.

### 5.8 Pagamento

| Atributo            | Descrição                                    | Regra de negócio associada                                                       |
| ------------------- | -------------------------------------------- | -------------------------------------------------------------------------------- |
| `id_pagamento`      | Identificador único do pagamento             | Deve ser único e obrigatório                                                     |
| `id_pedido`         | Identifica o pedido relacionado ao pagamento | Deve corresponder a um pedido existente                                          |
| `data_pagamento`    | Data em que o pagamento foi realizado        | Obrigatória quando o pagamento for confirmado                                    |
| `forma_pagamento`   | Forma utilizada para realizar o pagamento    | Deve permitir identificar formas como Pix, cartão ou outras aceitas pela empresa |
| `valor`             | Valor pago pelo cliente                      | Deve corresponder ao valor devido após os descontos aplicáveis                   |
| `status`            | Situação do pagamento                        | Deve indicar, por exemplo, pendente, confirmado ou cancelado                     |
| `desconto_aplicado` | Valor do desconto aplicado ao pagamento      | Para pagamentos via Pix, deve aplicar o desconto de 5%                           |

**Regras relacionadas:** a compra somente é efetuada após a confirmação do pagamento. O desconto de 5% é aplicado somente para pagamentos realizados via Pix.

---

### 5.9 Relação entre o Dicionário de Dados e as Regras de Negócio

Os atributos apresentados foram definidos considerando as regras de funcionamento da loja. Dessa forma, o dicionário serve como uma base para a construção do modelo conceitual e das próximas etapas da modelagem do banco de dados.

As principais relações são:

* **Funcionário → Pedido:** identifica o funcionário responsável pelo pedido e permite aplicar as regras de permissão.
* **Cliente → Pedido:** identifica o cliente que realizou o pedido.
* **Pedido → Pagamento:** permite controlar a confirmação do pagamento.
* **Produto → Estoque:** permite controlar a quantidade disponível de cada produto.
* **Fornecedor → Produto:** identifica o fornecedor responsável pelo fornecimento dos produtos.
* **Pedido → Produto:** permite identificar os produtos pertencentes a cada pedido.
* **Empresa → Funcionário:** relaciona os funcionários à empresa.

Os exemplos de valores eventualmente utilizados para representar os atributos devem ser fictícios e servir apenas para ilustrar o funcionamento do sistema, não devendo ser utilizados dados reais de clientes, funcionários ou fornecedores.


---

## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
*(vale 7,5% na dimensão conceitual)*
| Entidade | Atributos | Relaciona-se com | Cardinalidade | Justificativa |
|---|---|---|---|---|
| Empresa |---| Cliente |1:N - Uma empresa atende vários clientes. | |
| Empresa |---| Funcionário | 1:N - Uma empresa emprega vários funcionários | |
| Empresa |---| Fornecedor |  1:N - Uma empresa tem vários fornecedores | |
| Funcionário |---| Cliente | 1:N - Um funcionário atende vários clientes. |  |
| Fornecedor |---| d | |  |
| Produto |---| c | | |
| Estoque |---| d  | | |
| Pedido |---| s | | |
| Pagamento |---| d | |  |



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

A estrutura do modelo foi definida com base nos principais processos que identificamos na Peg Vest Jeans, focando em representar no banco de dados apenas os dados que realmente fazem parte da rotina da empresa. Por isso, modelamos entidades para clientes, funcionários, produtos, estoque e para as operações de venda e pedido, afinal, são esses pontos que sustentam o cadastro, a venda, o controle de estoque, o envio de pedidos, as entregas e as transferências.

Para a definição dos atributos, o foco foi guardar só o que é necessário para cada entidade. No caso de clientes, por exemplo, colocamos dados essenciais como nome, CPF, telefone e endereço; já para produtos, mantivemos as informações de cadastro, preço e quantidade em estoque. Essa divisão é importante para manter o banco organizado e evitar colocar dados de contextos diferentes dentro de uma mesma tabela.

Os relacionamentos e as cardinalidades foram mapeados seguindo o fluxo de trabalho da loja. Um cliente pode fazer várias compras ao longo do tempo, e os funcionários entram registrando e finalizando o atendimento. Os produtos se conectam tanto ao estoque quanto às vendas, o que permite checar a disponibilidade e dar baixa nos itens assim que uma venda é concluída. Com isso, as ligações refletem a lógica do negócio sem criar vínculos desnecessários no esquema.

No fim, a ideia dessa modelagem foi evitar uma complexidade desnecessária, mantendo os dados bem separados pela sua finalidade. O resultado é uma estrutura bem organizada, que reflete os processos atuais da Peg Vest Jeans e serve como uma base sólida para as próximas fases do projeto.

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
