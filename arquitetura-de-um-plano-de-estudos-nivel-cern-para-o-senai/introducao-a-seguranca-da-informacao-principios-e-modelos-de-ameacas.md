# Introdução à Segurança da Informação: Princípios e Modelos de Ameaças

## 1. Introdução

Bom, aqui começo o meu primeiro artigo em que aprofundo tecnicas de segurança da informação, explorando e integrando o conceito de ataques com equipes centauros (humanos + IA), em que através de teoria de jogos, estabele-se um esquema de recompensas baseados em accesso a recursos, onde quanto mais camadas a equipe adversária atravessa, maior seu ganho, enquanto a equipe de defesa também centauro, ao mitigar, recupera seus pontos perdidos e se prever um comportamento, ganha payoffs enquanto remove da equipe adversária.

No caso, esse sistema de transformers, cada neuronio seria uma tecnologia (IDS, Firewall, Switch, etc) e o modelo matematico de aprendizado de ambas as partes criam vetores (Por exemplo, do lado defensor, há o cruzamento entre IDS e firewall, criando um caminho vetorial, enquanto no atacante, ao quebrar um desses caminhos, conseguem tanto o IDS quanto o firewall, mas irei aprofundar mais adiante.

### Definição de Segurança da Informação

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

Bom, como dito anteriormente, a pior coisa que se pode acontecer a um negócio que lida com dados é um ataque persistente e direcionado. Podendo ser segmentados por estratégias e formas.

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

O atacante configura um roteador para anunciar rotas falsas para uma rede. Isso pode ser feito manipulando o BGP para fazer com que o tráfego seja redirecionado para um local não autorizado

O BGP Hijacking consiste em explorar a arquitetura descentralizada do protocolo Border Gateway Protocol para anunciar rotas indevidas, redirecionando o tráfego de forma não autorizada. Isso pode resultar em negação de serviço em larga escala, espionagem de tráfego em trânsito entre grandes blocos de rede e até mesmo adulteração de dados.

Uma medida de proteção pode ser a validação de rotas através de políticas rigorosas, o BGPSPEC que fornece autenticação e integridade das informações de roteamento e o monitoramento continuo do trafego na rede.

**DNS Spoofing**

**O DNS** (Domain Name System) é o sistema que traduz nomes de domínio amigáveis (como example.com) em endereços IP (como 192.0.2.1) que os computadores usam para identificar uns aos outros na rede. Quando você digita um nome de domínio no navegador, uma solicitação é enviada a um servidor DNS para resolver esse nome em um endereço IP.

No DNS Spoofing, o invasor corrompe respostas DNS para desviar usuários para endereços falsos, possibilitando phishing ou injeção de malware. A técnica pode envolver envenenamento de cache (DNS cache poisoning ao enviar respostas falsas a um servidor de cache DNS, fazendo armazenar informações incorretas) ou comprometimento de servidores DNS autorizados, impactando a integridade e a confiabilidade do nome de domínio.

Esse tipo de ataque abre portas para **phishing,** redirecionando usuários para sites falsos que se parecem com sites legítimos, onde os atacantes podem coletar informações confidenciais, como credenciais de login e dados financeiros ou i**njeção de malware, r**edirecionando usuários para sites maliciosos que contêm código malicioso, onde os atacantes podem infectar dispositivos com vírus, ransomware e outros tipos de software malicioso.

Uma contra medida eficaz é a implementação de protocolos que autentifica respostas DNS com assinaturas criptografadas, como DNSSEC, monitoramento continuo de tráfego e políticas de cache seguras.

**Man-in-the-Middle (MitM)**

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

**Exploração de TLS/SSL (BEAST, POODLE, Heartbleed)**

Vou resumir aqui:

* BEAST (Browser Exploit Against SSL/TLS)
  1. **Como Funciona**:
     * BEAST explora uma vulnerabilidade no SSL 3.0 e no TLS 1.0 que permite um ataque de criptografia CBC (Cipher Block Chaining).
     * O atacante intercepta e modifica pacotes SSL/TLS enquanto força o navegador a enviar dados específicos para um site alvo.
  2. **Impacto**:
     * Decriptação de dados criptografados.
     * Injeção de conteúdo malicioso durante a comunicação segura.
  3. **Mitigação**:
     * Atualização para TLS 1.1 ou superior, que não são vulneráveis ao ataque CBC.
     * Uso de TLS 1.0 com mitigação como TLS Record Splitting.
* POODLE (Padding Oracle On Downgraded Legacy Encryption)
  1. **Como Funciona**:
     * POODLE explora uma vulnerabilidade no SSL 3.0 relacionada ao preenchimento de dados em modos CBC.
     * Forçando a utilização de SSL 3.0, o atacante pode explorar essa falha para decriptar informações.
  2. **Impacto**:
     * Decriptação de sessões criptografadas.
     * Comprometimento de dados transmitidos supostamente seguros.
  3. **Mitigação**:
     * Desativar o suporte ao SSL 3.0 em navegadores e servidores.
     * Uso de criptografia moderna como TLS 1.2 e superiores.
* Heartbleed
  1. **Como Funciona**:
     * Heartbleed é uma vulnerabilidade no protocolo TLS, especificamente em uma extensão do OpenSSL chamada Heartbeat.
     * Um atacante envia uma solicitação maliciosa ao servidor, fazendo com que ele responda com mais dados do que deveria, vazando partes da memória do servidor.
  2. **Impacto**:
     * Extração de conteúdo sensível da memória do servidor.
     * Exposição de chaves privadas, dados de usuários, senhas e outros dados sensíveis.
  3. **Mitigação**:
     * Atualização para uma versão corrigida do OpenSSL.
     * Revogação e reemissão de certificados SSL/TLS.
     * Alteração de senhas e chaves privadas comprometidas.

### 3.5 Ataques em Aplicações e Dados

**Evasão de Firewalls e IDS usando Polimorfismo e Ofuscação**

Técnicas de polimorfismo, que a capacidade de um malware de se modificar de modo a alterar sua assinatura estática (sequência de bytes que identifica o malware) a cada nova infecção ou iteração, variantes de malware que alteram sua assinatura estática, dificultando a detecção por soluções baseadas em assinatura como antivírus, que dependem de assinaturas conhecidas para identificar ameaças.

O malware contém um motor polimórfico que gera novas versões de seu código a cada execução, por exemplo, um vírus polimórfico pode reordenar suas instruções, utilizar diferentes métodos de criptografia para seus segmentos de código e substituir funções por equivalentes que realizam a mesma tarefa onde cada nova versão tem uma assinatura diferente.

Da mesma forma, ofuscações em pacotes (via fragmentação, encoding de payload ou criptografia customizada) podem iludir sistemas de monitoramento, permitindo que o tráfego hostil se misture a fluxos legítimos.

Vou resumir aqui:

1. **Fragmentação**:
   * **Descrição**: Dividir o payload (carga útil) malicioso em partes menores e enviar esses fragmentos separadamente. O malware é reconstituído no destino.
   * **Exemplo**: Um arquivo malicioso pode ser dividido em vários pacotes menores, cada um transmitido separadamente para evitar detecção.
2. **Encoding de Payload**:
   * **Descrição**: Codificar o payload em diferentes formatos (por exemplo, Base64) para mascarar o conteúdo original.
   * **Exemplo**: A codificação de payload torna a análise direta do conteúdo mais difícil para sistemas de monitoramento.
3. **Criptografia Customizada**:
   * **Descrição**: Usar algoritmos de criptografia personalizados para proteger o payload. Apenas o malware sabe como decifrar seu próprio conteúdo.
   * **Exemplo**: Criptografar o código malicioso com uma chave que só será conhecida no momento da execução, evitando a detecção por scanners que analisam o conteúdo.

#### Contramedidas

**Análise Heurística e Comportamental:**

* **Descrição**: Em vez de buscar assinaturas específicas, essas técnicas analisam o comportamento dos programas e identificam padrões suspeitos de atividades, como acessos não autorizados à memória ou comportamentos anômalos.
* **Exemplo**: Um antivírus com análise heurística pode detectar malware polimórfico observando a atividade suspeita, independentemente da assinatura.

**Aprendizado de Máquina:**

* **Descrição**: Modelos de aprendizado de máquina podem ser treinados para reconhecer comportamentos maliciosos e padrões ocultos em grandes volumes de dados.
* **Exemplo**: Detectar novas variantes de malware com base em similaridades comportamentais em vez de apenas assinaturas estáticas.

**Injeção de Código (SQLi, XXE, RCE)**

A injeção de comandos SQL (SQLi) continua sendo um dos métodos mais comuns para obtenção de acesso não autorizado a bancos de dados, onde a vulnerabilidade permite que um atacante interfira nas consultas que uma aplicação faz ao banco de dados. Isso ocorre quando dados fornecidos pelo usuário são incluídos diretamente em uma consulta SQL sem a devida validação ou sanitização.&#x20;

**Como Funciona?**

1. **Entrada Maliciosa**:
   * O atacante insere comandos SQL maliciosos em campos de entrada de formulários, como campos de login, caixas de pesquisa ou parâmetros de URL.
   * Exemplo: Inserir `' OR '1'='1` em um campo de senha pode transformar uma consulta SQL legítima em uma que retorna todos os usuários.
2. **Execução da Consulta**:
   * A consulta modificada é executada pelo banco de dados.
   * O ataque pode resultar na divulgação de dados confidenciais, modificação ou exclusão de dados ou até mesmo a execução de comandos administrativos no banco de dados.

* **Prevenção:**
  * **Sanitização e Validação de Entrada**: Utilizar APIs seguras, como prepared statements, que separam o código SQL dos dados.
  * **Ferramentas de Detecção**: Implementar sistemas de detecção de intrusão (IDS) e monitoramento de atividades suspeitas.

Em paralelo, ataques como XXE (XML External Entities) exploram processadores XML mal configurados para exfiltrar arquivos internos ou realizar DoS.&#x20;

**Como Funciona?**

1. **Definição de Entidades Externas**:
   * O atacante inclui entidades XML externas maliciosas em um documento XML.
   * Exemplo: `<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>`
2. **Processamento do XML**:
   * O processador XML, ao interpretar a entidade, tenta acessar recursos externos, como arquivos locais ou URLs remotas.

* **Prevenção:**
  * **Desativação de Entidades Externas**: Configurar o parser XML para não processar entidades externas.
  * **Validação de Entrada**: Validar e sanitizar todo o conteúdo XML antes do processamento.

Já as RCE (Remote Code Execution) permitem que o invasor execute comandos arbitrários no servidor, muitas vezes resultando em controle total da aplicação ou do sistema operacional subjacente.

**Como Funciona?**

1. **Entrada Maliciosa**:
   * O atacante injeta código malicioso em entradas que serão processadas pelo servidor.
   * Exemplo: Injetar comandos de shell em um campo que é passado diretamente para o interpretador de comandos do sistema.
2. **Execução de Código**:
   * O servidor executa o código malicioso, concedendo ao atacante o controle sobre o sistema.

* **Prevenção:**
  * **Sanitização de Entrada**: Garantir que todas as entradas do usuário sejam devidamente validadas e sanitizadas.
  * **Políticas de Segurança**: Configurações rigorosas de segurança que minimizem a superfície de ataque, como desativar funcionalidades desnecessárias e usar permissões mínimas.

**Deepfake Attacks e Engenharia Social Automatizada**

Ferramentas de inteligência artificial permitem a criação de deepfakes realistas de áudio e vídeo, que podem ser empregadas para fraudar processos de autenticação biométrica ou manipular interações humanas. Associadas a técnicas de engenharia social, essas falsificações tornam-se ainda mais convincentes, afetando a confiança em identidades digitais e potencialmente levando ao roubo de credenciais ou a fraudes financeiras sofisticadas.

#### 3.6 Ataques Baseados em IA e Redes Neurais Adversariais

**Model Extraction & Model Inversion Attacks**

Em sistemas de aprendizado de máquina hospedados em plataformas públicas, invasores podem utilizar consultas iterativas para inferir parâmetros internos de modelos proprietários, caracterizando ataques de extração. Já o model inversion permite a reconstrução de dados de treinamento sensíveis a partir do comportamento do modelo, comprometendo a privacidade de usuários e organizações.

**Poisoning Attacks e Adversarial Perturbations**

Nos ataques de envenenamento (poisoning attacks), dados maliciosos são introduzidos no conjunto de treinamento, corrompendo a capacidade do modelo de classificar ou prever corretamente, seja direcionando-o a conclusões falsas ou reduzindo sua acurácia geral. Por outro lado, as adversarial perturbations são pequenas alterações em entradas legítimas, geralmente imperceptíveis a olho nu, mas suficientes para enganar modelos de visão computacional ou processamento de linguagem natural, conduzindo a classificações equivocadas e expondo falhas críticas em sistemas de segurança automatizados.





