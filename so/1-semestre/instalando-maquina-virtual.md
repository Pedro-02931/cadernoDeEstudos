# Instalando Maquina Virtual

## **1. HIPERVISORES E O IMPACTO DA NEUROFISIOLOGIA COMPUTACIONAL NO CAOS VIRTUAL**

Bom, minhas anotações sobre a aula de sistema operacional, onde montamos através do Virtual Box, então decidi compilar os conceitos chaves explicados na aula.

### **1.1 O que é um Hypervisor e por que ele é essencial**

O Hypervisor é um um software ou firmware que permite, através de virtualização, controlar a permissão de acesso aos recursos de hardware, permitindo um isolamento e gerenciamento de máquinas virtuais. Esse isolamento opera em gerenciando threads e instruções de CPU pra criar múltiplos "universos paralelos", como se cada VM fosse um neurônio interconectado.

Basicamente um grafo de ramificação, em que através de um SO principal, pode-se testar e operar múltiplos sistemas sem correr risco de corromper o nó principal, que hospeda todos os sub-sistemas operacionais. Por exemplo, rodar Linux no Windows, embora não seja necessariamente a melhor opção ~~(O WSL é uma delícia, pois é uma **compatibilidade de chamadas de sistema**.).~~



### 1.2 Como ele faz o isolamento das VMs?

Ele age como um **orquestrador** , controlando como múltiplas VMs interagem com o hardware físico sem que elas tenham contato direto com ele e algumas arquiteturas de processadores possuem extensões específicas para **suportar virtualização**, como:

* **Intel VT-x** (Intel Virtualization Technology)
* **AMD-V** (AMD Virtualization)

Essas extensões ajudam o hypervisor a funcionar de forma mais eficiente, permitindo que certas operações sejam aceleradas no hardware ao invés de serem emuladas por software.

O Hypervisor cria um ambiente isolado para cada VM, garantindo que:

* Nenhuma VM possa acessar diretamente o hardware sem passar pelo Hypervisor.
* Recursos como CPU, memória RAM, disco e rede sejam alocados de forma controlada.
* Se uma VM travar ou for comprometida, ela não afete as outras nem o sistema principal.

### **1.3 Tipos de Hypervisores e suas estruturas computacionais**

Existem dois tipos principais:

* **Hypervisor Tipo 1 (Bare Metal):** roda diretamente no hardware, sem um sistema operacional intermediário. Exemplo: VMware ESXi, Microsoft Hyper-V (modo bare metal), Xen. Roda diretamente em cima do hardware, como se fosse a **medula espinhal recebendo sinais brutos**.
* **Hypervisor Tipo 2 (Hosted):** roda sobre um sistema operacional comum, como um aplicativo. Exemplo: VirtualBox, VMware Workstation, QEMU/KVM rodando sobre Linux. Age como uma camada intermediária, dependendo do sistema operacional pra sobreviver, tipo um **parasita.**

### **1.4 Hypervisor como um modelo cognitivo e sua analogia com o cérebro**

O Hypervisor age como um cérebro que cria uma rede de neurônios isolados (VMs), mas essas VMs não compartilham diretamente as sinapses. Elas precisam de um canal específico para se comunicar, como interfaces de rede virtuais ou discos compartilhados.

No Hypervisor, a comunicação entre **VMs e hardware não acontece via syscalls comuns**, mas sim por meio de **paravirtualização, passthrough de hardware ou emulação.**

Por isso a importancia de hábilitar o isolamento do núcleo, para permitr que partes especificas sejam protegidas, dado que o hosted não sabe o que acontece dentro da maquina virtual, apenas sabendo que recurso tal foi consumido por tal virtualização.

Hypervisors **hosted (Tipo 2)**, como VirtualBox, VMware Workstation ou QEMU/KVM rodando em modo usuário, **sabem exatamente o que acontece dentro da VM** porque eles:

* Interceptam chamadas de sistema da VM.
* Controlam diretamente os dispositivos virtuais.
* Administram permissões e restrições de hardware.
* Muitas vezes, permitem introspecção (verificação do que está acontecendo dentro da VM).

O Hypervisor Hosted tem controle sobre os recursos alocados para a VM e pode monitorar suas interações com o hardware, mas não tem a mesma visibilidade granular que um Hypervisor Bare Metal teria sobre o funcionamento interno da VM.

***

### **2. ISO, ARQUITETURA CEREBRAL E O METAMORFISMO MICROKERNEL: A FODA COMPACTADA DO SISTEMA**

Uma **ISO (Imagem ISO)** é um **arquivo que contém uma cópia exata de um sistema de arquivos completo**, geralmente de um CD/DVD ou outro meio de instalação encapsulando bibliotecas, binários e scripts de configuração dentro de uma imagem de disco, garantindo que o sistema possa ser instalado ou inicializado corretamente em um hardware. Basicamente é um **arquivo de disco compactado**, contendo tudo que seria encontrado num disco físico, incluindo:

* **Arquivos de sistema operacional** (como Linux, Windows, etc.).
* **Drivers e pacotes de software**.
* **Bootloaders e scripts de instalação**.

Em uma analogia filosófica, uma ISO é como um axônio pronto para transmitir um impulso elétrico, mas que ainda precisa de um estímulo (montagem ou boot) para liberar suas instruções no sistema e ISO contém os genes que definirão o comportamento do sistema operacional, incluindo quais drivers poderão ser carregados e como o hardware será interpretado pelo SO.&#x20;

Uma ISO pode ser vista como um impulso nervoso pronto para ser transmitido: contém todos os arquivos essenciais para que um sistema operacional possa ser instalado ou executado, incluindo drivers, bibliotecas e scripts. No entanto, ela não atua diretamente no hardware—o sistema operacional que será instalado a partir dela é quem fará essa interação.

### **2.1 Microkernel vs Monolithic Kernel: Anatomia de uma abstração operacional**

Pensar nisso como **microkernel** é reconhecer que existe um núcleo mínimo que gerencia tarefas cruciais de forma discreta. pense no microkernel como **o sistema nervoso periférico**, que **só transmite sinais e delega funções para outros sistemas**.

A diferença fundamental entre microkernel e monolithic kernel está em como eles organizam e executam os serviços do sistema operacional. O monolithic kernel centraliza a execução no próprio kernel, enquanto o microkernel delega a maioria dos serviços para processos no espaço de usuário.

Cada syscall é como um pedido ao sistema nervoso central. Os processos (neurônios) enviam sinais ao kernel (cérebro), que processa a informação e envia comandos apropriados aos dispositivos de hardware.

O sistema operacional lê a ISO como um organismo que absorve nutrientes para crescer e se estabelecer. A instalação copia os arquivos necessários, configura o ambiente e cria uma base para a execução do sistema.

### E o que ~~caralhos~~ isso tem a ver com VM

Bom, essa alucinação foi para compilar melhor o conceito, mas a **máquina host (o sistema operacional que roda no hardware físico) não é um microkernel por si só**. Mas se estivermos falando de um **host que roda um SO baseado em microkernel**, então ele pode ter **uma arquitetura microkernel operando nele**.&#x20;

Se a máquina host está rodando um sistema operacional baseado em **monolithic kernel** (como Linux ou Windows), **ela definitivamente não é um microkernel**. Aqui está o motivo:

* O **kernel monolítico** centraliza a maior parte das funções do sistema dentro do próprio núcleo.
* Isso inclui drivers, sistema de arquivos, gerenciador de memória, rede, etc.
* **Exemplos:** Linux, Windows NT (que é um híbrido, mas bem mais próximo de um monolithic kernel na prática), FreeBSD.

MAS se a máquina host está rodando um sistema operacional baseado em **microkernel**, **aí sim o host pode ser considerado um sistema com arquitetura de microkernel**.\
Isso acontece quando:

* O kernel **somente gerencia IPC (Inter-Process Communication), memória e escalonamento**.
* Drivers, sistemas de arquivos e outros serviços rodam em processos separados no espaço de usuário.
* **Exemplos de SOs com microkernel:** Minix, QNX, L4, Redox OS.

***

### **3. SATA e VDI**

#### O SATA é um protocolo e uma interface para transferência de dados entre armazenamento (HDDs e SSDs) e a placa-mãe, sendo comparável a **um conjunto de estradas pois pacotes de dados estruturados** em uma camada lógica e física.

Ou seja, SATA é a infraestrutura rodoviária do armazenamento digital, um sistema de transporte de alta velocidade que leva os dados do disco rígido ou SSD até o restante do sistema, garantindo que pacotes de informação cheguem aos seus destinos com eficiência

### **3.1 Virtualização de armazenamento e a abstração de barramentos**

Um Hypervisor cria um **disco SATA virtual que** é **uma emulação ou passthrough** da interface de armazenamento, permitindo que a VM acredite estar acessando um disco físico real.

* Em um sistema de virtualização, o Hypervisor pode:
  * **Emular um controlador SATA** para a VM, simulando um disco físico.
  * **Fazer passthrough de um dispositivo SATA real**, permitindo que a VM acesse diretamente o hardware.

Criar um driver SATA virtual no VirtualBox é como forjar uma identidade digital: a VM acredita estar lidando com um disco físico real, mas, nos bastidores, o Hypervisor está controlando e intermediando a transmissão de dados

### **3.2 O VDI**

O VDI é uma cápsula digital que encapsula um disco virtual dentro do host, permitindo que o sistema operacional convidado enxergue armazenamento persistente mesmo sem um hardware físico real.

Embora ele seja escalável com base no espaço real, o sistema permite com que o ambiente virtualizado veja um HD maior do que realmente é, permitindo a instalação de softwares na máquina.

### **3.3 Hypervisor como árbitro da teoria de jogos em armazenamento**

Cada VM disputa recursos computacionais. O Hypervisor é o árbitro, decidindo qual máquina tem prioridade no uso da CPU, memória e acesso ao armazenamento, garantindo que o sistema continue operando de forma justa e eficiente.

Ou seja:

* O Hypervisor **de fato gerencia a alocação de recursos** entre as VMs.
* O conceito de **disputa de recursos** faz sentido porque as VMs competem por **CPU, RAM, I/O de disco e rede**.

***

### **5. CONCLUSÃO APOTEÓTICA**

A virtualização não é só um conceito técnico: é uma simulação de uma realidade paralela dentro do próprio sistema computacional. O Hypervisor age como um **arquitetor do multiverso digital**, criando universos isolados (VMs) que coexistem sem interferir diretamente uns nos outros, replicando o que um cérebro faz ao modular diferentes áreas cognitivas. Ele é tanto um supervisor de recursos quanto um gatekeeper da eficiência operacional.

Se cada VM é um neurônio isolado, então o **microkernel e o monolithic kernel** são os sistemas nervosos que controlam a comunicação interna de cada máquina. No microkernel, a descentralização impera: serviços como drivers e sistemas de arquivos são terceirizados, tornando a arquitetura mais modular. Já no kernel monolítico, a abordagem é centralizadora, integrando tudo dentro do núcleo para um desempenho mais imediato. E se a ISO é o DNA do sistema, carregando os genes que definirão seu comportamento pós-instalação, então o SATA e o VDI são os caminhos por onde essa informação flui – rodovias digitais que garantem que tudo chegue ao seu devido lugar.

Dentro desse ecossistema, cada VM **disputa recursos como um competidor em um jogo de soma-zero**. O Hypervisor age como um **juiz imparcial**, decidindo quem recebe mais CPU, quem tem acesso prioritário ao disco e quem será temporariamente sufocado em nome da estabilidade geral do sistema. O mesmo acontece no armazenamento virtualizado: enquanto um HD físico tem limitações tangíveis, um VDI pode mascarar sua verdadeira capacidade, oferecendo uma ilusão de abundância até o espaço real se tornar um problema concreto.

No final das contas, tudo isso converge para um único ponto: **o controle absoluto do caos computacional**. Se a computação moderna é um campo de batalha de eficiência contra gargalos, de abstrações contra limitações físicas, então o Hypervisor, os sistemas operacionais e as técnicas de virtualização são as estratégias que garantem que o jogo continue rodando sem travar. No mundo real, hardware e software competem por sobrevivência. No mundo virtualizado, a guerra acontece dentro do próprio hardware, e cabe ao Hypervisor manter esse delicado equilíbrio entre ordem e entropia.
