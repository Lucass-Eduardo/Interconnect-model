# Descrição do projeto

Um dado que já é conhecido pelos grandes fornecedores de serviços é que é mais barato manter um cliente do que atrair novos clientes. Neste projeto, recebi a tarefa de prever o cancelamento dos serviços da empresa de comunicação e serviços *Interconnect*.

A *Interconnect* forneceu uma amostra dos dados de seus clientes. Com esses dados, foi possível desenvolver um modelo de *machine learning* capaz de prever potenciais clientes que irão cancelar seus planos. O maior problema ao treinar esse modelo foi escolher as características corretas. Utilizei como base a correlação para selecionar as características e testei várias combinações diferentes até encontrar as melhores. Além disso, utilizei o ***RandomizedSearchCV***, um método de ajuste de hiperparâmetros, para encontrar o ajuste com o melhor desempenho, baseado em uma métrica escolhida. A métrica utilizada foi a *AUC-ROC*, que fornece uma única métrica que resume a capacidade do modelo de classificação em diferentes limiares, considerando tanto a Sensibilidade quanto a Especificidade.

Nas amostras, havia pequenos erros que foram fáceis de corrigir. Para analisar a correlação e distribuição dos dados, foi necessário converter várias colunas categóricas alfabéticas em numéricas. Eu poderia ter usado algoritmos prontos da biblioteca sklearn, mas escolhi escrever minha própria função para poder personalizar da forma que fosse conveniente para mim.

Utilizei 5 algoritmos de aprendizado de máquina diferentes e o que teve o melhor resultado foi o CatBoost, que obteve `0.92` na validação e `0.89` no teste. Para chegar a esse resultado, tive que diminuir as features e combiná-las para criar uma nova. Além disso, o fato do CatBoost aceitar dados do tipo `datetime` também influenciou no resultado final.
