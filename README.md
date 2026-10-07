# Regressão linear com PIB e Índice ABCR

Investigue se existe uma relação entre a atividade econômica brasileira e o fluxo de veículos nas rodovias. Pesquise os dados, organize uma tabela e construa um modelo de regressão linear em Python.

O **Produto Interno Bruto (PIB)** é o valor dos bens e serviços finais produzidos em um país durante um período.

O **índice de volume do PIB** acompanha a evolução da produção, descontando o efeito das mudanças de preços. Ele é construído encadeando as variações reais da produção e adota um período de referência igual a 100. Por exemplo, um índice de 120 representa um volume de produção 20% maior que o da referência. Na série utilizada, a média de 1995 corresponde a 100.

## 1. Pesquisa dos dados

Pesquise o índice de volume do PIB no IBGE e o Índice ABCR de fluxo total de veículos no Brasil. Utilize as séries **sem ajuste sazonal** e selecione **20 anos completos em comum**, preferencialmente de 2006 a 2025.

| Fonte | Acesso | O que procurar |
| --- | --- | --- |
| IBGE | [Tabela 1620 do SIDRA](https://sidra.ibge.gov.br/tabela/1620) | Selecione Brasil e “PIB a preços de mercado”. |
| ABCR | [Índice ABCR](https://melhoresrodovias.org.br/indice-abcr_2/) | Procure “Ver histórico” e a série original de fluxo total. |

## 2. Organização da base

Monte uma tabela com as seguintes colunas:

| Coluna | Conteúdo |
| --- | --- |
| `Ano` | Ano de referência dos dois indicadores. |
| `PIB_indice` | Média dos quatro índices trimestrais do PIB. |
| `ABCR_indice` | Média dos doze índices mensais da ABCR. |

Confira se todos os períodos estão disponíveis e use os **números-índice**, não as variações percentuais. Cada linha deve apresentar os dois indicadores para o mesmo ano.

## 3. Análise da relação

Crie um gráfico de dispersão com o índice do PIB no eixo horizontal e o Índice ABCR no vertical. Calcule a correlação entre as duas colunas e descreva a relação observada.

## 4. Treinamento do modelo

Treine uma regressão linear usando:

- **Entrada (`X`):** `PIB_indice`.
- **Valor a estimar (`y`):** `ABCR_indice`.
- **Treino:** os primeiros 16 anos.
- **Teste:** os quatro últimos anos.

Mantenha a ordem cronológica, sem embaralhar os registros. No scikit-learn, pesquise `LinearRegression`, `fit` e `predict`.

## 5. Avaliação dos resultados

Calcule **MAE, MSE e R²** no conjunto de teste. Apresente uma tabela com os valores observados e previstos. Explique o significado das métricas e se o modelo produziu estimativas próximas dos dados reais.

Uma correlação alta, por si só, não demonstra uma relação de causa e efeito.

## Organização do trabalho

Organize o trabalho em um notebook com as fontes consultadas, os dados, o código e uma conclusão breve. Registre as dificuldades encontradas e as soluções adotadas.

## Entregável

Envie o **link de um repositório no GitHub** contendo:

- README.md explicando a tarefa (use esse como base)
- notebook com o código e os resultados das análises;
- bases de dados utilizadas;
- conclusões sobre os resultados obtidos.

## Critérios de avaliação

A capacidade de **pesquisa e de resolução de problemas** faz parte da avaliação, assim como a preparação dos dados, a execução do modelo e a interpretação dos resultados. Justifique suas decisões; não será exigido um R² mínimo.
