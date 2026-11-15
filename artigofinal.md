# 1. Introducao

Este artigo apresenta o desenvolvimento de uma estratégia de trend following com sinal do fator time series momentum (MOSKOWITZ; OOI; PEDERSEN, 2012). Estratégias de momentum apresentam retornos médios positivos em diversos mercados e classes de ativos. No entanto, seus retornos são pontuados por perdas severas e concentradas em períodos de alta volatilidade (DANIEL; MOSKOWITZ, 2016). Tendo isso em vista, este trabalho utiliza um modelo de mudança de regime markoviano por meio do filtro de Hamilton (HAMILTON, 1989), para identificar períodos de alta volatilidade, de modo que a estratégia assuma posição apenas quando houver tendência clara e baixa volatilidade. 

O período de 2010 a 2018 é utilizado para a estimação do modelo e para a seleção dos ativos, e o período de 2019 a 2025 é reservado para a avaliação fora da amostra. A partir de um universo composto pelas maiores empresas listadas na B3 no início de 2010, foram selecionadas LREN3, ABEV3 e RENT3, por apresentarem a maior razão entre drift e volatilidade no período de estimação, característica favorável à identificação de tendências (SHI; LIAN, 2025).

# 2. Metodologia

## A - Ferramentas utilizadas
