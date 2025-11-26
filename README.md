# Teste de Hipóteses Z de Duas Amostras

1. Visão Geral do Projeto
Este projeto tem como objetivo principal aplicar o Teste de Hipóteses Z de Duas Amostras para determinar se existe uma diferença estatisticamente significativa no desempenho de alunos submetidos a duas metodologias de ensino distintas: Estratégia A e Estratégia B.

O objetivo de negócio é justificar cientificamente a implementação da estratégia de maior sucesso em larga escala. A análise se baseia na comparação das médias das notas obtidas pelos dois grupos.

2. Preparação dos Dados e Simulação
Esta seção estabelece o cenário do teste e gera os dados de exemplo para a aplicação do Teste Z.

Importação de Bibliotecas: Foram importadas numpy (para simulação de dados), pandas, matplotlib.pyplot e, crucialmente, statsmodels.stats.weightstats.ztest (para realizar o Teste Z) e scipy.stats.norm (para referência à distribuição normal).

Dados Simulados: Como o objetivo é demonstrar o procedimento, os dados foram simulados com np.random.normal().

Estratégia A: Média de 75 e Desvio Padrão de 8.

Estratégia B: Média de 80 e Desvio Padrão de 7.

Justificativa: O Teste Z é aplicável neste caso sob a suposição de que o desvio padrão populacional é conhecido ou que o tamanho da amostra é grande (n > 30 para ambos os grupos), o que é atendido no código (50 alunos por grupo).

3. Formulação das HipótesesO teste estatístico é estruturado em torno das seguintes hipóteses, que definem o que está sendo testado.Hipótese Nula ($H_0$): Não há diferença estatisticamente significativa entre as notas médias das duas estratégias.
$$\mu_A = \mu_B$$

Hipótese Alternativa ($H_a$): A nota média da Estratégia B é superior à nota média da Estratégia A (Teste Unilateral).
$$\mu_B > \mu_A$$

4. Execução do Teste Z de Duas AmostrasO teste é realizado usando a função ztest do statsmodels.Função Utilizada: ztest(x1=notas_B, x2=notas_A, value=0, alternative='larger')x1 e x2: As amostras de notas dos dois grupos.value=0: Representa a diferença sob a Hipótese Nula (assumimos que a diferença é zero).alternative='larger': Define o teste como unilateral (unidirecional), testando especificamente se a Estratégia B é "maior" que a Estratégia A, alinhado com a hipótese $H_a$.

Saídas: A função retorna a Estatística Z e o Valor P (Unilateral).

Estatística Z: Mede o número de desvios padrão que a diferença observada nas médias das amostras está distante da diferença hipotética (zero).

Valor P: A probabilidade de observar uma diferença tão extrema (ou mais extrema) quanto a que foi realmente observada, assumindo que a Hipótese Nula é verdadeira.

5. Conclusão e Impacto de Negócio
Nível de Significância ($\alpha$): Definido em 0.05 (ou 5%).
Decisão Estatística:
Se Valor P < $\alpha$: Rejeitamos $H_0$. A diferença observada é estatisticamente significativa.
Se Valor P $\ge$ $\alpha$: Não Rejeitamos $H_0$. Não há evidências suficientes para provar que a Estratégia B é superior.

Resultados Típicos (Com base nos dados simulados):

O Valor P (unilateral) resultante tende a ser muito baixo (muito menor que 0.05).
Conclusão de Negócio:
Rejeita-se a Hipótese Nula ($H_0$). Existe uma diferença estatisticamente significativa nas notas médias.
A Estratégia B tem um desempenho médio comprovadamente superior à Estratégia A.
Recomendação: A escola deve considerar a implementação da Estratégia B em larga escala, pois os resultados não são devidos ao acaso.
