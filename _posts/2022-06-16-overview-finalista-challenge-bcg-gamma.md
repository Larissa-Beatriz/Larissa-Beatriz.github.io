---
title: Como o time conseguiu ser finalista de um desafio do BCG Gamma
layout: post
date: 2022-06-16
image: https://overbr.com.br/wp-content/uploads/2019/09/Baanner-BGC.png
tags: [python, data-science, datathon]
comments: true
description: Projeto finalista do BCG GAMMA análise de fatores com maior impacto para o aumento de renda per capta da região.
---

# Introdução

Durante duas semanas fomos desafiados pelo BCG Gamma a criar análise avançada de dados e inteligência artificial para propor soluções para problemas reais relacionados ao desenvolvimento sustentável da Amazônia. 
Nesse tempo tivemos que entender todo a problemática, tratar de focar em uma solução e criar produto de dados que deviam ser acionáveis para o Instituto Arapyaú e para isso tivemos que iniciar pelo início e aqui nesse artigo vou passar por alguns pontos que ao meu ver foi importante para alcançarmos as finais e ser classificado como segundo lugar entre inúmeros grupos participantes, já deixo aqui os parabéns aos vencedores e a todos que participaram!

# Desafio

Com um escopo amplo o desafio era: Como promover o desenvolvimento econômico sustentável de municípios da Amazônia Legal?
Bom, só com esse problema de negócio a gente já se deparou com um oceano de possibilidades, seria necessário o afunilamento para encontrar o que queríamos resolver e o que vamos desbravar nos dados, portanto tivemo que:
- Entender a situação, definido o contexto que seria ajudar a população a ter um aumento na sua renda a partir do desenvolvimento sustentável
- Complicação, descrevemos o problema que no caso era a baixa renda per capita que as pessoas estavam tendo e o que poderíamos sugerir para aumentar

É de suma importância aqui levantar a questão de dados, sem eles não conseguiriamos alcançar o objetivo, mas mesmo assim tivemos acesso a um banco de dados bem completo e também complexos. Com isso é normal ter o instito de ir abrir as bases e já começar fazendo análises de forma aleatória, nesse ponto tivemos a capacidade de parar e criar hipóteses e uma metodologia para nos auxiliar na etapa de análise e consequentemente aplicação de algoritmos de machine learning que realmente vai ajudar na resolução do problema inicial.

## Abordagem e metodologia

Como dito anteriormente iniciamos o projeto afunilando a problemática central, partirmos do escopo geral e começamos a nos perguntar:
- O que seria um desenvolvimento sustentável
- Soluções que podem ser customizadas para cada munícipio da Amazônia Legal
- Focar nas visualizações para auxiliar no entendimento
- E claro, priorização do seria melhor a ser feito

Com isso conseguimos chegar em um escopo mais específico, que foi a tese central, que era o que queriamos alcançar: Como aumentar a renda per capita municipal na Amazônia Legal através do desenvolvimento sustentável?
E isso definido poderiamos ter um projeto bem acionável e focado em ajudar com análise de fatores com maior impacto para o aumento de renda per capta da região.

A metodologia escolhida é o princípio da pirâmide para identificar a causa raiz do problema permitindo assim focar em os pensamentos em tópicos relevantes ajudando a criar uma estrutura lógica e tornar a resolução do problema mais rápido, com isso geramos a nossa própria pirâmide.

![alt text](https://i.imgur.com/wkqPeXm.png)

Com toda a estrutura criada foi possível a criação dos nossos indicadores que serão usados nas nossas ferramentas de diagnóstico e também para um algoritmo de inteligência que será usado para a previsão do aumento da renda per capita.

# Ferramentas 

O que foi bastante comentado sobre a nossa solução foi as nossas ferramentas de diagnóstico criadas a partir dos indicadores identificados, tratados e criado na etapa anterior. Elas foram bem recebidas pois permite uma visualização rápida comparando os indicadores a nível estadual e federal do município com isso podendo ser utilizados por pessoas das esferas civis, legislativo e executivo mostrando um panorama do estado atual da renda per capita, a sustentabilidade da renda e do município.

A primeira ferramenta se faz o diagnóstico de um município o comparando entre dois indicadores, por exemplo, podiamos entrar com os indicadores de Renda Per Capita e comparar com o Índice de desigualdade e identificar para um município em questão como está sendo comparado com outros município do mesmo estado, fazendo assim uma ferramenta acionável a promover melhorias práticas.

A segunda ferramenta teve com intuito a forma de colocar os dados em perspectiva e cria sendo de urgência para agir e melhorar os indicadores, pois será comparado com outros município estaduais e federais, abaixo mostro um exemplo de comparação feita nesta ferramenta.

![alt text](https://i.imgur.com/VG5KYH7.png)

Visto que o escopo é um desenvolvimento sustentável criamos uma ferramenta para realizar o diagnóstico de quanto que o município é sustentável, permitindo assim uma visão panorâmica dos indicadores de desenvolvimento sustentável do município e com isso podemos atuar com um modelo de aprendizado de máquina para que seja possível simular de quanto será o aumento da renda per capita se melhorar X% dos indicadores desejados.

# Machine Learning

Criamos um modelo com “variáveis acionáveis” para guiar ações municipais e com isso melhorar a renda per capita dos cidadões. 
Estamos aqui criando um modelo supervisionado com uma variável contínua, renda per capita, portanto se trata de um problema dede regressão, fizemos uma experimentação longa de inúmeros algoritmos e o escolhido foi um Extreme Gradient Boosting pois foi o algoritmo que alcançou níveis aceitáveis de performance e explicabilidade, o modelo explica 57% da variabilidade da renda per capita no Brasil com erro percentual médio de 7.2%. Utilizamos 32 variáveis acionáveis - que prefeituras podem vim a influenciar.
Para previnir do sobre ajuste foi realizado a divisão de dados na proporção 80/20 e a validação cruzada e para melhorar o treinamento do modelo e ajustar os hiper parâmetros foi utilizado o método de Otimização Bayesiana.

O grande foco aqui com o algoritmo de machine learning é retirar dele as variáveis que são as mais importantes dado o alvo que a previsão da renda per capita, com isso tivemos que os indicadores de produtividade, meio ambiente e qualidade de gestão estão entre as mais relevantes e com isso podemos criar uma forma de criar valor ao utilizar esse output e simular possíveis cenários prevendo o aumento dos indicadores e verificar se teremos um aumento na renda per capita.

![alt text](https://i.imgur.com/NC3k72K.png)

Também foi possível ordenar os indicadores e identificar eles o impacto que eles tiveram na predição da variável alvo, com isso criamos os pilares de desenvolvimento sustentável com 15 variáveis mais importantes:
- Gestão da habitação e transporte
- Gestão do meio ambiente, aproveitamento do solo
- Qualidade da saúde e auxílio governamental

# Conclusão

Foi um desafio e tanto para todos do grupo, por isso preciso agradecer e muito os meus companheiros de grupo [Leonardo Fernandes de Castro](https://www.linkedin.com/in/ACoAAAQV6lgBwcHN0o_b7PK8WYRjA_J0uI3AaZ0?lipi=urn%3Ali%3Apage%3Ad_flagship3_detail_base%3BeYHS4k%2FPS0qrPysc%2Bp4nFA%3D%3D) e [Igor Cleto](https://www.linkedin.com/in/ACoAAB05OwYB5d-LQSQBK4AILoOsTGBmbVw0Vhs?lipi=urn%3Ali%3Apage%3Ad_flagship3_detail_base%3BeYHS4k%2FPS0qrPysc%2Bp4nFA%3D%3D) pelo excelente trabalho e parceria nessas semanas.