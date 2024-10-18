# clientes-com-maior-risco-de-churn
Classificação de clientes com maior risco de churn
1. Introdução
O objetivo deste projeto é prever a rotatividade (churn) de clientes de um banco, utilizando técnicas de aprendizado de máquina para identificar os fatores que contribuem para a saída dos clientes e melhorar as ações de retenção. O modelo foi desenvolvido para identificar clientes que têm alta probabilidade de deixar o banco, permitindo que a instituição financeira possa tomar medidas proativas.

2. Metodologia
O projeto foi dividido em várias etapas, conforme descrito a seguir:

2.1. Coleta e Preparação de Dados
Base de Dados Utilizada
Nome do arquivo: BankChurners.csv
Tamanho: 23 colunas com 10.127 registros
Principais colunas:
Attrition_Flag: Indica se o cliente saiu ou permaneceu no banco.
Customer_Age, Dependent_count, Income_Category, entre outras, que representam dados demográficos e comportamentais dos clientes.
Passos de Tratamento
Verificação de valores duplicados e ausentes: Não foram encontrados dados duplicados. Para valores ausentes, as linhas com valores ausentes foram removidas.

Normalização: Todas as variáveis numéricas foram normalizadas utilizando o MinMaxScaler para garantir que estivessem na mesma escala, variando entre 0 e 1.

Conversão de variáveis categóricas: As variáveis categóricas foram convertidas em numéricas usando One-Hot Encoding, permitindo que o modelo lidasse com essas colunas adequadamente.

2.2. Análise Exploratória de Dados (EDA)
Durante a EDA, foram exploradas algumas variáveis importantes:

Distribuição de churn: Cerca de 16% dos clientes na base de dados tinham o status "Attrited Customer" (clientes que deixaram o banco).

Distribuições demográficas: Gênero, estado civil, nível de escolaridade e tipo de cartão foram algumas das variáveis exploradas para entender os perfis dos clientes. Vimos que a maioria dos clientes utilizava cartões da categoria Blue, e as faixas de renda variavam significativamente.

2.3. Modelagem e Treinamento
Modelos Utilizados
O modelo principal escolhido foi o Random Forest, devido à sua robustez e capacidade de capturar interações complexas entre as variáveis.

Foi aplicada a técnica de validação cruzada com 5 folds para garantir a robustez do modelo.

Treinamento
Os dados foram divididos em 80% para treinamento e 20% para teste.

O modelo foi treinado no conjunto de treinamento e atingiu 100% de acurácia no conjunto de teste, o que inicialmente indicou um possível overfitting.

2.4. Avaliação de Desempenho
Métricas Utilizadas:
Acurácia: O modelo atingiu uma acurácia de 100%, tanto no conjunto de teste quanto na validação cruzada, indicando que ele está classificando corretamente todos os clientes como churn ou não churn.

Matriz de Confusão: O modelo foi perfeito em prever os dois grupos: tanto os clientes que deixaram o banco quanto os que permaneceram.

Relatório de Classificação: A precisão, o recall e o F1-score para ambas as classes (churn e não churn) foram 1.0.

Importância das Variáveis:
As variáveis mais importantes para o modelo incluíram:
Months_Inactive_12_mon: Meses de inatividade nos últimos 12 meses.
Total_Trans_Amt: Valor total das transações realizadas pelos clientes.
Total_Relationship_Count: Número total de produtos que o cliente possui com o banco.
Total_Trans_Ct: Contagem total de transações.
3. Considerações Finais
Resultados
O modelo apresentou um desempenho excelente com uma acurácia perfeita. Embora isso seja impressionante, é importante observar que a acurácia perfeita pode indicar overfitting, e seria essencial testar o modelo com novos dados ou dados de períodos futuros para garantir sua robustez.

As variáveis relacionadas ao comportamento transacional e à inatividade dos clientes mostraram ser os fatores mais influentes na decisão de churn. Isso sugere que clientes que realizam menos transações ou estão inativos por longos períodos tendem a ter uma maior probabilidade de deixar o banco.

Recomendações
Monitorar clientes inativos: A empresa deve priorizar campanhas de retenção para clientes que estão inativos por muitos meses, oferecendo incentivos para reativar suas contas.

Focar em clientes com poucas interações: Clientes com poucos produtos financeiros ou que realizam poucas transações devem ser acompanhados de perto, pois podem estar insatisfeitos ou com baixo envolvimento.

Coletar mais dados: Continuar coletando dados e revisar o modelo periodicamente para garantir que ele continue relevante em diferentes períodos.
