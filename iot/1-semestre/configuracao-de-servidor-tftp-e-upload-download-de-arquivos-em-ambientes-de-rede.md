# Configuração de Servidor TFTP e Upload/Download de Arquivos em Ambientes de Rede

### **1. Introdução - Objetivo da Aula**

A sessão teve como foco a **configuração e gerenciamento de um servidor TFTP** em um ambiente de redes estruturadas. O processo envolveu o entendimento da hierarquia de comandos disponíveis para diferentes níveis de usuários no Packet Tracer e a interface administrativa dos switches gerenciáveis. Além disso, a aula abordou a necessidade de **transportar e armazenar configurações** de dispositivos de rede usando **TFTP (Trivial File Transfer Protocol)** para backup e recuperação.

***

### **2. Arquitetura de Administração de Switches e Hierarquia de Comandos**

#### **2.1. Modos de Acesso e Escalabilidade de Privilégios**

Os switches gerenciáveis operam em uma estrutura hierárquica de comandos, onde os usuários podem **escalar privilégios** de acesso dependendo de sua autenticação e permissão dentro do sistema.

#### **2.2. Comandos Disponíveis por Categoria**

**Usuário Comum (Modo EXEC USER, sem privilégios administrativos)**

Os usuários com acesso restrito podem interagir com a rede e monitorar seu estado sem modificar configurações críticas. Alguns comandos disponíveis incluem:

* **`connect`** - Estabelece uma conexão de terminal.
* **`disable`** - Desativa comandos privilegiados.
* **`enable`** - Habilita comandos privilegiados (requer nível administrativo).
* **`exit/logout`** - Encerra a sessão do terminal.
* **`ping`** - Envia pacotes ICMP para diagnóstico de conectividade.
* **`ssh/telnet`** - Abre conexões remotas seguras ou não seguras.
* **`traceroute`** - Rastreia a rota de pacotes até um destino.

**Usuário Administrador (Modo EXEC PRIVILEGIADO, acesso root `#`)**

Com acesso elevado, os administradores podem modificar a configuração do switch e realizar operações críticas, como cópia, depuração e configuração de interfaces. Alguns comandos relevantes:

* **`clear`** - Redefine funções do sistema.
* **`copy`** - Copia arquivos entre dispositivos de armazenamento.
* **`debug/undebug`** - Ativa/desativa a depuração de processos da rede.
* **`erase`** - Apaga arquivos de um sistema de arquivos.
* **`show`** - Exibe o estado atual do sistema.
* **`reload`** - Reinicia o switch.
* **`write`** - Salva a configuração atual na memória.

**Modo de Configuração Global (`config` mode)**

Neste modo, os administradores podem definir políticas de segurança, configurar VLANs, interfaces e protocolos de roteamento. Os comandos incluem:

* **`aaa`** - Gerencia autenticação, autorização e contabilidade da rede.
* **`access-list`** - Define regras de firewall.
* **`interface`** - Seleciona e configura uma interface física ou lógica.
* **`hostname`** - Define o nome do sistema.
* **`spanning-tree`** - Gerencia a árvore de spanning (STP) para evitar loops de rede.
* **`vlan`** - Configuração de VLANs.
* **`vtp`** - Gerencia o protocolo de VLAN Trunking.

***

### **3. Configuração de um Servidor TFTP**

#### **3.1. Conceito e Finalidade**

O **TFTP (Trivial File Transfer Protocol)** é um protocolo simplificado de transferência de arquivos, amplamente utilizado para **armazenamento, backup e recuperação de configurações** de dispositivos de rede. Ele opera sobre **UDP (porta 69)**, sendo leve, mas vulnerável a ataques devido à ausência de autenticação robusta.

#### **3.2. Etapas para Configuração no Packet Tracer**

**Passo 1: Configurar o Servidor TFTP**

1. Adicionar um **servidor TFTP** à topologia de rede.
2. Atribuir um endereço IP estático ao servidor.
3. Configurar o serviço TFTP para permitir armazenamento e recuperação de arquivos.

**Passo 2: Configurar o Switch para Utilizar TFTP**

1. Acessar o switch via **console ou SSH**.
2. Habilitar o modo privilegiado com `enable`.
3. Verificar a conectividade com o servidor via `ping <IP do servidor>`.
4.  Executar o comando para copiar a configuração:

    ```bash
    copy running-config tftp
    ```
5. Inserir o endereço do servidor TFTP e o nome do arquivo de destino.

**Passo 3: Restaurar Configuração de um Backup via TFTP**

1. Garantir que o servidor TFTP esteja acessível.
2.  No switch, executar:

    ```bash
    copy tftp running-config
    ```
3. Confirmar os detalhes do arquivo e do IP do servidor.
4. Aplicar a configuração carregada.

***

### **4. Segurança e Gestão de Transferências TFTP**

#### **4.1. Vulnerabilidades do TFTP**

* **Sem Autenticação**: Qualquer dispositivo na rede pode enviar ou receber arquivos.
* **Uso de UDP**: Não há garantia de entrega dos pacotes, tornando-o suscetível a falhas em redes instáveis.
* **Interceptação de Tráfego**: Pacotes podem ser capturados e modificados via **MITM (Man-in-the-Middle)**.

#### **4.2. Estratégias de Proteção**

* **Filtragem de Tráfego**: Criar regras de firewall para limitar acessos ao serviço TFTP.
* **Criptografia**: Utilizar VPNs ou túneis SSH para encapsular as transmissões.
* **Autenticação Alternativa**: Sempre que possível, preferir **SCP ou SFTP** para operações sensíveis.

***

### **5. Aplicação em Ambientes Corporativos e Impacto na Manutenção de Redes**

A implementação de **TFTP para backup e restauração de configurações** permite:\
✅ **Recuperação Rápida**: Em caso de falha, um switch pode ser restaurado para o último estado operacional em segundos.\
✅ **Configuração Padronizada**: Novos dispositivos podem ser inicializados rapidamente com arquivos de configuração pré-definidos.\
✅ **Gestão Centralizada**: Evita configurações manuais inconsistentes entre múltiplos switches.

Em redes empresariais, TFTP é amplamente utilizado em **arquiteturas Cisco**, facilitando operações de manutenção e contingência.

***

### **6. Conclusão - Integração dos Conceitos na Administração de Redes**

A aula forneceu uma visão aprofundada sobre **administração de switches gerenciáveis** e o uso de **TFTP como um meio essencial para gestão de configuração**. Com isso, consolidamos conceitos críticos como:

* **Modos de operação de um switch e hierarquia de comandos**.
* **Processo de escalonamento de privilégios para administração remota**.
* **Configuração e uso de um servidor TFTP para backup e restauração de arquivos**.
* **Riscos de segurança inerentes ao uso do TFTP e formas de mitigação**.

Essa base é essencial para qualquer profissional que trabalhe com **infraestrutura de redes empresariais**, garantindo **gestão eficiente e segurança operacional** dos dispositivos.
