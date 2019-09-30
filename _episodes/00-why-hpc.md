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

Using an HPC system often has the following advantages for researchers:

* **Speed.** With many more processing cores, often with higher performance specs,
  than a typical laptop or desktop, HPC systems can offer significant speed up.
* **Volume.** Many HPC systems have both the processing memory (RAM) and disk
  storage to handle very large amounts of data. Terabytes of RAM and
  petabytes of storage are available for research projects.
* **Efficiency.** Many HPC systems operate a pool of resources that are drawn
  on by a many users.  In most cases when the pool is large and diverse enough
  the resources on the system are used almost constantly.
* **Cost.** Bulk purchasing and government funding mean that the cost to the
  research community for using these systems in significantly less that it
  would be otherwise.
* **Convenience.** Maybe your calculations just take a long time to run or are
  otherwise inconvenient to run on your personal computer. There's no need to
  tie up your own computer for hours when you can use someone else's instead.

> ## Thinking ahead
>
> How do you think using a large-scale computing system will be different
> from using your laptop? Talk to your neighbor about some
> differences you may already know about, and some
> differences/difficulties you imagine you may run into.
>
> Summarise your discussion in 2-3 sentances.
> 
> This discussion should take about 5 minutes
{: .challenge}

## On Command Line

Using HPC systems often involves the use of a shell through a command line
interface (CLI) and either specialized software or programming techniques.  The
shell is a program with the special role of having the job of running other
programs rather than doing calculations or similar tasks itself.  What the user
types goes into the shell, which then figures out what commands to run and
orders the computer to execute them.  (Note that the shell is called "the
shell" because it encloses the operating system in order to hide some of its
complexity and make it simpler to interact with.)  The most popular Unix shell
is Bash, the Bourne Again SHell (so-called because it's derived from a shell
written by Stephen Bourne).  Bash is the default shell on most modern
implementations of Unix and in most packages that provide Unix-like tools for
Windows.

Interacting with the shell is done via a command line interface (CLI) on most
HPC systems.  In the earliest days of computers, the only way to interact with
early computers was to rewire them.  From the 1950s to the 1980s most people
used line printers.  These devices only allowed input and output of the
letters, numbers, and punctuation found on a standard keyboard, so programming
languages and software interfaces had to be designed around that constraint and
text-based interfaces were the way to do this.  Typing-based interfaces are
often called a **command-line interface**, or CLI, to distinguish it from a
**graphical user interface**, or GUI, which most people now use.  The heart of
a CLI is a **read-evaluate-print loop**, or REPL: when the user types a command
and then presses the Enter (or Return) key, the computer reads it, executes it,
and prints its output.  The user then types another command, and so on until
the user logs off.

Learning to use Bash or any other shell sometimes feels more like programming
than like using a mouse.  Commands are terse (often only a couple of characters
long), their names are frequently cryptic, and their output is lines of text
rather than something visual like a graph.  However, using a command line
interface can be extremely powerful, and learning how to use one will allow
you to reap the benefits described above.  

> ## You interact with HPC systems through a command line interface
> Most interaction with HPC systems is through a command line interface, usually the
> bash shell.
{: .callout}


## The rest of this lesson

The rest of this lesson will cover the following topics

* We will learn how HPC systems are put together and what this means for you, as an HPC user.
* We will learn how to access a remote HPC system from the bash command line interface and transfer 
  data to and from the remote system.
* We will learn how to use the scheduler on the system to get our calculations up and running on the
  HPC systems.
* We will learn how to access software installed on the HPC system using environment modules.
* We will learn about how parallelism enables larger, faster computation using HPC systems.
* We will learn how we can improve the efficiency of our use of HPC systems.
* We will learn what the future holds for HPC and what this might mean for your use of HPC.

The skills we learn here have other uses beyond just HPC -
Bash and remote connection skills are used everywhere, be it for web development, running software, or operating servers.
It's become so essential that Microsoft
[now ships it as part of Windows](https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6)!
Knowing how to use Bash and HPC systems will allow you to operate virtually any modern device.
With all of this in mind, let's get started!
