# 📌 Roteiro para a Atividade de Event Storming

## **1️⃣ Preparação (5-10 min)**
    - Gestão do produtor
---

## **2️⃣ Mapeamento de Eventos de Domínio (15-20 min)**
    - Perfil criado
    - Documentação enviada
    - Documentação validada
    - Perfil aprovado

---

## **3️⃣ Identificação de Comandos e Atores (10-15 min)**
```
Comando: "Criar o perfil"
Ator: Produtor
vento gerado: "Perfil criado"
```

```
Comando: "Enviar a documentação"
Ator: Produtor
Evento gerado: "Documentação enviada"
```
```
Comando: "Validar a documentação"
Ator: Validador
Evento gerado: "Documentação validada"
```

```
Comando: "Avaliar o perfil"
Ator: Analista
Evento gerado: "Perfil aprovado"
```

---

## **4️⃣ Descobrindo Regras e Políticas de Negócio (10-15 min)**
- Pergunta-chave: **"Quais regras precisam ser seguidas nesse processo?"**
- Identificar **políticas** (regras automáticas ou manuais).
    - **Exemplo:**
        - **Se o pagamento não for aprovado em 24h, cancelar pedido.**
- Mapear **integrações externas** (ex: APIs, sistemas de terceiros).

---

## **5️⃣ Identificação dos Bounded Contexts (10 min)**
- Pergunta-chave: **"Quem é responsável por cada parte do processo?"**
- Separar os eventos e comandos em **diferentes áreas do sistema**.
    - **Exemplo:**
        - **Contexto de Pedidos** (Criação e status dos pedidos)
        - **Contexto de Pagamento** (Autorização financeira)
        - **Contexto de Logística** (Entrega e rastreamento)

---

## **6️⃣ Discussão e Refinamento (15 min)**
- Cada grupo apresenta seu fluxo.
- **Perguntas para discussão:**
    - Há eventos que poderiam ser melhor detalhados?
    - Existem regras de negócio não mapeadas?
    - Algum comando ou evento depende de um sistema externo?
- Refinar o modelo conforme necessário.

---

## **🎯 Dicas para Facilitar a Atividade**
✅ **Eventos são sempre no passado** e os comandos no presente.  
✅ **O foco é explorar e aprender**, não a perfeição.  
✅ **Usar cores diferentes para cada tipo de post-it** (como na legenda da imagem de Event Storming).  
✅ **Pensar no fluxo real do dia a dia do trabalho** para tornar a atividade mais prática.

---
## Links Úteis:

✅ https://medium.com/@jonesroberto/event-storming-guia-b%C3%A1sico-216498f5dd2d

✅ https://www.linkedin.com/pulse/o-que-%C3%A9-eventstorming-e-como-este-formato-de-workshop-rodrigues/