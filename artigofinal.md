# 1. Introducao

Este artigo apresenta o desenvolvimento de uma estratégia de trend following com sinal do fator time series momentum (MOSKOWITZ; OOI; PEDERSEN, 2012). Estratégias de momentum apresentam retornos médios positivos em diversos mercados e classes de ativos. No entanto, seus retornos são pontuados por perdas severas e concentradas em períodos de alta volatilidade (DANIEL; MOSKOWITZ, 2016). Tendo isso em vista, este trabalho utiliza um modelo de mudança de regime markoviano por meio do filtro de Hamilton (HAMILTON, 1989), para identificar períodos de alta volatilidade, de modo que a estratégia assuma posição apenas quando houver tendência clara e baixa volatilidade. 

A estratégia é aplicada a dois mercados, o brasileiro e o norte-americano, o que permite verificar se os resultados se mantêm em contextos com níveis distintos de juros, liquidez e volatilidade. Em ambos, o período de julho de 2001 a junho de 2021 é utilizado para a estimação do modelo e para a seleção dos ativos, e o período de julho de 2021 a junho de 2026 é reservado para a avaliação fora da amostra. No Brasil, a partir de um universo composto por grandes empresas listadas na B3, foram selecionadas ABEV3, VALE3 e ITUB4; nos Estados Unidos, a partir de um universo de grandes empresas americanas com histórico desde 2001, foram selecionadas AAPL, NKE e AMZN. Em cada mercado, os três ativos escolhidos são os que apresentam a maior razão entre drift e volatilidade no período de estimação, característica favorável à identificação de tendências (SHI; LIAN, 2025).

# 2. Metodologia

## A - Ferramentas utilizadas
