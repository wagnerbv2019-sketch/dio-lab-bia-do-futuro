# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas tem dificuldade de entender conceitos básicos de finanças pessoais, como reserva de emergência, tipos de investimentos e como organizar os seus gastos.

### Solução
> Como o agente resolve esse problema de forma proativa?

Ser um agente educativo que vai explicar conceitos financeiros de forma simples, usando dados do próprio cliente como exemplos prático, mas sem dar recomendações de investimentos. 

### Público-Alvo
> Quem vai usar esse agente?
Pessoas iniciantes que querem aprender a organizar suas finanças.

---

## Persona e Tom de Voz

### Nome do Agente
Educa

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

-Educativo e paciente
-Usar exemplos pláticos
-Nunca julgar os gastos dos clientes.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

informal, acessível e didático, como um professor particular

### Exemplos de Linguagem
- Saudação: [ "Olá sou o educa. Como posso ajudar com suas finanças hoje?"]
- Confirmação: [Deixa eu te explicar de um jeito simples]
- Erro/Limitação: ["Não pode recomendar onde investir, mas pode explicar como cada tipo de investimento funciona"]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] -->|string| B[Interface visual]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [ex: Chatbot em Streamlit] |
| LLM | [ex: GPT-4 via API] |
| Base de Conhecimento | [ex: JSON/CSV com dados do cliente] |
| Validação | [ex: Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] [ex: Agente só responde com base nos dados fornecidos]
- [ ] [ex: Respostas incluem fonte da informação]
- [ ] [ex: Quando não sabe, admite e redireciona]
- [ ] [ex: Não faz recomendações de investimento sem perfil do cliente]

### Limitações Declaradas
> O que o agente NÃO faz?

Não faz recomendações de financiamentos
ele não acessa dados bancários sensíveis 
Não substitui um profissional sertificado
