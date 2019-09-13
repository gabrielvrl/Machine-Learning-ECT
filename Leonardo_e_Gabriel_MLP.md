# MULTILAYER PERCEPTRON PARA PREVISÃO EM APROVAÇÃO DE ALUNOS NA DISCIPLINA DE PROGRAMAÇÃO

## Introdução
O trabalho abordará um programa de multilayer perceptron que tratará de analisar alguns dados e, a partir disso, identificar a situação de cada discente em uma turma.
Para a realização do trabalho, foram utilizados diferentes tipos de bibliotecas de programação, todos aplicados à linguagem Python. O programa tende a adquirir os dados dos alunos referentes ao início do semestre para que, dessa maneira, seja possível estimar como cada aluno estaria no final do semestre e, a partir disso, identificar suas maiores dificuldades.
Dentre as bibliotecas utilizadas no programa estão:
* sklearn;
* keras;
* pandas.
O objetivo do trabalho é a previsão da situação dos discentes ao final do período letivo referente à matéria de Lógica de Programação e, para isso, foram utilizados dados referentes às primeiras três semanas de aula, além da nota da primeira unidade para que, dessa maneira, pudesse ser feito um treino por meio de uma MLP de forma eficiente, gerando um resultado de predição aceitável. 


### Contribuidores

Leonardo Queiroz, aluno de bacharelado em engenharia mecânica na Universidade Federal do Rio Grande do Norte, contato em:
- [Github](https://github.com/leocqueiroz)

Gabriel Varela, aluno da Universidade Federal do Rio Grande do Norte do curso de bacharelado em engenharia mecatrônica. Contato em:
- [Github](https://github.com/gabrielvrl)
- [Site](https://gabrielvrl.github.io/)

### Scikit-Learn

Essa biblioteca é utilizada para métodos de aprendizado da máquina, ou seja, para auxiliar no processo de training da inteligência artificial.
No programa essa biblioteca foi utilizada para separar os dados entre treino e teste, que é possível analisar pela Fig. (01), parte crucial para o desenvolvimento de um programa MLP, além de ser utilizada para criar a matriz de confusão analisada no programa, onde essa utilização é possível ser observada na Fig. (02).

![DivisaodeDados](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/divisao_de_dados_entre_treino_e_teste_por_scikit_learn..png)
Figura 01. Divisão de dados entre treino e teste por Scikit-Learn.

![CriacaodaMatriz](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/criacao_da_matriz_de_confusao_por_scikit_learn.png)
Figura 02. Criação da matriz de confusão por Scikit-Learn.


### Keras
Essa biblioteca foi projetada para permitir uma fácil experimentação de dados em redes neurais, ou seja, para a fase de testes do programa. Ela se destaca por ser modular, extensível e fácil de usar.
No programa essa biblioteca foi utilizada para criar as camadas do multilayer perceptron, processo necessário para realizar a fase de treino, bem como pela distribuição de treino por meio de um otimizador chamado “adam”, o qual possibilitou separar os dados em épocas e suas devidas quantidades de dados.

![Keras](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/keras_utilizado_para_criar_as_camadas_da_MLP_e_para_otimizar_o_sistema_de_teste.png)
Figura 03. Keras utilizado para criar as camadas da MLP e para otimizar o sistema de teste.

Na Fig. (03) é perceptível que o Keras foi utilizado para criar 4 multicamadas. A primeira camada, que possui uma função “relu” possui 8 entradas, que se referem às 8 colunas selecionadas nos dados disponíveis e, em seguida, se divide entre 16 células correspondentes. As 2 camadas subsequentes são processos de aperfeiçoamento de cálculo, utilizando funções “relu”. A parametrização das unidades foi realizada por meio de tentativa e erro. Os valores foram alterados para encontrar um equilíbrio, sem que houvesse um underfitting ou um overfitting. Já a última camada possui apenas uma unidade, que seria a unidade de resposta e possui uma função “sigmoidal”, formada apenas por um resultado binário 0 ou 1.
Ainda na Fig. (03) é possível visualizar que na fase de treino foi utilizado um otimizador chamado “adam”, onde foi utilizado um fit para fazer a simulação. Foi escolhido um batch_size igual à 10, bem como 80 epochs. Isso se refere ao processo de solução do sistema, onde haverão 80 fases de teste, analisando 10 parcelas de dados por cada fase. Esses dados também foram parametrizados de forma a evitar underfitting e overfitting.


## Pandas 

Essa biblioteca é utilizada para manipulação e análise de dados, assim como adiciona ferramentas para manipular tabelas numéricas e trabalhar com séries temporais.
No programa essa biblioteca foi utilizada para analisar os dados de um arquivo .csv a partir de um link fornecido.

![Pandas](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/obten%C3%A7%C3%A3o_dos_dados_utilizando_a_biblioteca_pandas.png)
Figura 04. Obtenção dos dados utilizando a biblioteca pandas.

Na Fig. (04) é possível analisar que a obtenção dos dados foi feita utilizando a biblioteca pandas, de forma direta pelo link de um arquivo .csv.

### METODOLOGIA
Para realizar o estudo do MLP foram utilizados dados referentes à alunos de uma grade curricular do curso de Bacharelado em Ciências e Tecnologia. Para isso, os dados utilizados foram retirados de um arquivo .csv disponíveis no link (raw) abaixo:

https://raw.githubusercontent.com/ect-info/ml/master/dados/DataBaseLop.csv				   (1)

O link (1) possui os dados utilizados para o programa, o qual avalia o desempenho dos alunos ao longo do semestre de diversas maneiras possíveis.
Inicialmente, para realização do processo, foi escolhido os parâmetros utilizados para o MLP, ou seja, os parâmetros ideais para que a fase de treino fosse realizada adequadamente.
Como descrito na introdução, foi necessário escolher parâmetros referentes às primeiras três semanas de aula, bem como a nota da primeira unidade da disciplina, para gerar uma maior precisão dos resultados. Dessa maneira os parâmetros selecionados foram:
* notaProva1 = Nota da primeira prova da disciplina.
* qsub(1, 2 e 3) = Quantidade de submissões das listas correspondente para as 3 primeiras semanas;
* qsubp1 = Quantidade de questões submetidas para a prova 1;
* qsemana(1, 2 e 3) = Quantidade de dias diferentes que houve submissão nas 3 primeiras semanas;

### RESULTADOS
Para a correta análise dos resultados, foi utilizado um sistema de predict, o qual irá ser o responsável para realizer o teste da MLP. O Código referente à isso está claro na Fig. (05).

![Predict](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/predict_para_realização_do_teste_de_resultados.png)
Figura 05. Predict para realização do teste de resultados.

Após a realização do teste, foi montada a matriz de confusão, bem como pode ser observada na Fig. (02).
Assim sendo, o resultado obtido foi de 81,25% de acerto, o qual pode ser observado na seguinte figura.

![Resultados](https://github.com/gabrielvrl/Machine-Learning-ECT/blob/master/Imagens/resultados.png)
Na Fig. (06), é perceptível os resultados da matriz de confusão, bem como a taxa de acerto, que foi de 81,25%, além da quantidade de dados utilizados para teste, que foram de 112.


### REFERÊNCIAS
Keras: The Python Deep Learning library. Disponível em: <https://keras.io/>; Acesso em 06 de setembro de 2019.

Scikit-Learn: Machine Learning in Python. Disponível em: <https://scikit-learn.org/stable/>; Acesso em 06 de setembrto de 2019.

Pandas Data Analysis Library. Disponível em: <https://pandas.pydata.org/>; Acesso em 06 de setembro de 2019.
