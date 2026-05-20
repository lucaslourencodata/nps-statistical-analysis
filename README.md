# 📊 NPS Statistical Analysis: A Bootstrap Approach

Este projeto apresenta uma abordagem analítica e estatisticamente rigorosa para a avaliação do **Net Promoter Score (NPS)** de uma instituição financeira. O objetivo principal é mitigar vieses de resposta e quantificar a incerteza associada à métrica de satisfação por meio de inferência estatística.

---

## 🎯 Contexto do Problema e Justificativa

O Net Promoter Score (NPS) é um indicador crítico para medir a lealdade do cliente, identificar potenciais focos de *churn* e guiar estratégias de relacionamento. No entanto, um desafio comum na aplicação prática do NPS é o **viés de resposta**: como a pesquisa não é obrigatória, a base de respondentes tende a ser composta por extremos (clientes altamente satisfeitos ou muito insatisfeitos), o que pode distorcer a visão real da população.

Para trazer mais robustez e confiabilidade à tomada de decisão, este projeto aplica técnicas de **inferência estatística**. Ao selecionar amostras aleatórias e calcular intervalos de confiança, conseguimos estimar o comportamento real da população de respondentes com incerteza rigorosamente controlada.

---

## 🧪 Metodologia Estatística

A análise seguiu um pipeline estruturado de Ciência de Dados:

1. **Análise de Qualidade de Dados:** Verificação e tratamento de dados nulos ou inválidos que pudessem distorcer as métricas.
2. **Amostragem Aleatória:** Seleção de uma amostra representativa ($n = 1000$) utilizando sementes aleatórias para reprodutibilidade.
3. **Teste de Normalidade:** * Aplicação do teste de **Shapiro-Wilk** para validar a distribuição dos dados.
   * Construção de gráficos de diagnóstico (**Q-Q Plot** e Histograma).
4. **Estimação por Bootstrap:** Como os dados de NPS não seguem uma distribuição normal, utilizou-se o método não-paramétrico de reamostragem (*Bootstrap*) com 5.000 repetições para a construção de Intervalos de Confiança (IC) de 95%.
5. **Análise Temporal:** Avaliação da evolução mensal do NPS com faixas de confiança para identificar variações reais versus ruídos estatísticos.

---

## 📈 Principais Resultados

* **Rejeição de Normalidade:** O teste de Shapiro-Wilk apresentou um p-valor extremamente pequeno ($3.94 \times 10^{-33}$), confirmando com alta evidência estatística que os dados de NPS não seguem uma distribuição normal. Isso justificou perfeitamente o uso do método Bootstrap em detrimento de testes paramétricos tradicionais (como o Teste T).
* **Intervalo de Confiança Global:** A média amostral calculada foi de **6,939**. Através do Bootstrap (95% de confiança), determinou-se que a verdadeira média da população de respondentes está compreendida entre **6,725 e 7,153**.
* **Visão Temporal:** A análise mensal permitiu mapear a consistência do indicador ao longo do tempo, gerando um gráfico de linhas estruturado com a métrica central e suas respectivas margens de erro.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

O projeto foi desenvolvido em ambiente Python, utilizando as seguintes ferramentas:

* **Pandas & NumPy:** Manipulação, limpeza e tratamento vetorial dos dados.
* **SciPy (`stats`):** Computação estatística e aplicação do teste de Shapiro-Wilk.
* **Matplotlib:** Geração dos gráficos de diagnóstico (Histograma e Q-Q Plot) e do gráfico de tendência temporal com áreas de confiança (`fill_between`).

---

## 📂 Estrutura do Repositório

* `NPStimeseries.csv`: Base de dados histórica contendo as notas de NPS e os respectivos meses de coleta.
* `nps_statistical_analysis.ipynb`: Jupyter Notebook/Google Colab contendo todo o código documentado, testes executados e visualizações gráficas.

---

## 🚀 Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone [https://github.com/lucaslourencodata/nps-statistical-analysis.git](https://github.com/lucaslourencodata/nps-statistical-analysis.git)
