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


### 3.2 Requisitos Não Funcionais
*Características de qualidade (ex.: desempenho, segurança, usabilidade, disponibilidade).*

---
## 4. Regras de Negócio
*(esta seção DIVIDE com a Seção 3 "Requisitos do Sistema" os mesmos 7,5% da dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na documentação. "Regras de negócio" é o termo técnico usado em modelagem de dados para as regras de funcionamento de qualquer organização, com ou sem fins lucrativos)*

- **Regras operacionais:** *condições que a organização impõe (ex.: "um pedido só pode ser fechado se houver estoque disponível", "uma doação só pode ser registrada com identificação do doador", "um ritual só pode ser agendado se o espaço estiver disponível").*
- **Restrições organizacionais:** *limitações que afetam o modelo (ex.: políticas internas, prazos, exigências legais, normas religiosas ou estatutárias) — e por que elas importam.*

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
