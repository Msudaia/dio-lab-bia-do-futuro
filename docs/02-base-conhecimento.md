# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | CAnalisar padrão de gastos do usuário por categoria (alimentação, transporte, lazer, etc.) |
| `perfil_investidor.json` | JSON | Identificar capacidade financeira e calcular comprometimento de renda |
| `produtos_financeiros.json` | JSON | Padronizar e classificar os tipos de despesas |
| `transacoes.csv` | CSV | Comparar gastos do usuário com boas práticas (ex: % ideal por categoria) |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados foram estruturados para permitir análises mais eficientes, incluindo:

Padronização das categorias de gastos (ex: "iFood" → "Alimentação fora de casa")
Criação de agrupamentos entre gastos fixos e variáveis
Inclusão de benchmarks financeiros (ex: limite recomendado de 30% da renda para gastos variáveis)
Organização temporal das transações para análise mensal

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos CSV e JSON são carregados no início da execução do agente e estruturados em memória. Esses dados são organizados em variáveis que permitem rápida consulta durante a interação com o usuário.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados são inseridos dinamicamente no prompt do modelo, conforme a necessidade da análise.

Informações principais (renda, resumo de gastos) entram no contexto principal
Transações detalhadas são resumidas para evitar excesso de informação
Benchmarks são utilizados como referência para gerar recomendações

O agente utiliza esses dados para gerar respostas baseadas em análise real, evitando respostas genéricas.
---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

Dados do Usuário:
- Renda mensal: R$ 3.500
- Total de gastos: R$ 3.200
- Percentual comprometido: 91%

Distribuição de gastos:
- Alimentação: R$ 1.000 (29%)
- Moradia: R$ 1.200 (34%)
- Transporte: R$ 400 (11%)
- Lazer: R$ 600 (17%)

Benchmarks:
- Alimentação recomendada: até 20% da renda
- Lazer recomendado: até 10% da renda

Principais insights:
- Gastos com alimentação e lazer acima do recomendado
- Baixa margem para poupança

Objetivo do agente:
- Identificar oportunidades de redução de gastos
- Sugerir economia mensal com impacto estimado
