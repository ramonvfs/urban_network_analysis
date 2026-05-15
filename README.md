# Análise de Mobilidade Urbana com OSMnx e NetworkX

## Autores
* [Henrique Eduardo Costa da Silva](https://github.com/HenriqueEduardo1)
* [Murilo de Lima Barros](https://github.com/MuriloBarros304)
* [Ramon Vinicius Ferreira de Souza](https://github.com/ramonvfs)

## Identificação da Região Analisada

* **Localidade:** São José de Mipibu, Rio Grande do Norte, Brasil.
* O município localizado na grande Natal possui cerca de 50000 habitantes, foi escolhido por ter 
um tamanho adequado, o que facilita a visualização e o processamento dos dados, além de ser a 
cidade onde residem dois integrantes do grupo.
## Link da Apresentação

* **Vídeo:** [Inserir o link ***DO LOOM DESSA VEZ*** do vídeo de apresentação aqui]

## Objetivo do Trabalho

Para analisar a mobilidade urbana de uma cidade, técnicas usando centralidades em grafos são 
formas matematicamente confiáveis para obter-se insights importantes sobre importância de vias 
e caminhos, por exemplo. O objetivo deste trabalho é apresentar uma análise do fluxo da cidade 
usando grafos, mais especificamente utilizando centralidades, e outros métodos como K-Core, assim 
propondo uma visualização analítica sobre a topologia das vias.

## Metodologia

* **Extração de Dados:** Obtenção do grafo espacial via biblioteca OSMnx utilizando coordenadas 
geográficas/nome do local.
* **Processamento e Estruturação:**
* Uso de grafos direcionados (`MultiDiGraph`) para análises de fluxo com os pesos baseados no 
comprimento das vias.
* Conversão para grafos simples e não direcionados para análises de núcleo (como K-core).


* **Análise Topológica:** Aplicação de algoritmos da biblioteca NetworkX.
* **Visualização:** Geração de mapas de calor no Python (Matplotlib) e exportação do arquivo 
`.graphml` para renderização no Gephi.

## Métricas Calculadas

[tabela]

* **Número de Nós (Interseções):** 1585
* **Número de Arestas (Vias):** 4357
* **Grau Médio:** 5.5
* **Hubs Principais (Top 3 por Grau):** <br>
(1371092853, 8), (1371092880, 8), (1371092882, 8)
* **K-core Máximo:** 2
* **Nós no Núcleo Principal (K-core):** 1376

## Principais Visualizações

[Inserir as imagens geradas pelo notebook ou pelo Gephi. Recomenda-se adicionar legendas 
explicativas para cada mapa]

1. **Grafo Base:** Traçado viário original evidenciando vias de mão dupla e mão única.
* `[Inserir imagem do grafo limpo]`


2. **Distribuição de Grau:** Gráfico (histograma) demonstrando a frequência dos graus na rede.
* `[Inserir gráfico de distribuição]`


3. **Betweenness Centrality (Mapa de Calor):** Visualização das vias que atuam como pontes de 
fluxo.
* `[Inserir mapa de calor do betweenness]`


4. **Closeness Centrality (Mapa de Calor):** Visualização da acessibilidade de cada nó em 
relação ao resto da rede.
* `[Inserir mapa de calor do closeness]`


5. **K-Core / Hubs:** Destaque para o núcleo mais denso da malha viária em contraste com as 
periferias.
* `[Inserir imagem destacando o K-core]`



## Respostas às Questões Obrigatórias

**1. Os nós com maior grau coincidem com os nós de maior betweenness?**
[Inserir resposta. Discutir se os cruzamentos com mais vias conectadas são de fato os mesmos que 
concentram o fluxo da cidade de um lado para o outro, ou se há vias de menor grau que funcionam 
como gargalos obrigatórios.]

**2. O núcleo identificado pelo k-core coincide com os principais hubs?**
[Inserir resposta. Analisar se o 2-core (ou núcleo máximo identificado) engloba os maiores hubs 
ou se deixa algum hub importante de fora por estar em uma região mais periférica/arborescente.]

**3. O que a métrica de betweenness revela que o grau não revela?**
[Inserir resposta. Explicar como o betweenness identifica vias que servem de "ponte" entre 
diferentes bairros ou regiões desconectadas, mesmo que essas vias sejam retas longas com poucos 
cruzamentos (baixo grau).]

**4. O que muda quando a rede é analisada em sua posição geográfica real e quando é analisada 
por um layout estrutural?**
[Inserir resposta. Comparar as coordenadas reais (latitude/longitude do OSMnx) com os layouts 
do Gephi (ex: ForceAtlas2), explicando como o layout estrutural aproxima comunidades altamente 
conectadas, ignorando a distância física real.]

**5. Existem regiões críticas para mobilidade urbana na área analisada?**
[Inserir resposta. Identificar as artérias principais apontadas pelos mapas de calor e discutir 
possíveis pontos de engarrafamento ou vias onde a interrupção causaria colapso no fluxo.]

**6. A rede parece homogênea ou apresenta concentração estrutural?**
[Inserir resposta. Avaliar se o traçado é uma grade simétrica (como cidades planejadas) ou se 
possui centros densos e periferias esparsas.]

**7. Os resultados obtidos fazem sentido considerando o conhecimento urbano da região escolhida?**
[Inserir resposta. Validar os dados matemáticos com a realidade física de São José de Mipibu, 
verificando se as vias com maior betweenness correspondem às rodovias ou avenidas centrais 
conhecidas do município.]

## Principais Conclusões

[Inserir de 2 a 3 parágrafos fechando o raciocínio do trabalho. Sintetizar como as métricas do 
NetworkX ajudaram a revelar a estrutura invisível da cidade e quais foram os achados mais 
surpreendentes sobre a topologia da malha viária analisada.]