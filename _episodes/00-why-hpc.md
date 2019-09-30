---
title: "Por que usar Computação de Alto Desempenho?"
teaching: 20
exercises: 10
start: true
questions:
- "Por que eu deveria me interessar por Computação de Alto Desempenho (HPC)?"
- "O que eu posso esperar aprender com este curso?"
objectives:
- "Estar habilitado a descrever para que sistemas HPC são comumente usados"
- "Identificar como um sistema HPC pode acabar te beneficiando."  
keypoints:
- "Computação de Alto Desempenho (HPC) é uma ferramenta para calcular mais dados e/ou mais rápido do que é possível no teu computador."
- "HPC se baseia na utilização de paralelismo para prover melhorias de desempenho."
- "HPC tipicamente envolve se conectar a enormes sistemas de computação em qualquer lugar pelo mundo."
---

## Por que usar esses computadores?

> ## O que você precisa?  
>
> Fale com um colega sobre sua pesquisa. 
> Como a computação ajuda sua pesquisa? 
> Como mais computação pode te ajudar a fazer mais ou melhores pesquisas?  
>
> Resuma sua conversa em 2-3 frases.
> 
> Essa conversa deve levar em torno de 5 minutos
{: .challenge}

Frequentemente, problemas de pesquisa que usam computação podem tornar o desktop ou laptop insuficientes a partir de diversos pontos:

* Um estudante de estatística deseja realizar uma validação cruzada em seu modelo. Isso envolve executar o modelo 1000 vezes -- mas cada execução leva uma hora. A execução em seu laptop levará mais de um mês!

* Um pesquisador de genômica está usando pequenos conjuntos de dados de dados de sequência, mas em breve receberá um novo tipo de dados de seqüenciamento 10 vezes maior. Já é um desafio abrir os conjuntos de dados em seu computador -- a análise desses conjuntos de dados maiores provavelmente o travará.

* Um engenheiro está usando um pacote de dinâmica de fluidos que tem uma opção para executar em paralelo. Até o momento, ele não usou essa opção em seu desktop, mas, passando de simulações 2D para 3D, o tempo de simulação mais do que triplicou e pode ser útil tirar proveito desse recurso.  

Em todos esses casos, o que é necessário é o acesso a mais computadores que podem ser usados ao mesmo tempo. Felizmente, sistemas de computação em larga escala -- recursos de computação compartilhados com muitos computadores -- estão disponíveis em muitas universidades, laboratórios ou através de redes nacionais. Esses recursos geralmente têm mais processadores, que operam em velocidades mais altas, mais memória, mais armazenamento e conexões mais rápidas com outros sistemas de computador. Eles geralmente são chamados de "clusters", "supercomputadores" ou recursos para "computação de alto desempenho" ou HPC. Nesta lição, geralmente usaremos a terminologia HPC, mas é útil definir esses termos um pouco mais, caso você os encontre no futuro.

* **Computação de Alto Desempenho (HPC).** Recursos de computação que permitem às pessoas resolverem seus problemas mais rapidamente ou tratarem problemas maiores do que seriam capazes usando recursos de computação padrão (por exemplo, laptop, desktop ou workstation). Geralmente implica algum tipo de *computação paralela*.
* **Computação Paralela.** The use of computing resources in parallel to speed up computation or treat larger computational problems.
* **Supercomputador.** Normalmente usado para descrever um recurso HPC muito grande, como os encontrados na lista [Top500](http://www.top500.org). Geralmente, usa a mesma tecnologia que *clusters de computação*, mas em uma escala maior.
* **Clusters de Computação.** Normalmente usado para descrever um recurso HPC menor do que aqueles referidos como *supercomputadores*. Geralmente usa exatamente a mesma tecnologia dos supercomputadores, mas em uma escala menor.
* **_High Throughput Computing_ (HTC).** Um subconjunto da computação paralela em que os recursos de computação são usados em paralelo em muitas subtarefas independentes para aumentar a taxa na qual a computação pode ser executada. Por exemplo, variando um parâmetro de entrada (ou dados de entrada) para um cálculo e executando muitas cópias simultaneamente.
* **Computação em Nuvem.** Usando recursos de computação remota *sob demanda*. Geralmente associado ao uso de recursos públicos de computação em nuvem fornecidos por grandes corporações da Internet.

Todos os tópicos abordados nesta lição serão úteis, independentemente do tipo de recurso que você planeja usar e de que maneira. 

> ## HPC é computação paralela
> Embora os sistemas HPC geralmente tenham processadores um pouco mais poderosos, 
> mais memória e mais armazenamento, o poder adicional real vem do uso dos recursos em paralelo, 
> e não em série.
{: .callout}

O uso de um sistema HPC geralmente oferece as seguintes vantagens para os pesquisadores:

* **Velocidade.** Com muito mais núcleos de processamento, geralmente com especificações de desempenho mais alto, do que um laptop ou desktop típico, os sistemas HPC podem oferecer uma velocidade significativa.
* **Volume.** Muitos sistemas HPC têm memória de processamento (RAM) e armazenamento em disco para lidar com grandes quantidades de dados. Terabytes de RAM e petabytes de armazenamento estão disponíveis para projetos de pesquisa.
* **Eficiência.** Muitos sistemas HPC operam um conjunto de recursos que são atraídos por muitos usuários. Na maioria dos casos, quando o pool é grande e diversificado o suficiente, os recursos no sistema são usados ​​quase constantemente.
* **Custo.** A compra em massa e o financiamento do governo significam que o custo para a comunidade de pesquisa pelo uso desses sistemas é significativamente menor do que seria de outra forma.
* **Conveniência.** Talvez seus cálculos demorem muito tempo para serem executados ou sejam inconvenientes para serem executados no seu computador pessoal. Não há necessidade de amarrar seu próprio computador por horas, quando você pode usar o de outra pessoa.

> ## Pensando no futuro
>
> Como você acha que usar um sistema de computação em larga escala será diferente
> de usar seu laptop? Converse com seu colega sobre algumas
> diferenças que você já conhece, e algumas
> diferenças/dificuldades que você imagina poder encontrar.
>
> Resuma sua conversa em 2 a 3 frases.
>
> Essa discussão deve levar cerca de 5 minutos
{: .challenge}

## Na linha de comando

O uso de sistemas HPC geralmente envolve o uso de um shell por meio de uma interface de linha de comando (CLI) e software especializado ou técnicas de programação. O shell é um programa com o papel especial de executar outros programas, em vez de fazer cálculos ou tarefas semelhantes. O que o usuário digita entra no shell, que descobre quais comandos executar e ordena que o computador os execute. (Observe que o shell é chamado "o shell" porque encerra o sistema operacional para ocultar parte de sua complexidade e facilitar a interação.) O shell Unix mais popular é o Bash, o Bourne Again SHell (o chamado porque é derivado de um shell escrito por Stephen Bourne). O Bash é o shell padrão nas implementações mais modernas do Unix e na maioria dos pacotes que fornecem ferramentas semelhantes ao Unix para Windows.

A interação com o shell é feita por meio de uma interface de linha de comando (CLI) na maioria dos sistemas HPC. Nos primeiros dias dos computadores, a única maneira de interagir com os computadores antigos era reconectá-los. Entre os anos 50 e 80, a maioria das pessoas usava impressoras de linha. Esses dispositivos permitiam apenas a entrada e saída de letras, números e pontuação encontrados em um teclado padrão; portanto, as linguagens de programação e as interfaces de software precisavam ser projetadas com base nas restrições e nas interfaces baseadas em texto. As interfaces baseadas em digitação são frequentemente chamadas de **interface da linha de comandos**, ou CLI, para diferenciá-la de uma **interface gráfica do usuário**, ou GUI, que a maioria das pessoas usa agora. O coração de uma CLI é uma **repetição de leitura-avaliação-impressão** ou REPL: quando o usuário digita um comando e pressiona a tecla Enter (ou Return), o computador lê, executa e imprime sua saída. O usuário digita outro comando e assim sucessivamente até que o usuário efetue logoff.

Aprender a usar o Bash ou qualquer outro shell às vezes parece mais com a programação do que com o mouse. Os comandos são concisos (geralmente com apenas alguns caracteres), seus nomes são frequentemente enigmáticos e sua saída são linhas de texto, em vez de algo visual como um gráfico. No entanto, o uso de uma interface de linha de comando pode ser extremamente poderoso, e aprender a usar uma permitirá que você colha os benefícios descritos acima.

> ## Você interage com sistemas HPC através de uma interface de linha de comando
> A maior parte da interação com os sistemas HPC é por meio de uma interface de linha de comando, geralmente o
> shell bash.
{: .callout}


## O restante desta lição

O restante desta lição abordará os seguintes tópicos

* Aprenderemos como os sistemas HPC são montados e o que isso significa para você, como usuário de HPC.
* Aprenderemos como acessar um sistema HPC remoto a partir da interface da linha de comando do bash e transferir dados de e para o sistema remoto.
* Aprenderemos como usar o agendador no sistema para colocar nossos cálculos em funcionamento nos sistemas HPC.
* Aprenderemos como acessar o software instalado no sistema HPC usando módulos de ambiente.
* Aprenderemos sobre como o paralelismo permite uma computação maior e mais rápida usando sistemas HPC.
* Aprenderemos como podemos melhorar a eficiência do uso de sistemas HPC.
* Aprenderemos o que o futuro reserva para o HPC e o que isso pode significar para o seu uso.

As habilidades que aprendemos aqui têm outros usos além do HPC -
As habilidades com bash e de conexão remota são usadas em todos os lugares, seja para desenvolvimento na web, execução de software ou servidores operacionais.
Tornou-se tão essencial que a Microsoft
[agora o entrega como parte do Windows](https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6)!
Saber como usar os sistemas Bash e HPC permitirá operar praticamente qualquer dispositivo moderno.
Com tudo isso em mente, vamos começar!
