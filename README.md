### Linuxtips
# Estudo sobre git, docker e Kubernetes

Indice do arquivo
[ ] CRIAR INDICE

Container é uma tecnologia de virtualização leve usada principalmente para empacotar e isolar aplicativos e suas dependências em um ambiente separado, também podemos dizer que container é o agrupamento de uma aplicação junto com as suas dependências que compartilham o kernel do sistema operacional do host. Em outras palavras container é uma forma de isolamento.

A seguir, na figura, podemos notar as diferenças de quando temos aplicações sendo executadas nativamente, máquinas virtuais e por fim em containers.

![Comparação de uma VM com um container](img/img_container.png)

Containeres são muito populares porque oferecem várias vantagens, entre elas vale destacar:

1. Portabilidade: Como cada container inclui todas as dependências que ele precisa para a aplicação rodar perfeitamente, da mesma maneira em diversos ambientes sem problemas de compatibilidade.
2. Leveza: Por não precisarem de um sistema operacional completo consumem menos recursos.
3. Escalabilidade: São fáceis de replicar e escalar em diversos ambientes.
4. Rapidez: Se comparado a uma VM comum, a inicialização de um container é extremente rápida.

Observando a imagem acima pode então chegar a conclusão que a principal diferença entre uma VM (Máquina virtual) e um container é que na VM a máquina é virtualizada por inteiro até as camadas de hardware, enquanto que os contêineres a virtualização é apenas das camadas de software que estão acima da camada de sistema operacional.

Antes de continuarmos é necessário entender alguns conceitos importantes.

1. **Cgroups:** São uma funcionalidade do kernel Linux que permite gerenciar e limitar os recursos que os processos de um sistema podem consumir. 
2. **Namespaces:** São funcionalidades do kernel Linux usada em conjunto com o cgroup para prover isolamento de processos. Enquanto os cgroups controlam o uso de recursos (CPU, Memória, etc.), os namespaces são responsáveis por isolar diferentes aspectos do ambiente de execução, como isolamento do FileSystem, interfaces de rede, usuários, processos e etc. Em outras palavras, namespaces criam "subconjuntos" isolados de recursos do sistema, de modo que os processos em diferentes namespaces acreditem estar rodando em sistemas separados, embora compartilhem o mesmo kernel.

Antes de nos aprofundar no mundo dos containeres, vamos aprender a isolar um ambiente para entender melhor os conceitos acima apresentados.



