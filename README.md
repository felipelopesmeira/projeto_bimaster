# projeto_bimaster

<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Aplicação de modelos de previsão de vendas para o Walmart

#### Aluno: [Felipe Lopes Meira Alves](https://github.com/felipelopesmeira)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/felipelopesmeira/projeto_bimaster). <!-- caso não aplicável, remover esta linha -->





---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

Este trabalho tem como objetivo explorar modelos de machine learning e redes neurais com intuito de obter o melhor resultado na otimização da previsão de vendas da loja número 1 do Walmart.



### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

This work aims to explore machine learning models and neural networks in order to obtain the best result in optimizing the sales forecast of Walmart's number 1 store.

### 1. Introdução

O Walmart é uma multinacional de lojas de departamento. O projeto proposto faz uso da base de vendas de 45 lojas espalhadas pelos Estados Unidos no período de 2010 a 2012.

A base contém além da informação de vendas, outras variáveis importantes para o projeto como indicadores de feriados, temperatura, preço da gasolina, taxa de desemprego e CPI (índice de preços ao consumidor).

Com uma análise geral das 45 lojas, há alguns pontos que se destacam na base:

- O Walmart teve seu melhor desempenho em vendas em 2011 e o pior em 2012;

![image](https://user-images.githubusercontent.com/48620885/174113940-a7928b86-5c13-4865-9fca-38dd37c2582a.png)


- As lojas que mais venderam obtiveram suas maiores vendas no mês de Dezembro e nos anos de 2010 e 2011;

![image](https://user-images.githubusercontent.com/48620885/174111929-351dd97b-2bc9-4e88-ab45-5ad0afd898f5.png)


- Em relação à correlação entre as variáveis, temos o efeito do aumento do desemprego, CPI (índice de preços ao consumidor) e temperatura impactando negativamente a variável Weekly_sales (vendas semanais);

![image](https://user-images.githubusercontent.com/48620885/174110264-cd8bfe9a-2512-4227-b874-7deb2a2df81a.png)

- Após a análise exploratoria inicial da base, foi selecionada aleatoriamente a loja de número 1 do Walmart. Interessante ressaltar que essa loja não figura entre as maiores vendas da base.

### 2. Modelagem

O projeto proposto foi dividido em duas abordagens. Uma considera apenas as informações de vendas e a outra considera também as séries feriados, temperatura, preço da gasolina, taxa de desemprego e CPI.

Modelo 1: Apenas considerando os dados de vendas.

1. Para a previsão de vendas do modelo foi determinada uma janela de 20 entradas.
2. Separação da base entre treino e teste. 
3. Normalização das bases.
4. Aplicação dos modelos Random forest, Decision Tree, Redes neural com multiplas camadas e LSTM.
5. Avaliação dos modelos utilizando RMSE, MSE, R2 e RMSPE.
6. Previsão das proximas 12 entradas de vendas.

Modelo 2: Considerando os dados de vendas e as séries exogenas.

1. Para a previsão de vendas do modelo foi determinada uma janela de 20 entradas.
2. Separação da base entre treino e teste. 
3. Normalização das bases.
4. Aplicação dos modelos Random forest, Decision Tree, Redes neural com multiplas camadas e LSTM.
5. Avaliação dos modelos utilizando RMSE, MSE, R2 e RMSPE.
6. Previsão das proximas 12 entradas de vendas.

### 3. Resultados

Avaliando-se os dois modelos os seguintes resultados foram obtidos:

RMSE e MSE são métricas que calculam a média da diferença entre o valor predito e o real. Quanto maior o valor encontrado, maior a significância que o modelo não obteve uma boa performance. Nesta análise, o modelo 2 LSTM apresentou os valores mais baixos sendo superior aos demais modelos nesses quesitos. 

MAPE é uma métrica que mostra a porcentagem de erro em relação aos valores reais. No modelo 2 LSTM, o MAPE apresentou o percentual de 4.1%. Então se o resultado de MAPE for igual a 4.1%, significa que o modelo faz previsões em que a média da diferença entre o valor previsto e o real equivale a 4.1% do valor real, tanto para mais quanto para menos.

R2_score representa o percentual da variância dos dados que é explicado pelo modelo, os resultados variam entre 0 e 1 quanto maior é o valor de r2 mais explicativo é o modelo. O modelo de maior tamanho no quadro analisado foi do modelo 2 LSTM. 

RMSPE mensura o erro percentual em relação a magnitude da variável. O menor valor encontrado foi também no modelo 2 LSTM.

Os melhores resultados foram encontrados pelo modelo 2 LSTM que considera as séries exogenas.

![image](https://user-images.githubusercontent.com/48620885/177659988-0a367aa7-58fc-4f73-9410-55a46f09a3be.png)



### 4. Conclusões

O objetivo do trabalho foi explorar modelos de machine learning e redes neurais com intuito de obter o melhor resultado na otimização da previsão de vendas da loja número 1 do Walmart. A rede que obteve destaque na avaliação foi a LSTM com o diferencial da sua capacidade padrão de lembrar de informações por longos períodos de tempo, o que a torna indicada para previsão de séries temporais em longos intervalos de tempo. Ao análisar o modelo 2 LSTM do real x previsto houve semelhança nos movimentos do gráfico. 

![image](https://user-images.githubusercontent.com/48620885/179369590-18a77eab-0649-414d-908b-6fd625e036a6.png)


O modelo 2 LSTM na previsão dos próximos 12 passos seguiu o mesmo padrão de comportamento da série, demonstrando sua capacidade de memória da informação e capacidade preditiva.

![image](https://user-images.githubusercontent.com/48620885/178614862-e0dd2dc3-2494-4c95-8c77-5f3e54a59303.png)

Portanto, durante a avaliação dos modelos, houve destaque para o modelo 2 LSTM com resultados superiores em todos os indicadores de avaliação abordados no capítulo de resultados. O modelo 2 LSTM, que tem como característica o uso das séries exógenas, ao ser combinado com otimizador Adam foi o que gerou os melhores resultados.


---

Matrícula: 202.100.120  

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
