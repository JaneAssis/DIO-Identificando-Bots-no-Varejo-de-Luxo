# DIO-Identificando-Bots-no-Varejo-de-Luxo
## Projeto de detecção de anomalias que indicam scalping em lançamentos de artigos de luxo.
### O documento é referente à criação de um notebook estruturado para resolver o problema de detecção de fraudes utilizando a linguagem de programação Python.
**O objetivo: colocar em prática o conteúdo estudado no módulo "detecção de anomalias em transações em Python" do "Bootcamp Bradesco - GenAI, Dados & Cyber" da plataforma DIO.**

O tema escolhido foi *"Detecção de Bots em Lançamentos de Moda de Luxo".*  Devido ao fato de não ter um assunto específico definido para a prática, foi escolhido de modo livre.
O intuito é resolver o problema de revenda não autorizada, por bots de compra, de itens de edições limitadas do varejo de luxo. Usando técnicas de Machine Learning para identificar comportamentos não humanos no momento do checkout em uma plataforma de e-commerce. 

> **A função é diferenciar as compras realizadas por humanos e por bots através de um algoritmo de classificação treinado para analisar variáveis comportamentais do usuário no site.**   

**TECNOLOGIAS UTILIZADAS:**

- Linguagem: Python 3
- Ambiente de desenvolvimento: Google Colab 

**Bibliotecas utilizadas:** 
- Pandas
- NumPy 
- Matploitlib 
- Seaborn 
- Scikit learn 

 

**GERAÇÃO E SIMULAÇÃO DOS DADOS:** 

Primeiro foi necessário importar as bibliotecas para então criar o dataset sintético que simulasse 5000 transações durante o lançamento de um item de luxo. A proporção das classes de compras ficou: 95% para compras reais (humanas) e 5% para compras artificiais (bots). 

**OBSERVAÇÃO:** Devido ao fato de dados reais de transações desse tipo serem confidenciais, foi necessária a criação de uma base de dados sintética simulando compras de um lançamento de moda.

**ATRIBUTOS:** 

Os atributos utilizados foram: 

- tempo_checkout_segundos; 
- quantidade_cliques_mouse; 
- qtd_itens_carrinho; 

**FINALIZAÇÃO:** 

Após os atributos, foi necessário juntar os dados em um dataframe, realizar o pré-processamento e então o treinamento do modelo com o RandomForestClassifier. 

Finaliza-se o código com um pequeno quadro informando os resultados, além da importância das variáveis. *(como observado nas imagens reservadas).*

**OBSERVAÇÃO:**  

No primeiro dataset sintético criado, foi constatado um resultado de **100%**. O que indica que o modelo acertou todas as previsões no conjunto de testes. 

Entretanto, isso indica um *problema* pois os parâmetros se mostraram muito claros (algo que se diverge do mundo real). Logo, foi preciso mudar os parâmetros para que os hábitos humano-bot se sobrepusessem. 

Com isso, as linhas: 

human_time_checkout = np.random.normal(loc=**45**, scale=**15**, size=n_humans) 

bot_time_checkout = np.random.normal(loc=**1.5**, scale=**0.5**, size=n_bots) 

E 

bot_mouse_clicks = np.random.normal(loc=**2**, scale=**1**, size=n_bots) 

Foram mudadas para: 

human_time_checkout = np.random.normal(loc=**20.0**, scale=**8.0**, size=n_humans) 

bot_time_checkout = np.random.normal(loc=**15.0**, scale=**10.0**, size=n_bots)  

e 

bot_mouse_clicks = np.random.normal(loc=**6**, scale=**3**, size=n_bots) 

Resultando em uma saída de dados com mais ruídos e realista. (*como mostram as imagens reservadas*) 

**CONCLUSÃO** 

Ao final do projeto, tem-se o notebook que resolve a questão de detecção de fraudes de forma adaptável para o mercado de luxo. 

**REFERÊNCIAS BIBLIOGRÁFICAS**

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
https://www.python.org/

![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)
http://scikit-learn.org/

![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)
https://pandas.pydata.org/ 
