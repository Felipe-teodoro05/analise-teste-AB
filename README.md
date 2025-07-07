# Análise de Teste A/B para Otimização de Funil de Marketing

**Status do Projeto:** [Concluído]

## 1. Contexto e Problema de Negócio

Este projeto analisa os resultados de um teste A/B conduzido por uma empresa de e-commerce para avaliar a eficácia de duas campanhas de marketing (`control` vs. `test`). O objetivo é determinar, com um nível de confiança estatística de 95%, se a nova campanha (`test group`) gera uma taxa de conversão de compra superior e se é mais eficiente em outras etapas do funil de marketing. A análise investiga a fundo o funil de conversão para entender não apenas qual campanha gera mais vendas, mas onde no processo cada uma se destaca, avaliando o trade-off entre a capacidade de atração de cliques e a eficiência na conversão final

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
4.  Novas métricas de funil e de eficiência financeira foram calculadas, como Taxa de Clique (CTR), Taxa de Adição ao Carrinho, Taxa de Conversão de Compra e o Custo por Aquisição (CPA)

### Análise Estatística
A análise será conduzida em duas frentes para demonstrar e comparar diferentes ferramentas:

1.  **Análise no Microsoft Excel:** Utilização de tabelas dinâmicas e fórmulas para uma análise exploratória rápida.
2.  **Análise em Python:** Uso das bibliotecas `Pandas` para manipulação, `Matplotlib`/`Seaborn` para visualização e `Statsmodels`/`SciPy` para os testes de hipótese.

O método estatístico central será o **Teste Z para duas proporções** aplicado à **Taxa de Conversão de Compra** (Compras / Cliques no Site) para validar a hipótese principal. Análises secundárias foram feitas em outras métricas do funil, e a análise de Custo por Aquisição (CPA) foi incluída para fornecer uma visão financeira completa da performance.

## 4. Formulação das Hipóteses

Para a métrica principal (Taxa de Conversão de Compra), definimos as seguintes hipóteses:

> **Hipótese Nula ($H_0$):** Não há diferença estatisticamente significativa entre as taxas de conversão de compra das duas campanhas.
>
> $$ H_0: P_{test} - P_{control} = 0 $$

> **Hipótese Alternativa ($H_1$):** Existe uma diferença estatisticamente significativa entre as taxas de conversão de compra.
>
> $$ H_1: P_{test} - P_{control} \neq 0 $$

## 5. Resultados e Achados

A análise revelou um claro trade-off de performance entre as duas campanhas:

- **Atração de Cliques (Topo de Funil)**: A campanha de Teste demonstrou uma performance esmagadoramente superior na geração de cliques, com uma Taxa de Clique (CTR) de 10.24%, significativamente maior que os 5.09% da campanha de Controle.

- **Conversão em Vendas (Fundo de Funil)**: Por outro lado, a campanha de Controle foi estatisticamente mais eficaz em converter esses cliques em compras. A taxa de conversão de compra do grupo de Controle foi de 0.995%, superando os 0.795% do grupo de Teste. Essa diferença foi validada com um Teste Z, resultando em um p-valor < 0.001.

- **Eficiência Financeira**: A superioridade da campanha de Controle também se refletiu nos custos. O Custo por Aquisição (CPA) do grupo de Controle (US$ 4,41) foi aproximadamente 10% menor que o do grupo de Teste (US$ 4,92).

## 6. Conclusão e Recomendação de Negócio

A recomendação é a criação de uma campanha híbrida que combine os pontos fortes de ambas:

1. Utilizar o criativo do anúncio da Campanha de Teste para maximizar a Taxa de Clique (CTR) e atrair um maior volume de visitantes para o site.

2. Direcionar este tráfego para a página de produto e funil de checkout da Campanha de Controle, que comprovadamente converte visitantes em clientes de forma mais eficaz e a um custo menor.

Esta abordagem híbrida tem o potencial de otimizar o retorno sobre o investimento (ROI) ao capitalizar sobre a melhor performance de cada campanha em sua respectiva etapa do funil de marketing.

## 7. Tecnologias Utilizadas

* **Linguagem:** `Python`
* **Bibliotecas:** `Pandas`, `NumPy`, `Matplotlib`, `Seaborn`, `Statsmodels`
* **Ferramentas:** `Jupyter Notebook`, `Microsoft Excel`, `Git`, `GitHub`
* **Reprodutibilidade:** `requirements.txt` (para recriação do ambiente Python).
