# NotebookLM

Tema: Engenharia de IA


Objetivo: Aprender e compreender conceitos de Engenharia de IA.

Fontes:
HUYEN, Chip. Engenharia de IA: construindo aplicações com modelos de fundação. O'Reilly Media, 2025.



Pergutas e Respostas:

Quais principais diferenças de LLM e SLM ?


Embora o acrônimo SLM (Small Language Models) não seja mencionado diretamente nas fontes fornecidas — sendo esta uma informação externa que você pode querer verificar de forma independente —, os textos comparam extensivamente os grandes modelos de linguagem (LLMs) com modelos menores (que correspondem ao conceito de SLM). As principais diferenças entre eles baseiam-se em quatro eixos centrais:
1. Tamanho e Definição O tamanho de um modelo de linguagem é quantificado pelo seu número de parâmetros, que são as variáveis atualizadas durante o processo de treinamento
. É importante notar que "LLM" não é um termo científico fixo: o que é considerado "grande" muda com a evolução da tecnologia
. Por exemplo, um modelo de 117 milhões de parâmetros era considerado grande em 2018, enquanto hoje o padrão para LLMs costuma estar na casa dos 100 bilhões de parâmetros
2. Custos, Memória e Velocidade (Inferência)
LLMs: O treinamento de grandes modelos exige dados em escala de trilhões de tokens, poder computacional massivo e talentos altamente especializados, criando uma barreira de entrada que apenas grandes corporações podem pagar
. Além disso, executar esses modelos gera alta latência e altos custos operacionais devido à enorme quantidade de memória exigida para abrigar seus parâmetros
Modelos menores: Exigem consideravelmente menos memória, o que os torna mais fáceis de ajustar, mais baratos e mais rápidos de usar em produção
. Por terem um custo de inferência muito menor, a adoção de modelos menores frequentemente melhora a usabilidade de um aplicativo e facilita a execução local em dispositivos
3. Generalização vs. Especialização de Tarefas
LLMs: Graças à sua escala, eles operam como modelos de uso geral (foundation models). Um único LLM "pronto para uso" pode apresentar bom desempenho em uma vasta variedade de tarefas (como tradução, codificação, análise de sentimentos e matemática) sem a necessidade de treinamento adicional
Modelos menores: Têm menor capacidade de conhecimento geral, mas compensam pela especialização. Um modelo pequeno e ajustado com precisão (finetuning) em um conjunto de dados de alta qualidade pode superar o desempenho de LLMs muito maiores em tarefas específicas
. Em um exemplo citado nas fontes, um modelo ajustado que era 60 vezes menor superou uma variante do GPT-3 na tarefa de edição de texto
4. Técnicas de Treinamento (Destilação de Modelos) Para compensar a diferença de capacidade geral sem perder os benefícios de custo, é muito comum aplicar uma técnica chamada destilação de modelos aos modelos menores
. Nessa técnica, os dados gerados por um LLM grande (o "professor") são usados para treinar um modelo pequeno (o "aluno"), fazendo com que o modelo menor aprenda a imitar os comportamentos e a performance do modelo maior, mas operando com uma fração do seu tamanho origina

Qual principal foco do RAG ?


O principal foco da técnica de RAG (Geração Aumentada por Recuperação) é construir um contexto específico e relevante para cada consulta feita a um modelo de inteligência artificial
. Inicialmente, seu objetivo central surgiu como uma solução para superar as limitações de tamanho de contexto dos modelos básicos, já que não é viável inserir todo o conhecimento do mundo diretamente no prompt de uma só vez
Na prática, o foco do RAG se concentra nos seguintes pilares:
Fornecimento de conhecimento externo (foco nos fatos): Enquanto técnicas como o ajuste fino servem para moldar o comportamento e o formato das respostas de um modelo, o RAG é focado em fornecer fatos
. Ele permite que o modelo recupere dados de fontes de memória externas (como bancos de dados internos, sessões de bate-papo anteriores ou a Internet) para complementar o seu conhecimento
Aumento da precisão e redução de alucinações: Os modelos de IA têm maior probabilidade de cometer erros ou inventar respostas (alucinar) quando lhes falta informação
. O foco do RAG em fornecer acesso a documentos relevantes ajuda o sistema a gerar respostas mais detalhadas, precisas, informativas e com base na realidade
Eficiência e desempenho no uso do contexto: Mesmo com modelos que suportam contextos enormes, jogar informações em excesso pode confundir a IA e aumentar o custo computacional
. O RAG foca em recuperar apenas a informação mais pertinente para a pergunta do usuário, reduzindo o número de tokens de entrada e aumentando a eficácia do processamento do modelo
Gerenciamento de dados dinâmicos e privados: O RAG é focado em lidar com informações que mudam frequentemente ou que são específicas de um usuário (como os dados de uma empresa que não poderiam estar nos dados de treinamento originais do modelo)
. Ele também se adapta perfeitamente a dados tabulares e multimodais (como imagens e textos combinados) de bancos de dados da empresa
