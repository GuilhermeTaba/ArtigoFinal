Filtro de regime e consistência

Trend following segura posição por semanas a meses.
O filtro pode aumentar ou diminuir o holding, então tenho que confirmar no backtest.

Holding maior é bom sinal: menos trocas falsas e menos custo.
Frase: “O filtro de regime aumenta o holding period e melhora a consistência da estratégia.”

Provar com: menor drawdown, Sharpe estável ao longo do tempo e menos trades.'


Guide de trending following:
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5140633 

# Comeco de uma trend 
 (ancoragem) Anchoring Effect: Investors tend to anchor their views on recent historical data, unwilling to quickly change their minds, leading to slow reactions to new information and thus slow
price reactions.// demora pra os pressos subirem

 (efeito disposição) Disposition Effect: Investors tend to sell profitable stocks too early to realize gains; conversely, they are reluctant to cut losses on losing stocks. The consequence is that 
prices do 
// investidores vendem antes deixa o preco baixo

 prices underreact to information -> forma uma rampa 

# Sinal que a gente vai usar pra detectar uma trend

4. Time series momentum factor
For a more in-depth analysis of time series momentum, we focus our attention on a single time series
momentum strategy. Following the convention used in
the cross-sectional momentum literature (and based on
the results from Fig. 1 and Table 2), we focus on the
properties of the 12-month time series momentum strategy with a 1-month holding period (e.g., k¼12 and h¼1),
which we refer to simply as TSMOM.

1. TSMOM signal with a window of 260 trading days and equal weighting;


# Continuacao de uma trend 
## Porque uma trend sobe mais do que deveria 

(Efeito manada) Herding Effect: Also known as the bandwagon effect,when investors’ views differ from the
majority, they tend to doubt and change their views to align with the group. After a price
rise or fall begins, investors will join the trend like a herd

(Viés de confirmação e de representatividade)
Confirmation and Representativeness Bias: After a trend starts, investors use recent price
movements to infer the future, selectively focusing on the direction of recent profits; moreover, once they confirm their views, they will seek various data and information to support
their views, allowing the price trend to continue

# Prejuzos da estrategia 
When the trend is small, the strategy yields negative returns; only when the trend
is significant

# Tipos de riscos 
Convergent risks are those that are understood and can be measured through modeling;// ganha porque converge ao preco real 

Divergent risks are unknown, unpredictable, and cannot be well-measured risks // ganha porque diverge do preco real

# Desafio real 
 
Descobrir quando essa tendencia para

# Escolher acoes 
geometric Brownian motion:

From this model, it is easy to see that (long) trend following strategies favor positive drift
rates in returns (i.e., the larger µ, the better) and dislike volatility (i.e., the smaller σ, the better).
A larger µ and/or a smaller σ indicate a more significant trend5

- WEGE3
tem lookahead
WEGE3: rampa limpa, o caso “ideal” do guia
PRIO3: regimes alternados de alta e de baixa, onde o trend following agregou muito
Ibovespa: zigue-zague, onde o trend following puro falhou

sem lookahead

Top 3 em μ/σ no treino (2010–2018):

RADL3 (Raia Drogasil): 0,668
EQTL3 (Equatorial Energia): 0,645
ABEV3 (Ambev): 0,630

TOP 3 mercado americano 
MCD (McDonald’s): μ/σ 0,927, Sharpe do TSMOM 0,75
AMZN (Amazon): μ/σ 0,846, Sharpe do TSMOM 0,78
QQQ (ETF da Nasdaq): μ/σ 0,826, Sharpe do TSMOM 0,85

maior drift rate

menor volatlidade

# Escolha de periodo 

Os períodos de crise foram mantidos no backtest para testar se o Markov switching reduz as perdas em períodos de volatilidade altíssima e sem direção definida, preservando os ganhos nas crises com tendência persistente.

# Tipos de trending following 

- Trend following de drift (longo prazo) -
olha uma tendencia longa

- Trend following de autocorrelação (curto prazo)

# Fluxo 

Para fins descritivos, o modelo foi estimado com a amostra completa (2010–2026), mostrando que os regimes identificados coincidem com os principais episódios de estresse do mercado brasileiro. A avaliação da estratégia, por sua vez, é feita fora da amostra, com parâmetros estimados até 2018 e probabilidades filtradas, para evitar look-ahead bias.
