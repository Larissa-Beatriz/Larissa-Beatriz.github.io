---
title: Passos antes de aplicar machine learning
layout: post
date: 2022-07-18
image: 
tags: [python, data-science, machine-learning]
comments: true
description: Existem alguns passos antes mesmo em pensar em aplicar machine learning na empresa.
---

# Introdução

Esse assunto de machine learning está sendo muito falado e até temos algumas empresas que tem como core do seu produto aplicar machine learning de forma automática, acredito que isso seja muito bom para empresas que tem uma maturidade maior, mas devemos ter em mente que algumas variáveis precisam ser decididas e desenvolvidas antes mesmo de pensar em um algoritmo de machine learning.

<p align="center">
  <img src="https://i.imgur.com/pgjf5h2.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Algumas pessoas pensam que somente ter um time de data science é possível aplicar aprendizado de máquina e já disponibilizar para os usuários
</p>

## Alguns problemas

Quando estamos em um time de cientista de dados podemos perceber etapas que levam o projeto ao fracasso, entre elas podemos destacar:
- Pesquisar o assunto em alguns blogs e aplicar técnicas mais populares
- Escolher o algoritmo que teve a melhor performance
- Levar a solução para produção e esperar que funcione até que alguém peça para desligar

Não me entenda mal, pesquisar sobre assunto em blogs é algo que faço e é sempre bom se manter atualizado, porém nem sempre o que está escrito ali é o ideal para que seja aplicado na empresa sem ao menos levantar todos os requisitos e os riscos que possamos ter e isso também tem a ver com as técnicas que estão sendo mais comentadas, talvez aquele framework novinho ainda tem vários bugs que não conseguimos identificar anteriormente e isso acarreta em problemas futuros de manutenção e até escabilidade.

Aquele algoritmo escolhido somente pois ele deu ótimos resultados nas métricas de desempenho também pode levar o projeto a ser um fracasso, precisamos sempre validar o que realmente devemos resolver além disso devemos validar e verificar a qualidade dos dados que serão usados como input para o algoritmo e sempre levar em conta o tempo de experimentação, que também não pode ser muito longo e sem pontos de entrega/comunicação.

Mesmo com todos esses possíveis problemas, o time pode ainda levar o projeto para produção e esperar que ele desempenhe tão bem quanto foi no cenário de desenvolvimento, e isso pode ser um erro, pois há possibilidades desse problema realmente não ser solucionado pelo modelo e ainda aumentar os custos com algo que não foi de impacto positivo e no fim o projeto ser desligado.

Isso é somente alguns problemas que possamos encontrar, toda a solução não se limita a somente esses pontos apresentados, mas um que eu tenho certeza de que é um grande problema: comunicação. Podemos encontrar um problema que tão simples que passa despercebido, que é realmente entender a regras de negócio da área, sendo assim a única forma de entender é se comunicando com as pessoas chaves e líderes dessas áreas.

O time fica tanto focado nas novas tecnologias, algoritmos, ferramentas e API's, etc que esquece o que realmente estão ali para fazer, que é solucionar o problema de negócio de forma que podemos no fim aumentar a receita ou diminuir os custos. No fim, o time está fazendo as perguntas incorretas.

# Como diminuir o risco do projeto ser um fracasso?

Bom, não temos aqui (ainda) uma receita que é só seguir que vamos ter um projeto sem falhas e sempre ser um sucesso, mas podemos aqui ir lapidando um processo de forma que teremos uma visão geral e que possa ser de grande valia para alcançar os resultados de forma clara e objetiva.

Sabemos que um projeto de ciência de dados visa gerar dinheiro para empresa, que somos capazes de resolver grandes tarefas, mas necessitamos de fazer tudo isso de forma que a solução seja aplicada com qualidade, padrões de ferramentas, processos e metodologias que minimizam o abandono do projeto, e um bom caminho é seguir algumas etapas fundamentais:

- Planejamento
- Escopo e pesquisa
- Experimentação
- Desenvolvimento
- Implantação
- Avaliação de desempenho

<p align="center">
  <img src="https://i.imgur.com/U9iAdrB.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Pelo menos alguns passos devemos seguir, esses ajudam a manter o projeto nos trilhos e aumentam as suas chances de ser implementado
</p>


## Planejamento

Planejar é elaborar o plano, organizar o plano e o planejamento é a preparação para um trabalho, de uma tarefa com estabelecimento de métodos convenientes, de acordo com o dicionário. E não é muito diferente em um projeto de machine learning, na verdade é exatamente o que devemos fazer.

<p align="center">
  <img src="https://i.imgur.com/XMOTHpb.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Antes mesmo de ter algum planejamento a primeira coisa que é feita é ler os dados, um péssimo costume e precisamos corrigir
</p>

E isso entra a questão da comunicação, é comum um projeto começar sem uma boa comunicação do porquê está fazendo o projeto, do que é preciso para executar, quando entregar, enfim, falta um alinhamento de todas as partes interessadas, necessitando assim uma boa orientação do que precisa ser construído, como irá funcionar a solução e qual objetivo das previsões do modelo.

Como venho dizendo, é necessário ter uma boa comunicação principalmente na etapa inicial, onde devemos planejar junto ao time e clientes de todo o processo:
- Dizer como funciona um projeto de ciência de dados para os clientes
- Levantar os pontos de possíveis problemas junto à área cliente
- Entender a fonte dos dados e a sua qualidade
- Perguntar como funciona o processo de negócio atualmente
- Perguntar como eles desejam receber a solução na etapa final
- Planejar e pesquisar sobre como será a experimentação e como será implementado a solução

Com esses pontos é possível entender melhor do que criaremos, principalmente na onde vamos impactar e como vamos impactar, para que seja possível adiantar alguns possíveis problemas até de viabilidade do projeto, se espera o projeto ser executado da forma que se deseja.

Dentro dessa etapa se espera, e é sugerido, criar algumas reuniões para trazer as pessoas chaves para o projeto e discutir como ele será realizado, entre uma dessas reunião é interessante discutir sobre como funciona o projeto de machine learning e as etapas que podem vim a falhar até que seja possível encontrar uma solução que vai funcionar, de forma satisfatória, o problema.

Existe projetos que nascem sem ao menos ter dados os suficientes para que um algoritmo funcione, portanto é sem, é de extrema importância verificar, validar e quantificar se a qualidade dos dados da fonte estão nos conforme que se espera, talvez seja necessário um trabalho anterior com a equipe de engenharia de dados para tratar ou até mesmo iniciar a coleta dos dados.

A comunicação ao decorrer dessas reuniões deve ser claras e diretas, entender como funciona o processo atualmente dará ao time um entendimento maior do negócio e com isso é possível atuar de forma mais assertiva e com isso desenvolver um produto que tenha maior chances de ser um sucesso e, não distante disso, deve-se entender também como será a entrega desse projeto e a data de entrega esperada para que seja possível julgar o que é e o que não é possível fazer.

<p align="center">
  <img src="https://i.imgur.com/dhusvwk.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Um ciclo onde as probabilidades são altas em levar o projeto ao fracasso por motivos de planejamento mal executado, ou até mesmo, não realizado.
</p>

Se nós planejamos e definirmos a nossa experimentação dos algoritmos, será possível focar nas descobertas e talvez encontrar não a melhor solução, mas aquela solução que é boa o suficiente que o projeto seja lançado. 

## Escopo e pesquisa

Uma etapa que não pode ser evadida é a criação do escopo e a pesquisa de soluções, temos aqui um dever em trazer a maior clareza para o projeto, portanto o que se deve ser executado nessa etapa se diz respeito a responder duas perguntas para o cliente, pelo menos, para que posssamos prosseguir com o projeto:

- A solução irá resolver o problema?
- Quanto tempo levará para ser feito?

Na etapa de pesquisa é onde o time faz um brainstorming de possíveis soluções e levanta o risco e tempo de implementação de cada uma, pois assim terá uma visão do todo do projeto. É levantado não somente como outras pessoas resolveram um problema similar ao do projeto, mas também olhar para as soluções propostas em artigos acadêmicos, olhando as teorias!

O time precisa ter uma visão geral de: quais features precisam ser desenvolvidas para satisfazer o projeto, qual processo adicional de ETL será necessário, consenso de todos do time quais dados serão de entrada e de saída do modelo, o que precisa ser otimizado e quais ferramentas serão usadas para facilitar o processo. 

<p align="center">
  <img src="https://i.imgur.com/NoSaPMD.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Um momento que todos nós vamos encontrar, o tempo é dinheiro, e todos vão querer solucionar o problema no menor tempo possível, precisamos ser bem objetivos
</p>

Existem inúmeras bibliotecas de código, ferramentas e frameworks desenvolvidos e aberto ao público, navegando e pesquisando é possível encontrar diversas formas de solucionar o seu problema e com isso pode levar a etapa de pesquisa a ser um grande problema relacionado ao tempo despendido para essa tarefa, por isso é necessário limitar o tempo dessa tarefa, além disso esse tempo limite pode ajudar a não aumentar muito a complexidade da solução sem necessidade.

Como um time, todos devem estar a par da pesquisa para que seja possível fazer uma curadoria e escolher como será feito em diante do projeto, pois foi realizado um trabalho comparando uma parte das possíveis soluções com os possíveis algoritmos, frameworks e ferramentas e todos estão de acordo com os próximos passos.

## Experimentação

Essa etapa é onde levamos um bom tempo e onde está aplicada umas das partes mais científica do projeto, onde aplicamos realmente a metodologia cientifica de experimentação de algoritmos para solucionar os nossos problemas com a entrada de dados da empresa, e contrapartida é um dos maiores casos de falhas de projeto é por causa do tempo muito longo que se leva na fase de experimentação ou desenvolvendo um protótipo que não atinge as expectativas que se deseja. 

É aqui que um projeto de machine learning se diferencia da engenharia de software, é a etapa experimentação é onde colocamos a ciência nos dados, dependendo o projeto será necessário pesquisar mais a fundo sobre o assunto, portanto o time precisa focar em artigos. 

O objetivo da experimentação é produzir uma simulação do produto que permita uma comparação não tendenciosa das soluções consideradas. O foco aqui é balancear entre dois objetivos: velocidade e comparabilidade. 

É comumente utilizado metodologias ágeis para essa etapa, definindo histórias e tarefas, com isso é possível criar um plano de experimentação, algo que também foi desenvolvido lá na primeira etapa de planejamento. Com isso é possível compartilhar com todo o time e com outras áreas e com isso mostrar de forma mais clara as etapas concluídas e os resultados.

<p align="center">
  <img src="https://i.imgur.com/gDnrvtn.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Existe inúmeras possibilidades em uma experimentação, tanto como parâmetros, algoritmos e ferramentas que possamos utilizar e criar um protótipo da solução ineficiente leva a empresa e seus tomadores de decisão a decidir o extremo de cancelar o projeto
</p>

A experimentação tem um ponto importante para ser sempre lembrado, o monitoramento e o salvar dos resultados, parâmetros e dados de cada experimento realizado pelo time. Em cada caso de experimento esse processo é necessário para entender todos os pontos que foram decididos para realizar um experimento, os parâmetros e algoritmos utilizado em cada um, os dados onde o experimento foi executado e os resultados apresentados para fins de comparação e possivelmente a escolha de um algoritmo ideal, com dados ajustados e parâmetros de melhor performance.

## Desenvolvimento

Essa etapa onde é desenvolvido o projeto seguindo todos os padrões de codificação e colocamos toda a confusão de machine learning em um lugar, ter um código com vários pontos de possíveis problemas e muito extenso pode levar o projeto a ter sérios riscos de ser descontinuado.

Como um amigo sempre me disse, devemos desenvolver o código pensando em que a manutenção futura seja de fácil acesso, isso quer dizer que o código/projeto deve ser toda desenvolvida de forma que no futuro a manutenção ou inserção de novos processos sejam de forma sem dor.

<p align="center">
  <img src="https://i.imgur.com/ZlC6eo2.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Um código escrito de forma sem padrão e bagunçado pode levar uma simples tarefa ser grande e complexa, devemos evitar isso nesta etapa de desenvolvimento o máximo possível
</p>

O desenvolvimento de um código limpo é foco total dessa etapa, a modularização e registrar as novas versões em um ambiente em que possibilita esse versionamento é algo fundamental. Com isso devemos desenvolver o projeto onde o impacto de uma mudança em uma etapa do processo não seja motivos de que outra etapa tenha problemas na sua execução.

Portanto, o time deve ser envolvido no desenvolvimento ágil, porém com código limpo, onde eles podem trabalhar juntos de forma eficiente na mesma base de código, minimizando bastante a chance de erros e reduzindo a quantidade de tempo gasto no debugging do código.

## Implantação

Talvez seja uma das etapas mais confusas e complexas que faz parte do projeto de machine learning, o caminho da criação dos modelos e a aplicação das predições dele é bem variado dependendo de como os modelos são usados para as previsões.

<p align="center">
  <img src="https://i.imgur.com/zhilC7X.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
Em cada solução existe uma natureza que devemos seguir para que as predições sejam entregues com eficiência
</p>

Devemos sempre criar a solução que tenha uma estratégia bem clara e econômica para a empresa. As predições realizadas pelo algoritmo treinado devem ser realizadas onde a infraestrutura esteja de acordo com o ambiente onde será colocado, sem faltar ou sobrar infraestrutura pois isso impacta o valor que será cobrado, caso esteja em uma nuvem, ou a infraestrutura local que deve ser construída para suportar a solução.

Em alguns projetos devemos pensar em uma predição realizadas de forma ao vivo, portanto a infraestrutura precisa comportar um número de requisições de acordo com a demanda e em outros casos, as predições são feitas de forma em lotes, um grande volume de dados é a entrada para o algoritmo fazer as predições para cada um dos valores apresentados.

Para cada uma dessas formas de predição é necessário planejar e estruturar as etapas tanto anteriores à predição como também no momento de enviar os resultados, talvez precisa implantar um novo ETL e esse precisa ser executado para cada requisição, é necessário de tempos em tempos o retreinamento do modelo para que seja possível ele aprender com os novos dados e isso é preciso implantar um processo, preciso criar monitoramento das versões dos modelos e a lista continua, por isso é precisamos organizar bem a infraestrutura.

O risco de construir uma solução com engenharia insuficiente - não atende ao acordo de nível de serviço (SLA) ou às necessidades de volume de tráfego, ou é superprojetada - excede as especificações técnicas a um custo inaceitavelmente alto, é alto, devemos pensar nesses intervalos e os riscos financeiros, do time e da empresa associados nesta etapa do projeto.

## Avaliação de desempenho

Se o projeto que utiliza o machine learning que está em desenvolvimento não se prove ser benefico ao negócio, ele terá uma vida curta caso chegue em produção, ou até mesmo não chegue a esse ponto. Para um projeto ter sucesso é necessário que tenha um orçamento de desenvolvimento e que, pelo menos, se pague e gere receita.

Um modelo que esteja sendo criado tem alguns objetivos, um deles é que ele tenha um impacto diretamente ou no aumento da receita ou na diminuição dos custos, com isso leva aos motivos em criar processos para avaliar o desempenho da solução de forma analítica e que isso seja o suficiente para provar o valor do projeto para a empresa.

<p align="center">
  <img src="https://i.imgur.com/AEFEhfT.png" alt="Sublime's custom image"/>
</p>
<p align = "center">
No fim das contas, o projeto deve bater as suas metas, mas sem um design de experimento onde o modelo é comparado em um teste A/B eficaz, as chances de ele ter sucesso serão bem menores
</p>

Não devemos nos esquecer que o objetivo primário de um cientista de dados é resolver um problema de negócio difícil, usando estatísticas, algoritmos e modelos preditivos onde é muito oneroso, monótono ou complexo para um humano resolver. MLOps é aumentar as chances de o projeto ter a eficiência no seu desenvolvimento, facilitando o seu gerenciamento em todo o seu código, eliminando assim as chances do projeto ser abandonado ou cancelado a avaliação do modelo leva o projeto a ser notado e continuado.

# Conclusão

O objetivo primário de um DS é resolver um problema de negócio difícil, usando estatísticas, algoritmos e modelos preditivos onde é muito oneroso, monótono ou complexo para um humano resolver. Engenharia de ML é aumentar as chances de o projeto ter a eficiência no seu desenvolvimento, facilitando o seu gerenciamento em todo o seu código, eliminando assim as chances do projeto ser abandonado ou cancelado. 

Todas essas etapas anteriormente citadas não são escritas em pedra e ao menos podem vir ser o suficientes para o seu cenário, mas devemos sempre ter uma metodologia, e pelo menos um plano, para que o seu projeto tenha o sucesso que você e a sua equipe espera.

### Fontes

Esse artigo escrito por mim teve uma boa ajuda de um excelente livro: Machine Learning Engineering in action, escrito pelo Ben Wilson, vale muito a leitura caso queira adentrar mais neste assunto, pois o autor entra com vários exemplos de sua experiência com mais detalhes.
