## Regressão Linear

Neste notebook vamos desenvolver um modelo de regressão linear para **Precificação de Plano de Saúde**, buscando prever a variável de custo. Com o modelo pronto,
as operadoras de plano de saúde poderão informar a margem de lucro desejada e ter, facilmente e com a aplicação de Machine Learnig, o valor a ser cobrado do 
cliente final.

# Introdução

A regressão linear é uma técnica estatística que permite modelar a relação entre uma variável dependente (ou resposta) e uma ou mais variáveis independentes (ou explicativas) contínuas. Ela é usada para prever valores da variável dependente com base nos valores conhecidos das variáveis independentes. Faz parte dos algoritmos de modelos de aprendizado Supervisonado do grande universo de Machine Learning.

A regressão linear é chamada assim porque assume que a relação entre as variáveis é linear, ou seja, pode ser representada por uma linha reta em um gráfico. A equação da linha é dada por:

    y = β0 + β1*x1 + ε

onde y é a variável dependente que queremos prever, x1 é a variável independente, β0 e β1 são os parâmetros da linha (intercepto e inclinação, respectivamente), que estimam a relação entre x e y, e ε é o erro aleatório - que deve ser observado e tratado.

O objetivo da regressão linear é encontrar os valores de β0 e β1 que melhor se ajustam aos dados observados, de modo a minimizar a soma dos quadrados dos erros entre as previsões da linha e os valores reais. Esse processo é chamado de ajuste de modelo.

A regressão linear pode ser usada para uma variedade de fins, incluindo previsão, controle de qualidade, análise de correlação e identificação de fatores de risco. No entanto, ela pressupõe que as relações entre as variáveis são lineares e que os erros são independentes e têm distribuição normal. Portanto, é importante verificar essas suposições antes de utilizar a regressão linear.

# Objetivo

Depois dessa breve introdução sobre o assunto, é hora de por a mão na massa e construir nosso primeiro modelo.

No caso do nosso objetivo, que é prever o custo do plano de saúde, para que a operadora do plano possa informar a margem de lucro que deseja aplicar e ter, facilmente, o valor final a ser cobrado do cliente.

Para isso, usaremos a regressão linear para encontrar a relação entre as características dos pacientes e o custo do plano. As características que usaremos para prever o custo incluem idade, sexo, índice de massa corporal (IMC), número de filhos, e fumante ou não. A partir dessas informações, o modelo de regressão linear será capaz de prever o custo do plano com base nas características de um novo paciente.

# Preparação dos dados e Análise Exploratória

Essas duas etapas são fundamentais para um bom resultado. Na primeira é onde são feitos os processos de limpeza e transformação dos dados brutos para que seja 
possível uma análise mais clara e confiável. Isso pode incluir a remoção de dados ausentes ou duplicados, a transformação de variáveis
para outros formatos (por exemplo, de texto para números), a normalização de valores e a criação de novas variáveis a partir das existentes. 

A análise exploratória, por sua vez, envolve a exploração dos dados para entender melhor suas características e padrões. Isso pode incluir a visualização dos 
dados em gráficos ou tabelas, a análise de estatísticas descritivas (como média, desvio padrão, quartis, etc.), a identificação de outliers e a exploração de 
correlações entre variáveis.

# Ajuste dos dados
Para que os dados possam ser usados em uma regressão linear, é importante que eles atendam a certos requisitos:

    As variáveis devem ser numéricas: todas as variáveis utilizadas no modelo, precisam ser do tipo numérica,
    Linearidade: os dados devem estar relacionados linearmente. Isso pode ser verificado plotando um gráfico de dispersão entre as variáveis para ver se há uma tendência linear - este gráfico já foi construido na fase de análise exploratória.
    Normalidade: Os dados devem seguir uma distribuição normal para garantir a precisão dos resultados da regressão linear. A normalidade pode ser verificada plotando um histograma dos dados, que também já foi gerado na sessão anterior.
    Homocedasticidade: Os dados devem ter uma variância constante em toda a faixa de valores das variáveis independentes, ou seja, precisam estar em escalas parecidas.
    Independência: As observações dos dados devem ser independentes entre si. Ou seja, uma observação não deve ser afetada pela observação anterior ou posterior.

Se os dados atenderem a esses requisitos, é possível usá-los em uma regressão linear. É importante lembrar que a regressão linear é uma técnica estatística poderosa, mas é essencial que os dados sejam cuidadosamente analisados e preparados antes de serem usados para evitar resultados imprecisos ou enganosos.

Por exemplo, uma variável com valores possíveis "yes" e "no" foi transformada em 0 ou 1:
![image](https://user-images.githubusercontent.com/11036213/222989043-dbb7c9b3-7fc7-4b62-b6e1-642618cd0ff3.png)

Outras transformações foram feitas e estão descritas no notebook. A seguir, vamos para o modelo.

