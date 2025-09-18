# Dinâmica: Design Estratégico do Projeto

## Objetivo
Identificar os subdomínios do projeto, classificá-los (Core, Supporting, Generic) e desenhar os bounded contexts, incluindo suas interações. Esse exercício ajudará a criar uma visão clara e estratégica do domínio.

---

## 1. Nome do Projeto
AgroTrace

---

## 2. Objetivo Principal do Projeto
Garantir a rastreabilidade de ponta a ponta de commodities agrícolas (soja, café, etc.), utilizando dados da cadeia de suprimentos para certificar a origem do produto e facilitar o acesso a crédito verde (green finance) para produtores rurais sustentáveis.

---

## 3. Identificação dos Subdomínios
Liste os subdomínios do sistema e classifique-os como **Core Domain**, **Supporting Subdomain** ou **Generic Subdomain**.

| **Subdomínio**                              | **Descrição**                                                                                        | **Tipo**         |
|---------------------------------------------|------------------------------------------------------------------------------------------------------|------------------|
| Certificação de sustentabilidade            | Avaliar eventos das cadeias de suprimento de um produtor e emissão de selo de sustentabilidade       | Core Domain      |
| Gestão de Produtores                        | Cadastro, verificação e manutenção do histórico de produtores que buscam certificação para crédito verde                                                                                                                                                | Core Domain      |
| Rastreabilidade de commodities              | Manter registros de eventos na cadeia de suprimentos dos produtores                                  | Supporting       |
| Acesso ao crédito                           | Integrar produtores certificados com Fornecedores de Crédito.                                        | Supporting       |
| Integração com Bureaus de crédito           | Consulta scores e análises de crédito de Bureaus                                                     | Generic          |
| Integração com Dados Governamentais         | Consulta Informações e certificações de orgãos do governo (IBAMA, Secr. Fazenda, Justiça)            | Generic          |

---

## 4. Desenho dos Bounded Contexts
Liste e descreva os bounded contexts identificados no projeto. Explique a responsabilidade de cada um.

| **Bounded Context**           | **Responsabilidade**                                                                                | **Subdomínios Relacionados** |
|-------------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------|
| Contexto de Produtores        | Gerenciar o cadastro e histórico de produtores rurais                                               | Gestão de Produtores         |
| Contexto de Rastreabilidade   | Processa e controla registro de movimentação de commodities ao longo da cadeia de suprimentos       | Rastreabilidade de commodities                  |
| Contexto de Certificação      | Avalia histórico do produtor e de sua cadeia de suprimento para emitir certificados                 | Certificação de sustentabilidade, Gestão de Produtores, Integração com Dados Governamentais     |
| Contexto de Acesso a crédito verde   | Para produtores certificados, avalia dados de crédito e integra com fornecedores de crédito       | Certificação de sustentabilidade, Acesso ao crédito, Integração com Bureaus de crédito          |

---

## 5. Comunicação entre os Bounded Contexts
Explique como os bounded contexts vão se comunicar. Use os padrões de comunicação, como:
- **Mensageria/Eventos (desacoplado):** Ex.: O Contexto de Consultas emite um evento "Consulta Finalizada", consumido pelo Contexto de Pagamentos.
- **APIs (síncrono):** Ex.: O Contexto de Pagamentos consulta informações de preços no Contexto de Consultas.

| **De (Origem)**              | **Para (Destino)**          | **Forma de Comunicação**    | **Exemplo de Evento/Chamada**                             |
|------------------------------|-----------------------------|-----------------------------|-----------------------------------------------------------|
| Contexto de Produtores       | Contexto de Rastreabilidade | Mensageria (Evento)         | "Produtor cadastrado"                                     |
| Contexto de Rastreabilidade  | Contexto de Certficação     | API                         | Obter informações de rastreabilidade pelo ID do produtor  |

---

## 6. Definição da Linguagem Ubíqua
Liste os termos principais da Linguagem Ubíqua do projeto. Explique brevemente cada termo.

| **Termo**                    | **Descrição**                                                                                   |
|------------------------------|-----------------------------------------------------------------------------------------------|
| Ex.: Consulta                | Sessão médica entre paciente e médico.                                                       |
| Ex.: Paciente                | Usuário que agenda e realiza consultas.                                                      |
| Ex.: Receita                 | Prescrição médica gerada durante a consulta.                                                 |

---

## 7. Estratégia de Desenvolvimento
Para cada tipo de subdomínio, explique a abordagem para implementação:
- **Core Domain:** Desenvolver internamente com foco total.
- **Supporting Subdomain:** Desenvolver internamente ou parcialmente terceirizar.
- **Generic Subdomain:** Usar ferramentas ou serviços de mercado.

| **Subdomínio**              | **Estratégia**                         | **Ferramentas ou Serviços (se aplicável)** |
|-----------------------------|---------------------------------------|-------------------------------------------|
| Gestão de Consultas         | Desenvolvimento interno               |                                           |
| Cadastro de Usuários        | Interno com uso de Auth0 para login   | Auth0                                     |
| Pagamentos                  | Terceirizar usando API Stripe         | Stripe                                    |

---

## 8. Diagrama Visual (Opcional, mas Recomendado)
Desenhe um diagrama que mostre:
- Os bounded contexts.
- Como eles se comunicam.
- A relação com os subdomínios.

Use ferramentas como **Miro**, **Lucidchart** ou mesmo papel e caneta para criar seu diagrama e adicionar ao projeto.

---

## Dicas para Apresentação
- Explique cada parte do design, focando no **Core Domain** (o coração do negócio).
- Justifique por que certos subdomínios foram classificados como Supporting ou Generic.
- Destaque como a comunicação entre bounded contexts foi pensada para ser escalável.

---

Boa sorte com a dinâmica! 🚀
