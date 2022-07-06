# projeto_bimaster

<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Aplicação de modelos de previsão de vendas para o Walmart

#### Aluno: [Felipe Lopes Meira Alves](https://github.com/felipelopesmeira)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/link_do_repositorio). <!-- caso não aplicável, remover esta linha -->





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

Os resultados apresentados para ambos os modelos na aplicação do random forest apresentaram grande similaridade. 

	Random Forest	Decision Tree	RNN	LSTM
	Modelo 1	Modelo 1	Modelo 1	Modelo 1
RMSE	164252.0124	163784.0344	176657.5269	198503.6568
MSE	26978723567	26825209938	31207881823	39403701756
MAPE	6.10%	6.82%	6.93%	7.35%
R2_score	-4.32357196	0.411642147	-0.299064598	-32.39108755
RMSPE	[8.77648461] %	[9.25900233] %	[10.16531628] %	[10.22618955] %
				
	Random Forest	Decision Tree	RNN	LSTM
	modelo 2	modelo 2	modelo 2	modelo 2
RMSE	163645.055	203595.0168	147799.1411	83895.53846
MSE	26779704019	41450930877	21844586111	7038461373
MAPE	5.76%	6.86%	7.59%	4.08%
R2_score	-2.05126665	0.075799839	0.259506948	0.689388737
RMSPE	[8.51515159] %	[11.68523346] %	[9.28600371] %	[5.29037507] %
![image](https://user-images.githubusercontent.com/48620885/177659439-3404a916-aa2e-4025-aff3-33754a19e92d.png)


### 4. Conclusões

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

---

Matrícula: 202.100.120  

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
