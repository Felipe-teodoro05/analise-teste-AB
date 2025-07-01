# 📊 Análise de Teste A/B para Otimização de Funil de Marketing

**Status do Projeto:** [ 🚧 Em Andamento ]

## 1. Contexto e Problema de Negócio

Este projeto analisa os resultados de um teste A/B conduzido por uma empresa de e-commerce para avaliar a eficácia de duas campanhas de marketing (`control` vs. `test`). O objetivo é determinar, com um nível de confiança estatística de 95%, se a nova campanha (`test group`) gera uma taxa de conversão de compra superior e se é mais eficiente em outras etapas do funil de marketing.

A análise fornecerá uma base de dados sólida para a tomada de decisão sobre qual campanha alocar mais recursos no futuro.

## 2. Dataset

Os dados foram divididos em dois arquivos `.csv` (`control_group.csv` e `test_group.csv`), obtidos na plataforma Kaggle. Cada arquivo contém métricas diárias de performance da campanha correspondente.

**Principais colunas:**
* `Campaign Name`: Nome da campanha (Controle ou Teste).
* `Date`: Data da observação.
* `Spend [USD]`: Gasto com a campanha no dia.
* `# of Impressions`: Número de vezes que o anúncio foi exibido.
* `Reach`: Número de pessoas únicas alcançadas.
* `# of Website Clicks`: Número de cliques no site.
* `# of Searches`: Número de buscas realizadas no site.
* `# of View Content`: Número de visualizações de conteúdo/produto.
* `# of Add to Cart`: Número de adições ao carrinho.
* `# of Purchase`: Número de compras finalizadas.

## 3. Metodologia de Análise

### Preparação dos Dados
1.  Os dois arquivos CSV serão carregados em DataFrames separados.
2.  Uma coluna `group` será adicionada a cada DataFrame para identificar a origem (`control` ou `test`).
3.  Os DataFrames serão concatenados em um único conjunto de dados mestre.
4.  Novas métricas de funil serão calculadas, como Taxa de Clique (CTR), Taxa de Adição ao Carrinho e a Taxa de Conversão de Compra.

### Análise Estatística
A análise será conduzida em duas frentes para demonstrar e comparar diferentes ferramentas:

1.  **Análise no Microsoft Excel:** Utilização de tabelas dinâmicas e fórmulas para uma análise exploratória rápida.
2.  **Análise em Python:** Uso das bibliotecas `Pandas` para manipulação, `Matplotlib`/`Seaborn` para visualização e `Statsmodels`/`SciPy` para os testes de hipótese.

O método estatístico central será o **Teste Z para duas proporções** aplicado à **Taxa de Conversão de Compra** (Compras / Cliques no Site) para validar a hipótese principal. Análises secundárias serão feitas em outras métricas do funil.

## 4. Formulação das Hipóteses

Para a métrica principal (Taxa de Conversão de Compra), definimos as seguintes hipóteses:

> **Hipótese Nula ($H_0$):** Não há diferença estatisticamente significativa entre as taxas de conversão de compra das duas campanhas.
>
> $$ H_0: P_{test} - P_{control} = 0 $$

> **Hipótese Alternativa ($H_1$):** Existe uma diferença estatisticamente significativa entre as taxas de conversão de compra.
>
> $$ H_1: P_{test} - P_{control} \neq 0 $$

## 5. Resultados e Achados

*[Esta seção será preenchida após a conclusão da análise.]*

## 6. Conclusão e Recomendação de Negócio

*[Esta seção será preenchida com a conclusão final e a recomendação de negócio.]*

## 7. Tecnologias Utilizadas

* **Linguagem:** `Python`
* **Bibliotecas:** `Pandas`, `NumPy`, `Matplotlib`, `Seaborn`, `Statsmodels`
* **Ferramentas:** `Jupyter Notebook`, `Microsoft Excel`, `Git`, `GitHub`