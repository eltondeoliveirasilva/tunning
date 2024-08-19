# tunning

A Importância do Tuning

Antes de entrarmos nos algoritmos específicos, é importante entender por que fazer tuning é essencial para obter o melhor desempenho possível dos modelos.

Quando treinamos um modelo de ML, como uma Random Forest ou SVM, existem vários parâmetros e hiperparâmetros que controlam seu comportamento. Por exemplo:


Número de árvores em uma floresta aleatória
Profundidade máxima das árvores
Taxa de aprendizado do gradiente descendente
Função kernel para SVMs
e muitos outros

Os valores default nem sempre resultam no melhor desempenho. Na verdade, dificilmente serão os ideais para um problema específico.

Além disso, diferentes combinações de parâmetros interagem de forma não linear e o espaço de busca é gigantesco. Testar manualmente é humanamente impossível.

Felizmente, técnicas como Grid Search e Random Search nos permitem explorar automaticamente este espaço de parâmetros para descobrir a melhor configuração para nosso dataset e métrica desejada.

Isso pode melhorar consideravelmente métricas como acurácia, AUC-ROC, F1-score, etc. Ou seja, mais capacidade preditiva e utilidade prática dos modelos.

Grid Search

O Grid Search realiza uma busca exaustiva dos melhores parâmetros em uma grade (grid) pré-definida pelo usuário.

A ideia é definir valores ou intervalos de valores para explorar em cada parâmetro ou hiperparâmetro. Por exemplo:


Número de árvores: 100, 200 e 300
Profundidade máxima: 5, 10 e 15
Taxa de aprendizado: 0.01, 0.05 e 0.1

O Grid Search então treina modelos com todas as possíveis combinações desses valores (100 árvores com profundidade 5 e taxa 0.01, 100 árvores com profundidade 5 e taxa 0.05, etc) e avalia o desempenho de cada um.

Ao final, ele seleciona os hiperparâmetros que obtiveram o melhor score na métrica definida, como acurácia, AUC-ROC ou outra.

Dessa forma, garantimos que encontramos a melhor configuração dentro do grid especificado, sem precisar testar manualmente.

Por outro lado, definir os valores do grid requer algum conhecimento prévio sobre bons intervalos para explorar em cada parâmetro. Também pode ser computacionalmente caro testar todas as combinações em problemas mais complexos.

Random Search

O Random Search resolve alguns dos problemas do Grid Search usando uma abordagem aleatória, como o próprio nome diz.

Ao invés de testar todas as combinações, ele gera aleatoriamente valores para cada parâmetro dentro de ranges especificados, treina o modelo e avalia o desempenho.

Isso é repetido por um número pré-definido de iterações. Os melhores hiperparâmetros encontrados são então usados para treinar o modelo final.

As vantagens são:


Menos computacionalmente intensivo, pois não avalia todas as combinações
Pode encontrar valores ótimos mesmo que não tenham sido especificados no grid inicial
Mais simples de definir os ranges iniciais

Por outro lado, como se baseia em aleatoriedade, não há garantia que os globais serão encontrados.

Geralmente o Random Search é usado para ter uma noção inicial dos melhores valores, que podem então ser refinados com Grid Search posteriormente.

Exemplos Práticos
