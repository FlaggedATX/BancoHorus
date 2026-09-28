# Interpretação de AUC

**Empresa/categoria:** Consultoria
**Vaga:** Estágio em Análise de Dados
**Tema:** Machine Learning
**Nível:** Estágio

---

## Contexto

Estava explicando um EDA (Exploratory Data Analysis) de um dataset financeiro, ao apresentar as estatísticas do meu modelo de regressão logística (como AUC e Acurácia) veio a questão.

## Questão

"Como você interpreta o AUC do seu modelo?"

## Resposta

O AUC mede a capacidade do modelo de diferenciar as duas classes. Por exemplo, um AUC de 0,85 significa que, ao comparar aleatoriamente um exemplo positivo com um negativo, o modelo dá uma pontuação maior para o positivo em aproximadamente 85% das vezes. Quanto mais próximo de 1, melhor a capacidade de discriminação, enquanto 0,5 representa um desempenho equivalente ao acaso.

## Explicação

O AUC (Area Under the Curve) vem da curva ROC, que mostra como o modelo se comporta conforme mudamos o threshold usado para separar as classes. Para cada threshold, temos uma combinação diferente de taxa de verdadeiros positivos e falsos positivos.

A área sob essa curva resume esse comportamento em um único valor. Por isso, um AUC alto indica que o modelo consegue manter uma boa separação entre as classes mesmo quando o threshold muda.

Uma forma intuitiva de entender o AUC é pensar na capacidade do modelo de ordenar corretamente os exemplos: se pegarmos aleatoriamente um positivo e um negativo, queremos que o modelo dê uma pontuação maior para o positivo. O AUC representa justamente a proporção de vezes em que isso acontece.

Por exemplo, imagine que escolhamos 10 pares de observações, cada par contendo um caso positivo e um negativo. Se o modelo atribuir uma pontuação maior ao positivo em 8 dos 10 pares, teríamos uma estimativa de AUC de aproximadamente 0,80.

| AUC | Interpretação |
|---|---|
| **1,0** | Separação perfeita |
| **0,9 – 1,0** | Excelente |
| **0,8 – 0,9** | Boa |
| **0,7 – 0,8** | Razoável |
| **0,5 – 0,7** | Baixa |
| **0,5** | Equivalente ao acaso |
| **< 0,5** | Pior que o acaso |

Isso também explica por que o AUC é diferente da acurácia. A acurácia depende de um threshold específico, enquanto o AUC avalia a capacidade de discriminação do modelo considerando diferentes thresholds.

**Origem da questão:** `relato`
**Contribuidor:** [@FlaggedATX]
