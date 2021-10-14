# Aplicacao_de_Machine_Learning_para_Apoio_a_Selecao_de_Lideres_em_Uma_Empresa_de_Grande_Porte

#### Alunos: Alessandro Melgaço Barbosa Filho eBeatriz Ventorini Lins de Albuquerque.
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler)

---

Trabalho apresentado ao curso BI MASTER como pré-requisito para conclusão de curso e obtenção de crédito na disciplina [Projetos de Sistemas Inteligentes de
Apoio à Decisão](https://ica.puc-rio.ai/es/bi-master-es/)

---

### Resumo

O objetivo deste trabalho foi explorar possibilidades de aplicação de ferramentas de machine learning para apoiar o processo de seleção de líderes em uma empresa
de grande porte.
A área cliente, demandante deste estudo, é responsável pela seleção de empregados para ocupar posições de liderança em diferentes níveis hierárquicos e
diferentes áreas da empresa.
Por se tratar de uma empresa com milhares de empregados, e que possui diversos registros relativos à sua atuação, há uma grande quantidade de dados
disponíveis. A área cliente solicitou apoio para explorar esses dados e gerar informação e conhecimento que possam apoiar o processo de identificação,
recrutamento e seleção dos possíveis candidatos.
Os dados dos empregados incluem: resultados de avaliações realizadas por uma empresa externa especializada em seleção de executivos, resultados de avaliação
de desempenho e competências, histórico de experiências gerenciais, dados do perfil profissional (cargo, função, ênfase de atuação), dados demográficos (gênero,
idade, cidade de atuação) e outros.
Neste trabalho, foram aplicados métodos de tratamento dos dados, clusterização, classificação e redução de dimensionalidade. As ferramentas utilizadas foram um
Jupyter Notebook (Python), e o Rapid Miner. Todos os resultados foram apresentados no notebook.

### 1. Introdução

A empresa que cedeu os dados para este trabalho possui milhares de empregados e realiza, periodicamente e também em casos pontuais, processos internos de
seleção de líderes. Em alguns casos, os empregados se candidatam às vagas divulgadas, mas em outros casos, a empresa busca ativamente os candidatos
possivelmente mais adequados a determinadas vagas, e também realiza ações de orientação de carreira para os empregados interessados. Em função da grande
quantidade de possíveis candidatos, a empresa tem investido, cada vez mais, em melhorar seus processos internos de recrutamento e seleção, com o objetivo de
encontrar e desenvolver os talentos mais adequados para as posições, incluindo possíveis talentos escondidos ou desconhecidos.
A equipe de recrutamento e seleção de lideranças, que faz parte da área de Recursos Humanos da empresa, é a responsável por esses processos, e é a cliente deste
trabalho. Antes de conceder acesso aos dados disponíveis, que são confidenciais, a equipe cliente participou de uma reunião com os autores do trabalho e seus
respectivos gerentes, para alinhamento das necessidades, dos objetivos, das possibilidades e das restrições do trabalho. Devido à grande quantidade de dados
disponíveis, a cliente solicitou apoio para explorar esses dados e gerar informação e conhecimento que possam apoiar o processo de identificação, recrutamento e
seleção dos possíveis candidatos.
A equipe cliente forneceu para este trabalho diversos arquivos contendo registros relativos à atuação dos empregados, que incluem: resultados de avaliações
realizadas por uma empresa externa especializada em seleção de executivos, resultados de avaliação de desempenho e competências, histórico de experiências
gerenciais, dados do perfil profissional (cargo, função, ênfase de atuação), dados demográficos (gênero, idade, cidade de atuação) e outros.
Além dos objetivos principais, que são identificar os candidatos mais adequados a cada posição-alvo e explorar melhor os dados de perfil dos potenciais candidatos,
as necessidades da equipe cliente incluem: identificar talentos escondidos, obter subsídios para oferecer orientação de carreira aos empregados, direcionar ações de
desenvolvimento para essa evolução na carreira, sugerir mobilidade para outras áreas baseado no perfil dos empregados, identificar quais são os atributos mais
significativos para a seleção dos candidatos e priorizar esses atributos em futuras avaliações de candidatos.
Ao longo do trabalho, foram aplicadas ferramentas para tratamento dos dados, métodos de exploração, clusterização, classificação e redução de dimensionalidade,
que serão apresentadas e comentadas no notebook Jupiter, que está disponível neste mesmo repositório.

### 2. Modelagem

  - Pré-processamento: Antes de iniciar a análise exploratória, foi necessário consolidar e tratar os dados disponíveis, pois vieram de diferentes fontes e não estavam
unificados nem padronizados.
Foram realizados os seguintes passos: tratamento de valores faltantes, agregação de valores de alguns atributos categóricos que possuíam muitos valores
presentes (idade, ênfase), remoção de alguns atributos, agrupamento de alguns atributos em subdivisões para apoiar as análises, tratamento de outliers.
Após o tratamento, foi gerado um dataset unificado que também foi exportado para ser utilizado nos processos que seriam construídos no Rapid Miner.
  - Descrição dos atributos: A descrição detalhada dos atributos está no arquivo "Dicionário de Atributos.pdf", disponibilizado neste repositório.

### 3. Resultados

Na análise exploratória foram considerados alguns agrupamentos categóricos: estado (UF), sexo, Diretoria, func (função gerencial), escolaridadeCargo (escolaridade
comprovada para contratação), escolaridadeMax (nível atual de escolaridade), ênfase (área especializada de atuação na empresa). Foi identificado
desbalanceamento de dados em relação a alguns agrupamentos (por exemplo, algumas categorias do atributo estado).

Foram identificadas pequenas variações nos dados para homens e mulheres (atributo sexo), e algumas variações importantes nos grupos do atributo Diretoria, func,
escolaridade e idade.
Foram analisadas as correlações entre os atributos, demonstrando que algumas subdivisões (competências Petrobras) possuíam forte correlação com outros
atributos, acrescentando pouco ao resultado final.
Por meio da redução de dimensionalidade, buscou-se identificar os atributos mais significativos, para simplificar o modelo de dados do cliente e tornar mais
eficiente e confiável a interpretação dos dados durante os processos de seleção de líderes.
Na clusterização, foi possível identificar, por exemplo, que: o atributo gênero possui baixa influência; há maior incidência nas áreas de negócio da empresa e nas
ênfases mais associadas a essas áreas; os atributos escolaridade, função e idade têm relação direta; o atributo aderência tem relação direta.
Foi aplicado um modelo de classificação com o objetivo de estimar a função gerencial a partir dos 6 atributos da subdivisão Motivadores. Esse e outros resultados
estão detalhados no notebook.

### 4. Conclusões

A área cliente havia solicitado apoio para tratar, consolidar, explorar e analisar os dados disponíveis, com o objetivo de fortalecer os processos de seleção de líderes.
Antes da realização deste trabalho, o apoio oferecido havia sido centralizado na construção de um painel de business intelligence, com filtros para navegar pelos
dados disponíveis e preparar listas de possíveis candidatos; porém, todo o trabalho de escolha dos filtros, definição dos critérios, identificação de agrupamentos e
outras ações ainda precisava ser feito pela equipe cliente.
Agora, com a realização deste trabalho, a aplicação das ferramentas e dos modelos utilizados possibilitou oferecer um apoio diferenciado à área cliente, mostrando
novos caminhos, diferentes possibilidades e muitos insights.
Os próximos passos serão: apresentar o resultado à área cliente; explicar e demonstrar como as novas informações disponíveis poderão ser exploradas, de
diferentes formas, e apoiar essa exploração; aprofundar algumas análises ou testar outros modelos, de acordo com os novos insights que surgirão a partir dessa
exploração pela área cliente; desenvolver um novo painel de business intelligence para que a área possa explorar com mais autonomia esse novo conjunto de
informações.

---

Matrícula: 192.671.011 e 192.671.019

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação Business Intelligence Master

