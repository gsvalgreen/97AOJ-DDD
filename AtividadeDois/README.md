# 📚 Design Estratégico do Projeto

## 📌 Aula 1: Introdução ao Domain-Driven Design (DDD)

### **1️⃣ Revisão da Aula**

- O que é **Domain-Driven Design (DDD)**?
- Diferença entre **Complexidade Essencial vs. Complexidade Acidental**.
- **Subdomínios**: Core Domain, Supporting Subdomains e Generic Subdomains.
- **Bounded Contexts**: Separando conceitos e linguagens dentro do domínio.

### **2️⃣ Identificação dos Subdomínios**

| **Subdomínio**                      | **Descrição**                                                                                            | **Tipo**    |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|-------------|
| Certificação de sustentabilidade    | Avaliar movimentações das cadeias de suprimento de um produtor e emissão de selo de sustentabilidade     | Core Domain |
| Gestão de Produtores                | Cadastro, verificação e manutenção do histórico de produtores que buscam certificação para crédito verde | Core Domain |
| Rastreabilidade de commodities      | Manter registros de movimentações na cadeia de suprimentos dos produtores                                | Supporting  |
| Acesso ao crédito                   | Integrar produtores certificados com Fornecedores de Crédito.                                            | Supporting  |
| Integração com Bureaus de crédito   | Consulta scores e análises de crédito de Bureaus                                                         | Generic     |
| Integração com Dados Governamentais | Consulta Informações e certificações de órgãos do governo (IBAMA, Secr. Fazenda, Justiça)                | Generic     |

---

## 📌 Aula 2: Mapeamento de Contextos (Context Mapping)

### **1️⃣ Objetivo da Aula**

Nesta aula, vamos:
✅ Explorar como **Bounded Contexts** se relacionam entre si.  
✅ Aplicar **Context Mapping** para visualizar dependências entre contextos.  
✅ Criar um **diagrama de Context Mapping** para um projeto.

---

### **2️⃣ Atividade Prática: Context Mapping no Projeto**

📌 **Objetivo:**  
Identifique os **Bounded Contexts** do projeto e criar um **Context Map**, definindo as relações entre eles.

📌 **Instruções:**  
1️⃣ **Escolha um projeto** (real ou fictício). Ou utilize o seu projeto da aula 1. Pode ser um e-commerce, um sistema de
saúde, um banco digital.
2️⃣ **Liste os Bounded Contexts** que fazem parte do sistema.  
3️⃣ **Defina os relacionamentos** entre os contextos usando os padrões do Context Mapping (**Customer-Supplier, Shared
Kernel, Anticorruption Layer, etc.**).  
4️⃣ **Crie um diagrama** representando o Context Map.  
5️⃣ **Justifique suas escolhas** (por que cada relacionamento foi modelado dessa forma?).

📌 **Relacionamento entre os contextos**

| **Origem**                  | **Destino**                        | **Tipo de Relacionamento**     | **Explicação**                                                                                                                                                                                       |
|-----------------------------|------------------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Contexto de Produtores      | Contexto de Rastreabilidade        | **Customer-Supplier**          | A rastreabilidade depende de ter um produtor cadastrado.                                                                                                                                             |
| Contexto de Rastreabilidade | Contexto de Certificação           | **Anticorruption Layer (ACL)** | Para certificar um produtor, é preciso monitorar os diversos tipos de movimentações rastreadas, o contexto de certificação traduz as movimentações para uma estrutura comum de dados a ser validada. |
| Contexto de Certificação    | Contexto de Acesso a crédito verde | **Shared Kernel**              | A liberação de acesso a crédito verde só acontece enquanto a certificação está válida                                                                                                                |

📌 **Formato de Entrega:**

- O trabalho pode ser entregue em **Markdown (.md), PDF ou apresentação (PPT)**.
- O diagrama pode ser anexado como **imagem** ou **link para uma ferramenta online**.
- Entrega via **repositório Git** ou outra plataforma definida pelo professor.

📌 **Ferramentas para Criar o Diagrama:**

- [Miro](https://miro.com/)
- [Lucidchart](https://www.lucidchart.com/)
- [Figma](https://www.figma.com/)

📌 **Context Map:**

![Context Map](./utils/context_map.png)

## 📌 Aula 3: Próximos Passos

Na próxima aula, vamos explorar **Design Tático**, abordando:  
🔹 **Entidades vs. Value Objects** – Como diferenciar e modelar corretamente.  
🔹 **Agregados** – Como definir o agregado raiz e garantir consistência.  
🔹 **Repositórios** – Como separar persistência da lógica de domínio.

📌 **Prepare-se!** Tente aplicar **Context Mapping** no seu projeto antes da próxima aula.

---

**📢 Bom trabalho! Nos vemos na próxima aula! 🚀**
