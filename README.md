# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

O objetivo deste projeto foi utilizar o SageMaker Canvas da AWS para criar um modelo de machine learning capaz de prever a demanda de estoque, ajudando a otimizar a gestão de inventário e melhorar a eficiência operacional

O dataset escolhido para treinar o modelo de previsão de estoque foi o “dataset-1000-com-preco-variavel-e-renovacao-estoque.csv”

## 🚀 Passo a Passo

### 1. configurações

A coluna "QUANTIDADE_ESTOQUE" foi selecionada como a coluna alvo, pois representa a quantidade de estoque disponível, que é a variável que desejamos prever. A previsão precisa dessa quantidade é crucial para otimizar a gestão de inventário.

A coluna "ID_PRODUTO" foi escolhida para identificar de forma única cada item no conjunto de dados. Isso é essencial para diferenciar os produtos e prever a demanda individualmente para cada um.

A coluna "PRECO" foi selecionada como coluna de agrupamento. Embora seja opcional, agrupar os dados por preço pode ajudar a identificar padrões de demanda baseados em diferentes faixas de preço, aumentando a precisão das previsões.

A coluna "DATA_EVENTO" foi escolhida para representar os carimbos de tempo nos dados.

O horizonte de previsão foi definido para 5 dias. Esta escolha permite um equilíbrio entre curto e médio prazo, oferecendo previsões que podem ser imediatamente úteis para ajustes operacionais rápidos e planejamento de curto prazo.

O calendário de feriados do Brasil foi selecionado porque o projeto está sendo desenvolvido no contexto brasileiro. Incluir os feriados específicos do país ajuda a capturar variações na demanda que ocorrem devido a eventos festivos e feriados nacionais.

O método "Standard Build" foi escolhido para construir o modelo. Esta opção fornece um equilíbrio entre precisão e tempo de construção, permitindo criar um modelo robusto e eficiente sem a necessidade de configurações avançadas. É ideal para casos em que se deseja obter resultados confiáveis de forma rápida e eficiente.

### 2. Resultados da Análise

Avg. wQL: 1.024
O valor de Avg. wQL (Average weighted Quantile Loss) indica a perda média ponderada das previsões quantílicas. Um valor mais baixo é desejável e indica previsões mais precisas.

MAPE: 0.001
O MAPE (Mean Absolute Percentage Error) foi extremamente baixo, indicando que as previsões tiveram uma precisão alta em termos percentuais.

WAPE: 1.038
O WAPE (Weighted Absolute Percentage Error) é semelhante ao MAPE, mas ponderado.

RMSE: 0.576
O RMSE (Root Mean Square Error) foi relativamente baixo, indicando um bom desempenho do modelo na previsão dos valores absolutos do estoque.

MASE: 0.003
O MASE (Mean Absolute Scaled Error) também foi muito baixo, reforçando a eficácia do modelo na previsão de estoque.

A coluna "Holiday_BR" (calendário de feriados no Brasil) não teve impacto significativo na acurácia do modelo. Isso pode indicar que os feriados não influenciam diretamente a demanda de estoque para os produtos analisados.

### 3. Análise das Previsões

A análise dos percentis mostra variações mínimas na demanda esperada, sugerindo uma tendência de estabilidade.

As previsões para os dias subsequentes variam ligeiramente em torno de zero, indicando que a demanda deve permanecer estável, com pequenas flutuações.

### 4. Conclusões

Estabilidade na Demanda

As previsões indicam uma demanda estável, com pequenas variações ao redor de zero, sugerindo que o estoque não precisará de grandes ajustes imediatos.
Impacto dos Feriados

A coluna "Holiday_BR" não impactou significativamente as previsões, o que indica que os feriados não afetam a demanda de forma substancial para este produto específico.
Precisão do Modelo

As métricas de desempenho (como RMSE e MAPE) indicam que o modelo é preciso e confiável para prever a demanda de estoque.

## Insights

Previsões de Demanda Estáveis: As previsões indicam uma demanda estável nos próximos dias, o que pode ser útil para manter níveis de estoque consistentes.

Ferramenta Eficiente: O SageMaker Canvas provou ser uma ferramenta eficiente para criar previsões de demanda precisas, suportando decisões de gestão de estoque baseadas em dados.

