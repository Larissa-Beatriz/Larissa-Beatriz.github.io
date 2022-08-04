---
name: Recomendador de Imóveis
tools: [python, outsystems]
image: https://i.imgur.com/nuWHnUm.jpg
description: Algoritmo de machine learning aplicado em um sistema de recomendação de imóvel
---

Algum tempo atrás minha família estava procurando um imóvel para comprar, sendo assim procuramos um corretor de imóvel para me auxiliar nesse processo, não era comum procura imóveis por meio da internet, o que hoje é um ponto inicial de procura, lembrando disso me veio a vontade de criar um projeto de Machine Learning para me recomendar algum imóvel que seja do meu gosto.

Então vamos lá, o que eu desenvolvi para me ajudar nessa tarefa? Usei o Scrapy para eu consiga automatizar o processo de extração dos dados da web, ele me auxilia em criar processo para que seja possível ter um banco de dados para o processo de Machine Learning. Criei um aplicativo web com OutSystems no qual ele tenha acesso a esses dados e assim eu consiga analisar cada imóvel e colocar a decisão, se eu compraria ou não, e, por fim, um aplicativo web no qual me mostra quais são os imóveis mais compatíveis com o meu gosto, de acordo com o modelo de machine learning. 

PS: o webapp aqui mostrado não coloquei os links para os imóveis, para evitar maiores problemas por causa do scraping.

Assim temos os seguintes passos: 

- Extrair dados da web com Scrapy; 
- Criar os apps no OutSystems; 
- Criar o modelo de ML; 
- Desenvolver webapp para consumo do modelo de machine learning;

Vendo assim até parece que são poucos passos, mas isso demandou bastante tempo e empenho na construção. E claro, tem inúmeras formas de ter feito, esse foi o meu caminho que trilhei.

**Extração dos dados**

Para que seja possível treinar um modelo de machine learning é necessário dados para ele aprender, portanto iremos fazer o Scrapy para que seja possível continuar o processo. É extremamente importante fazer esse processo de forma responsável, já que iremos fazer várias requisições para um website, caso você também venha a fazer um scraping, use de forma responsável, dependendo da onde o website esteja hospedado o servidor não aguentará o número de requisições que irá ser feito. 

Falado isso, eu escolhi alguns websites onde eu encontro vários imóveis e com isso conseguir dados reais de imóveis da minha cidade, Uberlândia, nele eu consigo informações relevantes de um imóvel por exemplo, área em metros quadrados, quantidade de banheiros, quantidade de garagem, quantidade de quartos, o bairro e, claro, o preço de venda do imóvel. 

Com o Scrapy eu consigo extrair todas essas informações do site e com ele posso salvar essas informações em um banco de dados, aqui eu escolhi o SQLite, mas poderia ser um banco em cloud para que possamos criar processos automatizados que tempos em tempos extraia esses dados e guarde nesse banco, mas por enquanto irei usar essa forma mais simples. 

Tive alguns problemas com um website, ele é mais complexo do que eu tenho conhecimento sobre o Scrapy, assim eu tive que “apelar” em alguns momentos, talvez isso tenha impacto negativo na performance e nas boas práticas, mas até então, está funcionando tudo ok. 

Assim criei meu Spider para esse site, onde é extraído os dados que eu necessito. Eu tenho duas funções, uma na qual eu faço um loop sobre a quantidade de páginas que eu quero fazer o scraping e a outra função é a que faz a extração dos dados que preciso. 

Com esses dados extraídos, agora é a hora de armazenar eles, portanto foi feito um pipeline onde é possível criar uma conexão com o banco SQLite, criar a tabela onde os dados serão armazenados e assim os dados são inseridos com o que foi retornado da página. Bem simples, o pouco que eu li sobre, é possível criar processos muito complexos, ao passar do tempo e com estudos eu irei melhorar esse processo. 

No final desse processo temos um banco de dados com os dados organizados em forma de tabela, é possível criar processos de data cleaning com o scrapy, mas decidi fazer isso de forma separada. 

**Sistema de apoio à decisão dos dados**

Como o projeto é um sistema de recomendação de imóveis é necessário criar os labels para cada imóvel, para que o algoritmo aprenda sobre o meu gosto e me recomende imóveis de acordo com o meu perfil. Para fazer esse processo eu desenvolvi um WebApp usando OutSystems.  

OutSystems é uma plataforma de low-code, resumindo, é possível criar aplicações somente clicando e arrastando, o que me ajuda bastante, já que não tenho muito conhecimento em desenvolvimento web e com isso permite focar em data science.

![alt text](https://i.imgur.com/LvdmRkV.gif)

**Machine Learning em ação**

Para esse problema, que é de classificação, foi testado alguns algoritmos de machine learning para escolher o melhor que se saem com os dados, spoiler aqui, eu escolhi o algoritmo CatBoostClassifier. Para ver todo o processo e os pacotes que desenvolvi, entre no notebook no meu GitHub.

[Clique aqui](https://github.com/mathdeoliveira/house-recommendation/blob/master/analysis/entire_process.ipynb)

**Deploy**

Para o deploy foi utilizado o Streamlit desenvolvido em Python onde é possível criar um webapp para consumir o modelo de machine learning utilizando os dados extraídos por meio de scraping e carregados no AWS, a imagem abaixo é mostrado a estrutura do projeto.

Para o aplicativo ficar on-line, criei o banco de dados MySQL e uma instância de uma máquina ECS na Amazon Web Services (AWS).

![alt text](https://i.imgur.com/FEV3fXA.png)

E no final, temos o nosso webapp rodando na internet, para acessar o aplicativo é necessário a execução do todo processo para a máquina na AWS ficar on-line.

**Considerações finais**
Gostaria de pedir a você comente o que achou da solução criada por mim, e caso tenha alguma crítica ou sugestão fique a vontade em entra em contato comigo. Aproveito também para pedir para você me seguir nas redes sociais: