# Divergências entre o código e as referências

Comparação entre `artigofinal_brasil.ipynb` / `artigofinal_eua.ipynb` e as referências 1–5 de `bibliografia.md`.

## O que está de acordo

- **Hamilton (1989), filtro – seção 4.2:** os passos 1–4 do `hamilton_filter` (previsão do regime, densidade conjunta, verossimilhança e Bayes) são os mesmos do artigo. A notação p = P(sₜ=1 | sₜ₋₁=1), q = P(sₜ=0 | sₜ₋₁=0), a representação AR(1) sₜ = (1−q) + λsₜ₋₁ + vₜ com λ = p+q−1 (eq. 2.3–2.4), a inicialização pela probabilidade incondicional (1−q)/(2−p−q) e a log-verossimilhança como subproduto do filtro, maximizada numericamente, seguem o artigo.
- **Ang e Timmermann (2012), regimes – p. 13:** "regimes are mostly identified by volatility". Isso sustenta dois regimes separados pela volatilidade. Hamilton (p. 369) também afirma que o filtro vale com σ dependente do regime.
- **Shi e Lian (2025), seleção – p. 6:** a escolha das ações por μ/σ segue o guia (drift alto e volatilidade baixa favorecem o trend following). A janela de 252 dias do sinal é próxima dos "260 trading days, equal weighting" (p. 26).
- **Daniel e Moskowitz (2016), motivação:** os crashes de momentum ocorrem em "panic states" (volatilidade alta, repique do mercado). Isso justifica sair da posição no regime de alta volatilidade.

## Divergências

| # | Referência | O que a referência faz | O que o código faz | Gravidade | Situação |
|---|---|---|---|---|---|
| 1 | Moskowitz, Ooi e Pedersen (2012) | Sinal = sinal do retorno **em excesso** à taxa livre de risco nos últimos 12 meses | Usava o sinal do retorno **bruto** | Alta no Brasil (com CDI de 10–13 % a.a., uma ação que sobe menos que o CDI tem excesso negativo) | ✅ **Corrigido**: `mom = sign(ret_acao − ret_rf)` em 252 dias, com o CDI (Brasil) ou a T-Bill (EUA) |
| 2 | Moskowitz, Ooi e Pedersen (2012) | Posição dimensionada para 40 % de vol anual (40 %/σ, com σ por EWMA) | Peso fixo de 1/3 por ação na entrada, sem ajuste pela vol | Média | Declarar como simplificação no texto |
| 3 | Moskowitz, Ooi e Pedersen (2012) | Holding de 1 mês (k=12, h=1), rebalanceamento mensal | Confere o sinal todo dia e opera quando ele muda; sem rebalanceamento | Média | Declarar no texto (gera mais trades que o TSMOM original) |
| 4 | Hamilton (1989) | **Média** muda com o regime, inovações normais, AR(4) | Média única, **variância** muda com o regime, t de Student, sem AR | Média | Apresentar como extensão: variante de volatilidade (Ang e Timmermann; Hamilton, p. 369); t de Student pelas caudas grossas (Ang e Timmermann, p. 2). Nenhuma das 5 referências usa a t de Student. |
| 5 | Ang e Timmermann (2012) / `ideias.md` | O padrão é a média **e** a volatilidade mudarem ("regime turbulento: vol alta, drift negativo ou nulo") | Só a volatilidade muda | Baixa | Justificar: Ang e Timmermann mostram que a diferença nas médias é pequena; ajustar o `ideias.md` |
| 6 | Shi e Lian (2025), p. 6 | "For strategies that can short, we pay more attention to the absolute value of the Sharpe ratio" | Ranking por μ/σ com sinal, mas as estratégias vendem a descoberto | Baixa | Justificar ("seleção pelo lado comprado") ou usar \|μ/σ\| |
| 7 | Daniel e Moskowitz (2016) | Momentum **cross-sectional** (winners − losers); estado de pânico definido pelo **mercado** (bear market + vol do mercado); peso dinâmico contínuo (∝ média/variância) | TSMOM por ação; regime pela vol da **própria ação**; filtro liga/desliga | Baixa | Usar como motivação, não como método replicado |

## Texto desatualizado

- `artigofinal.md` ainda cita treino 2010–2018, teste 2019–2025 e as ações LREN3, ABEV3 e RENT3. O código atual usa treino jul/2001–jun/2021, teste jul/2021–jun/2026 e ações definidas pelo ranking.
- `ideias.md` descreve regimes por média e volatilidade, mas o modelo implementado muda só a volatilidade (item 5).
