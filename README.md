# Análise Exploratória — ENEM 2019

Projeto de análise de dados desenvolvido como trabalho acadêmico, investigando padrões de desempenho dos participantes do ENEM 2019 com foco no impacto do acesso à internet no desempenho de estudantes de baixa renda.

---

## Hipótese Testada

**H0:** O acesso à internet não influencia as notas de estudantes de baixa renda.

**H1:** Estudantes de baixa renda com acesso à internet têm notas maiores do que estudantes de baixa renda sem acesso à internet.

---

## Dataset

- **Baixe os microdados do ENEM 2019 em:** https://www.kaggle.com/datasets/lauroliveira/enem-2019-dados-tratados
- **Total de registros:** ~3.7 milhões de participantes com nota válida
- **Variáveis principais:** notas por área, renda familiar, acesso à internet, tipo de escola, sexo, idade

---

## Metodologia

### Análise Exploratória
- Distribuição das notas por sexo e tipo de escola
- Identificação de outliers via IQR
- Comparação entre boxplots e histogramas

### Teste de Hipótese
- **Teste:** Mann-Whitney U (unicaudal)
- **Justificativa:** robusto para distribuições não normais e grandes amostras
- **Notas testadas:** Redação e Matemática
- **Definição de baixa renda:** testada em 3 critérios de corte (< R$1.000, < R$1.500 e < R$2.500)

### Bônus — Correlação
- Comparação entre Pearson e Spearman via heatmap
- Variáveis: notas, renda, idade e pessoas na residência

---

## Resultados

### Teste de Hipótese — H0 rejeitada (p ≈ 0.000)

| | Com Internet | Sem Internet | Diferença |
|---|---|---|---|
| Redação (média) | 540 | 500 | +40 pontos |
| Matemática (média) | 493 | 469 | +24 pontos |

Resultado consistente nos 3 critérios de corte de baixa renda testados.

### Correlação — Pearson vs Spearman

A maior divergência entre os métodos aparece em variáveis assimétricas como **renda familiar**, onde Spearman se mostra mais robusto. Para as notas do ENEM — calculadas pelo TRI — os métodos convergem, pois o TRI naturalmente aproxima as distribuições da normalidade.

---

## Limitações

- **Correlação não implica causalidade** — o acesso à internet pode ser proxy de outras condições favoráveis dentro da baixa renda, como moradia mais estável ou maior escolaridade dos pais.
- A definição de "baixa renda" foi testada em múltiplos critérios justamente por não haver um corte universalmente aceito.
- Treineiros não foram removidos da análise geral.

---

## Tecnologias

- Google Colab (ambiente de desenvolvimento)
- Python 3
- Google Colab
- Pandas
- Scipy
- Seaborn
- Matplotlib
- Numpy
- Kagglehub
