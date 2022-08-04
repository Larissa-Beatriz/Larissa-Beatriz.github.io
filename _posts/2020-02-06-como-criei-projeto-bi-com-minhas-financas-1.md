---
title: Como criei um projeto de Business Intelligence baseado nas minhas finanças pessoais (Parte 1)
layout: post
date: 2020-02-06
image: https://miro.medium.com/max/1400/1*nVov-VtfIQ6vYYqEzWvmRA.jpeg
tags: [sql, business-intelligence, pentaho]
comments: true
description: Desenvolvendo um projeto de Business Intelligence (parte 1).
---

É um bom hábito manter as suas finanças bem organizadas, saber o que comprou, onde comprou, o quanto gastou e quando comprou, seja em uma empresa ou na vida pessoal. E claro, em uma empresa esses dados são gerados em uma maior quantidade do que compras/vendas vida pessoal, claro que depende de como você gasta 😊!
Nessa visão, eu desenvolvi um sistema onde eu poderia armazenar informações, que eu acho interessante para o **meu caso**, e assim eu estaria apto a analisar como anda a minha saúde financeira.
Aproveitando esse desejo aliei com a minha vontade de aprender e melhorar minhas habilidades profissionais no âmbito de Business Intelligence (BI), onde vou desenvolver os quesitos de banco de dados com o desenvolvimento de um Data Warehouse (DW), a integração dos dados (ETL) com o desenvolvimento de um fluxo de dados ligado às necessidades, a visualização de dados com o desenvolvimento de dashboards e relatórios e a análise desses dados. E tudo isso vou detalhar melhor ao decorrer do texto.

# **Mas afinal, o que é Business Intelligence?**
Ao decorrer do tempo, cada vez mais, se faz necessário avaliar e analisar dados com o intuito de ajudar na previsão de alguma coisa e suportar na tomada de decisão, e com os dados é possível criar visões com perspectivas diferentes. Com um sistema bem organizado, é possível tomar decisões mais certeiras com dados para dar suporte, tirando um pouco daquele clássico caso de tomar decisão somente por feeling, mas claro, isso também ajuda na tomada de decisão.
Com isso, hipoteticamente aqui falando, se todo mês de Junho eu tenho um aumento nos meus gastos com Bebidas eu consigo avaliar e analisar o motivo e com isso tomar alguma decisão para equilibrar esses gastos, por exemplo, não gastar em alguma outra área, verificar qual produto eu estou gastando mais e diminuir a compra e até aumentar a minha renda nesse tempo. Assim possuir dados do passado é importante para prever futuras decisões.
Portanto, Business Intelligence é todo o processo de coletar, estruturar, analisar, compartilhar e monitorar informações para a tomada de decisão. Isso em conjunto e utilizando tecnologia é possível transformar dados brutos em informações, sendo essas informações úteis para a tomada de decisão, e sendo útil é possível criar estratégias assertivas.
Resumindo um pouco, o BI pode ser dividido em estágios, sendo eles:
- Coleta de Dados
- Limpeza e transformação dos dados
- Análises
- Relatórios/Dashboards

Existe ainda o estágio de implementação do BI que é usar as tecnologias das ferramentas que estão disponíveis no mercado, sendo elas de processamento de dados e visualização dos dados. Portanto, é possível diferentes ferramentas formarem uma infraestrutura de BI, mas o mais comum é ter ferramentas de: armazenamento, processamento de dados e visualização.

# **E como o BI pode me ajudar nas finanças?**
Com os processos descrito acima, o BI me ajudará a responder perguntas bastante pertinentes e me ajudar a automatizar processos nos quais levam bastante tempo, como criar planilhas por exemplo.
Os dados organizados em um banco de dados analítico me permitem resolver algumas questões que são comuns no dia-a-dia e me ajuda a tomar melhores decisões sobre os meus gastos pessoais, identificando pontos importantes para monitorar, analisar e decidir sobre o que seja necessário intervenção.
Mas o que me ajudará a realmente nas minhas finanças? No BI os relatórios e/ou dashboards se encarrega a me ajudar, com os indicadores de performance, KPI’s, me indica onde devo prestar atenção e focar minhas ações naquele quesito. Mas antes de chegar lá, tem um longo caminho.
Então espero que com BI me ajude a fazer avaliações sobre para onde o dinheiro está indo, como está indo, o quanto está indo e quando está indo. O BI me permite fazer essas observações pois é possível comparar os resultados em diferentes perspectivas, com o cubo OLAP que mais a frente irei explicar melhor, me ajudará nesse quesito. E claro, diminuindo bastante tempo naquele processo tedioso de ficar criando planilhas e focando essencialmente na análise das finanças.

# **E como eu comecei o projeto?**
Bom, primeiramente foi necessário ter alguma origem dos dados, assim existe um sistema no qual é inserido os dados sobre as compras e armazenado em um banco de dados. Esse sistema simplesmente faz isso, é bastante simples, eu o desenvolvi como forma de aprendizado, portanto meu foco não era ser o mais bonito e alta performance, mas sim funcional.
Como disse, o sistema armazena os dados no banco de dados, mas quais são esses dados? Como o foco é finanças pessoais preciso saber quais produtos foram comprados, onde foram comprados, quantidade comprada, quanto foi valor unitário e o valor total do produto, quando foi feito a compra e qual foi a forma de pagamento da compra. Assim temos o seguinte:
Os produtos têm o seguinte formato:
- sua categoria;
- sua subcategoria;
- sua marca;
- seu nome.
  
O local de compra é formado por:
- o tipo do estabelecimento da compra;
- a cidade;
- o bairro;
- o endereço completo;
- o nome do local da compra.
  
Assim temos o seguinte, a compra é formada por: produto, o local de compra, a forma de pagamento, a quantidade comprada, valor unitário e o valor total. Com isso, os dados são inseridos no banco de dados.

![alt text](https://miro.medium.com/max/700/1*j8S-jrYReXezSluIgB13Fw.png)

Portanto tendo o entendimento do funcionamento do sistema de origem dos dados e conhecer essas regras de negócios podemos assim prosseguir com o projeto, começando com o primeiro passo: o levantamento de requisitos.

# **Passo 1: Levantamento dos requisitos**
Os requisitos são praticamente algumas perguntas que devemos responder com o projeto de BI, com elas tomamos como norte o que devemos fazer para chegar no objetivo, que é trazer informações acerca dos dados.
Aqui vou mostrar somente um requisito, para não alongar demais essa parte do texto.
O requisito é: Como estão as compras realizadas. O intuito desse requisito é verificar como estão a evolução das compras realizadas, analisando pelo dia, pelo produto, pelo local de compra e forma de pagamento.
A primeira coisa a se saber é se já existe alguma forma que essa pergunta é respondida atualmente, para assim verificar como o cliente costuma visualizar essa informação. O caso aqui é criação, não existe nenhuma forma já existente, iremos criar mais para frente.
Na sequência precisamos validar se os dados para responder essa pergunta existem, onde está e quem tem acesso para disponibilizar para usá-los no processo. No nosso caso temos sim os dados, que são as tabelas de origem já carregadas com dados. O acesso será disponibilizado por meio de uma conexão do banco de dados PostgreSQL.
Agora devemos pensar como deve ser a visualização desse requisito onde iremos visualizar a evolução de acordo com o requisito. Também podemos pensar nos filtros que serão implementados na visualização e a sua hierarquia. Uma possibilidade é que essa visualização possa haver algum detalhamento, o Drill, também devemos considerar.
Para o nosso caso, foi pensando o seguinte. Para as visualizações como se trata de uma evolução podemos pensar em gráfico de barras ou de linhas. Para os filtros serão os de data e a forma de pagamento que irão filtrar todos os gráficos, sendo a hierarquia de data o ano, semestre, mês e dia e não haverá drill nessa tela. A proposta de visualização dessa tela é a imagem abaixo:

![alt text](https://miro.medium.com/max/700/1*DROG1ZNQsaHi4BpqLR3VhA.png)

E como se trata de uma proposta, podemos mais a frente pensar em melhorias nessa tela no futuro, principalmente o design da tela, como cores e imagens.

# **Passo 2: desenho do Data Warehouse**
A origem dos dados foi criada no sistema transacional e em dados normalizados, focado na entrada e saída de pequenos lotes de dados, que esses dados sejam consistentes, baseado no CRUD (sigla para criação, leitura, atualização e deleção) eliminando assim a redundância dos dados.
Aqui não vou entrar nos detalhes sobre a diferença entre esses dois modelos de banco de dados, pois existe muito material onde possa consultar e entender melhor.
Como o banco de dados transacional é utilizado dessa forma se faz necessário a criação de outro banco de dados que funcionará de forma analítica e que ocorra a desnormalização dos dados para melhorar o desempenho e focado em consultas em grandes volumes de dados.
Portanto o DW tem objetivos, sendo alguns dele: otimizar o processo de consultas e análises dos dados, tempo de resposta otimizado, os dados armazenados no DW devem ser de fácil interpretação e o DW é desenhado com base no negócio para a tomada de decisão.
Vamos decidir alguns processos antes de modelar o nosso DW. Primeiramente vamos seguir o modelo do banco de dados definido como star schema (modelo estrela), tem esse nome pela forma que o desenho se parece com uma estrela, o modelo estrela é uma metodologia de modelagem de dados muito usado em DW, se caracteriza por ter dados redundantes com o intuito de aumentar a performance das consultas nas tabelas, essas tabelas são chamadas de dimensões que são ligadas diretamente na fato.
Seguindo as boas práticas iremos definir nomenclaturas para diferencias as tabelas do DW e os campos que compõe essas tabelas. As tabelas dimensões serão formadas por um prefixo anterior ao nome que indica qual área faz referência, sendo o prefixo DIM_NOME_DA_TABELA e seguindo essa definição a tabela fato tem o prefixo FT_NOME_DA_TABELA.
Para a nomenclatura dos nomes dos campos será a seguinte, para os campos chaves das tabelas dimensões: SK_NOME_DO_CAMPO, para os campos chaves do sistema de origem: NK_NOME_DO_CAMPO, para os campos com nome: NM_NOME_DO_CAMPO, para valores monetários: VL_NOME_DO_CAMPO, para quantidade: QTD_NOME_DO_CAMPO e para datas: DT_NOME_DO_CAMPO.
Para o nosso DW foi levantando que vamos ter quatro dimensões, sendo elas a de Tempo, Forma de Pagamento, Produto e Local de Compra. E para armazena o fato acontecido teremos uma tabela fato, a Compras.
Existe outros conceitos que devemos nos preocupar no desenho de um DW, como por exemplo, o SCD (Slowly Changing Dimensions) onde diz que uma dimensão pode haver alterações nos seus registros ao decorrer do tempo e se faz necessário a atualização, a tipagem dos dados como o campo será criado fisicamente no banco de dados. Esses procedimentos já foram decididos e implementados, no caso SCD será mais bem explicado no processo de carga das tabelas.

Com isso dito, o desenho do nosso DW ficou o seguinte:

![alt text](https://miro.medium.com/max/580/1*OyrWKDkwf_KC7sEyGZOegA.png)

O nosso DW está criado logicamente e fisicamente no banco de dados e agora é preciso agora carregar as tabelas com os dados relevantes para a análise das finanças pessoais, isso o ETL se encarregará que é exatamente o nosso próximo passo.
O restante dos nossos passos virão na próxima parte, até lá :)