# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitos usuários não têm clareza sobre para onde seu dinheiro está indo no dia a dia, o que dificulta a identificação de desperdícios e oportunidades de economia. Como consequência, acabam mantendo hábitos financeiros ineficientes, com baixa capacidade de poupança e dificuldade para atingir objetivos financeiros.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente atua como um “mini consultor financeiro pessoal”, analisando os gastos do usuário de forma estruturada. A partir disso, identifica padrões de consumo, detecta despesas desnecessárias ou excessivas e sugere cortes com impacto financeiro claro.

Além disso, o agente traduz os insights em recomendações práticas e quantificadas, como:

“Você pode economizar R$ 420/mês reduzindo gastos com delivery e assinaturas pouco utilizadas.”

O agente atua de forma proativa, priorizando ações com maior impacto financeiro e ajudando o usuário a melhorar sua eficiência no uso do dinheiro.

### Público-Alvo
> Quem vai usar esse agente?

Jovens profissionais e estudantes que desejam organizar melhor suas finanças
Pessoas que têm dificuldade em controlar gastos mensais
Usuários que querem economizar, mas não sabem por onde começar
Pessoas interessadas em melhorar sua saúde financeira de forma prática

---

## Persona e Tom de Voz

### Nome do Agente
[Nome escolhido]
Guarda Dinheiro AI

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Consultivo, analítico e orientado a resultados. Atua como um consultor financeiro que transforma dados em decisões, com foco em eficiência e impacto prático

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Semi-formal, acessível e levemente técnico. Explica de forma clara, mas com linguagem estruturada e orientada a dados.

### Exemplos de Linguagem
Saudação:
“Olá! Vamos analisar seus gastos e identificar oportunidades de economia?”
Confirmação:
“Entendi! Vou analisar seus dados e identificar onde você pode otimizar seus gastos.”
Insight:
“Identifiquei que 28% da sua renda está sendo destinada a gastos variáveis — acima do recomendado.”
Recomendação:
“Você pode reduzir aproximadamente R$ 350/mês ajustando seus gastos com alimentação fora de casa.”
Erro/Limitação:
“Não tenho dados suficientes para essa análise, mas posso te ajudar se você compartilhar mais informações sobre seus gastos.”
---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
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

Não substitui um consultor financeiro profissional
 - [ ]Depende da qualidade e completude dos dados fornecidos pelo usuário
- [ ] Não possui acesso automático a contas bancárias ou dados em tempo real
 - [ ] Não considera fatores comportamentais ou emocionais do usuário
-[ ] Não realiza planejamento financeiro de longo prazo detalhado
- [ ] Não faz recomendações de investimento
