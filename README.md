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


Miniguia de engenharia em AI


A engenharia de IA consolidou-se como o processo de criação de aplicativos com base em modelos básicos (foundation models) já prontos e amplamente disponíveis, diminuindo drasticamente a barreira de entrada da área
. Diferente da engenharia de Machine Learning (ML) tradicional — que exige alto investimento para treinar modelos do zero focados em tarefas limitadas —, a engenharia de IA concentra-se muito mais na adaptação e avaliação de modelos abertos e de uso geral
.
Para ajudar a estruturar seus projetos, aqui está um miniguia abordando os pilares fundamentais da engenharia de IA:
1. A Pilha de Engenharia de IA (The AI Stack)
A criação de aplicações de IA pode ser dividida em três camadas principais:
Desenvolvimento de aplicativos: Focado na interface do usuário, engenharia de prompt e avaliação rigorosa do sistema
Desenvolvimento de modelos: Engloba a engenharia de conjunto de dados, técnicas de ajuste (como finetuning e RAG) e a otimização da inferência
Infraestrutura: Ferramentas para servir os modelos, gerenciar os dados, recursos computacionais e monitorar ativamente a produção
2. Técnicas Fundamentais de Adaptação de Modelos
A evolução típica de um aplicativo geralmente começa com a técnica mais barata e passa para as mais complexas, conforme as limitações do modelo aparecem
Engenharia de Prompt: É a técnica mais fácil e não altera os pesos do modelo
. Para resultados eficazes, escreva instruções claras, forneça exemplos (aprendizado in-context/few-shot) e divida tarefas complexas em subtarefas encadeadas menores
. Outra técnica poderosa é a Cadeia de Pensamento (Chain-of-Thought - CoT), que incentiva o modelo a pensar "passo a passo" ou usar a autocrítica antes de dar a resposta final
RAG (Geração Aumentada por Recuperação): Se o modelo sofre com a falta de informações, respostas desatualizadas ou alucinações, o RAG soluciona o problema dando ao modelo acesso a fontes de conhecimento externo (como bancos de dados ou a Internet) no momento da consulta
. A eficácia do RAG depende crucialmente do algoritmo de recuperação (ex: baseado em termos como o BM25 ou pesquisa de vetores de embeddings)
Agentes e Uso de Ferramentas: Para interagir com o mundo ou realizar ações complexas de várias etapas, você pode construir Agentes. Um agente de IA tem capacidade de percepção do ambiente, planejamento autônomo (decomposição de tarefas) e execução, podendo evocar ferramentas como APIs, calculadoras, interpretadores de código e executores SQL
Ajuste Fino (Finetuning): Se o RAG resolve a falta de "fatos", o ajuste fino ajuda na "forma" (estilo, tom ou sintaxe específica, como gerar um JSON estrito ou código para um dialeto SQL de nicho)
. O ajuste fino atualiza os pesos do modelo original
. Para evitar os enormes custos e gargalos de memória do ajuste fino completo, o padrão da indústria é usar PEFT (Ajuste Fino Eficiente de Parâmetros), sendo o LoRA a técnica mais popular, pois ela injeta pequenas matrizes adicionais treináveis sem alterar a pesada matriz de peso original
3. Desenvolvimento Orientado por Avaliação
Talvez o maior obstáculo para colocar IA em produção não seja o desenvolvimento, mas saber se o aplicativo está funcionando
. Por isso, o desenvolvimento deve ser orientado por avaliação.
Defina critérios claros: Antes de construir o app, estabeleça métricas como correção funcional, toxicidade, consistência factual ou capacidade de seguir instruções
IA como Juiz (LLM-as-a-judge): Como os resultados da IA são gerativos, abertos e com múltiplas respostas corretas possíveis, métricas exatas são difíceis de aplicar
. Usar um LLM avançado para julgar e pontuar os resultados da própria IA em critérios específicos (ou comparando qual resposta é a melhor) tornou-se a técnica de avaliação automática padrão e flexível na indústria
4. Otimização de Inferência (Custo e Velocidade)
Não importa a qualidade de um modelo, se ele for lento ou muito caro, será inútil em produção
. A latência é geralmente dividida em TTFT (Tempo até o Primeiro Token) e TPOT (Tempo por Token de Saída)
. As principais otimizações incluem:
Quantização: Reduzir a precisão numérica de um modelo (por exemplo, de 32 bits para 8, 4 ou até 1 bit), reduzindo drasticamente o uso de memória e a largura de banda, acelerando a inferência, embora correndo pequenos riscos de degradação da qualidade
Loteamento Contínuo (Continuous Batching): Para os servidores, processar múltiplas requisições em lote dilui o custo; o loteamento contínuo permite devolver as requisições aos usuários no exato momento em que ficam prontas e aceitar novas, sem esperar que o lote inteiro termine
Gestão de Caches (Prompt e KV): Modelos autorregressivos precisam recalcular contextos o tempo todo. Otimizar o Cache KV do mecanismo de atenção reduz gargalos computacionais. Igualmente, usar o Cache de Prompt poupa o modelo de reprocessar instruções enormes (como o prompt de sistema ou grandes documentos contextuais) a cada nova interação do usuário, diminuindo a latência e o custo
5. Dados
A visão atual da engenharia foca na "IA centrada em dados", onde a melhoria do modelo vem de dados de altíssima qualidade, relevância e diversidade, e não apenas de sua arquitetura
. Um processo revolucionário na área é a Síntese de Dados: usar modelos mais fortes para simular e gerar em larga escala novos dados sintéticos, instruções, códigos e anotações para treinar ou destilar modelos menores ou refinar seu próprio comportamento
