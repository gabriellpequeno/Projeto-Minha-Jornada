# Uma Jornada de Aprendizado
[Gerenciamento de Versão](./moduloVersionamento.md)


## Parte 1 | A Evolução da Internet

Da Arpanet até a WEB 3.0.

### História da Internet
A Internet moderna tem suas raízes na ARPANET, uma rede de comutação de pacotes financiada pelo Departamento de Defesa dos EUA na década de 1960. O desenvolvimento do TCP/IP (Transmission Control Protocol/Internet Protocol) nos anos 70 estabeleceu a base para a interconexão de redes, levando ao crescimento da Internet como a conhecemos hoje.

### Web 2.0 e Web 3.0
A evolução da Web é divida em três grandes etapas que marcam pontos de virada tecnológicos.

 - **Web 1 (Nos primórdios)**
 Focada em páginas estáticas e consumo de conteúdo. Era a "Web de leitura
 
- **Web 2.0 (Atual)**
Caracterizada pela interatividade, colaboração e conteúdo gerado pelo usuário. É a "Web social", impulsionada por plataformas como Facebook, YouTube e blogs.

- **Web 3.0 (O futuro que bate a porta.)**
Visa a descentralização e a propriedade do usuário sobre seus dados. É a "Web de propriedade", baseada em tecnologias como Blockchain e inteligência artificial.

### Backbones e Arquitetura da Internet

**O Backbone da Internet** é a principal rota de dados entre grandes redes interconectadas e roteadores centrais. Ele funciona como a **"espinha dorsal"** da Internet, consistindo em cabos de fibra óptica de alta capacidade que transportam a maior parte do tráfego de longa distância. **A arquitetura da Internet** é baseada em um modelo de camadas **(o modelo TCP/IP)**, que garante escalabilidade, robustez e a capacidade de interconectar redes heterogêneas.

## Parte 2 | Os Fundamentos de Redes

### Topologia de Redes

A Topologia de Redes é a disposição física ou lógica dos elementos de uma rede de comunicação, como dispositivos e cabos. A topologia física descreve o layout real dos cabos, enquanto a topologia lógica descreve como os dados fluem através da rede.

| Estrela | Anel | Barramento | Malha (Mesh) |
|--|--|--|--|
| Todos os dispositivos se conectam a um ponto central. | Cada dispositivo se conecta exatamente a outros dois, formando um único caminho circular para o sinal. | Todos os dispositivos se conectam a um único cabo principal. | Cada dispositivo se conecta a todos os outros ou a múltiplos outros. |
| Fácil de instalar e gerenciar a falha em um nó não afeta a rede. | Tráfego de dados rápido. | Requer menos cabo e é de fácil instalação. | Alta redundância e tolerância a falhas. |
| Falha no ponto central paralisa toda a rede. | Falha em um único link ou nó pode paralisar a rede; difícil de reconfigurar. | Falha no cabo principal paralisa a rede; difícil de isolar falhas. | Extremamente cara e complexa de instalar e gerenciar. |




### Tipos de Redes

As redes são classificadas com base em sua **área de cobertura:**

- **PAN (Personal Area Network):**
Conecta dispositivos dentro do alcance de um indivíduo, tipicamente a poucos metros.

- **LAN (Local Area Network):**
Cobre uma área geográfica pequena, como uma casa, escritório ou campus.


- **MAN (Metropolitan Area Network):**
Cobre uma área maior que uma LAN, como uma cidade.

- **WAN (Wide Area Network):**
Cobre uma área geográfica extensa, conectando LANs e MANs, como a Internet.

## Parte 3 | Protocolos e Endereçamento

São **os protocolos** que definem como nossa rede se comunica de maneira eficaz e segura, garantindo que cada **endereço** receba o que tem que receber.

### Protocolos de Comunicação: TCP, UDP e ICMP
| Protocolo | Camada | Orientação | Confiabilidade | Uso Principal |
|--|--|--|--|--|
| TCP (Transmission Control Protocol) | Transporte | Orientado à Conexão | Alta (garante entrega, ordem e retransmissão) | HTTP, HTTPS, FTP, SMTP (navegação web, e-mail) |
| UDP (User Datagram Protocol) | Transporte | Não Orientado à Conexão | Baixa (entrega "melhor esforço", sem garantia) | DNS, VoIP, Streaming de vídeo (aplicações em tempo real) |
| ICMP (Internet Control Message Protocol) | Rede | Não Orientado à Conexão | Usado para controle | Mensagens de erro e consultas |

### Internet Protocol (IP)

O **Internet Protocol (IP)** é o protocolo principal para rotear dados através da Internet. Ele define o esquema de **endereçamento e a estrutura dos pacotes** de dados (datagramas).

- **IPv4:**
Utiliza endereços de 32 bits, representados por quatro números decimais separados por pontos (ex: 192.168.1.1). Devido ao esgotamento de endereços, está sendo gradualmente substituído

- **IPv6**
Utiliza endereços de 128 bits, representados por oito grupos de quatro dígitos hexadecimais separados por dois pontos (ex: 2001:0db8:85a3:0000:0000:8a2e:0370:7334). Oferece um espaço de endereçamento virtualmente ilimitado.

### Portas de Endereços IP
As portas são identificadores que em conjunto do IP permite que os dados cheguem aos processos ou aplicativos devidos. 
| Porta | Protocolo | Serviço |
|--|--|--|
| 20/21 | TCP | FTP (File Transfer Protocol) |
| 22 | TCP | SSH (Secure Shell) |
| 25 | TCP | SMTP (Simple Mail Transfer Protocol) |
| 53 | UDP/TCP | DNS (Domain Name System) |
| 80 | TCP | HTTP (Hypertext Transfer Protocol) |
| 443 | TCP | HTTPS (HTTP Secure) |

## Parte 4 | Desempenho de Rede

Existem métricas que medem a eficiência com que os dados são transmitidos numa rede, como a latência, largura de banda ou taxa de erro de atividade.

### Latência, Ping e Tracert
- **Latência:**
É o tempo que um pacote de dados leva para viajar de um ponto a outro. É um indicador crucial do desempenho da rede.

- **Ping:**
Utiliza o protocolo ICMP para enviar pacotes de solicitação de eco a um host e medir o tempo de ida e volta, que é a latência.

- **Tracert (Traceroute):**
Mapeia o caminho que um pacote de dados percorre até seu destino, listando todos os roteadores (saltos) intermediários e a latência para cada um.

### Conceitos Fundamentais do DNS
O DNS (Domain Name System) é o sistema de nomenclatura hierárquico e descentralizado usado para traduzir nomes de domínio legíveis por humanos (ex: www.exemplo.com) em endereços IP numéricos (ex: 192.0.2.44) que os computadores usam para se comunicar. Ele funciona como a "lista telefônica" da Internet.

#### Diagrama de Fluxo de consulta DNS

```mermaid
 sequenceDiagram
    participant Usuário
    participant Resolvedor DNS
    participant Servidor Raiz (.)
    participant Servidor TLD (.com)
    participant Servidor Autoritativo (site.com)

    Usuário->>Resolvedor DNS: 1. Onde está www.site.com?
    Note over Resolvedor DNS: Cache está vazio. Preciso descobrir.

    Resolvedor DNS->>Servidor Raiz (.): 2. Olá, quem responde por .com?
    Servidor Raiz (.)-->>Resolvedor DNS: 3. Os servidores TLD do .com respondem.

    Resolvedor DNS->>Servidor TLD (.com): 4. Olá, quem responde por site.com?
    Servidor TLD (.com)-->>Resolvedor DNS: 5. O Servidor Autoritativo de site.com responde.

    Resolvedor DNS->>Servidor Autoritativo (site.com): 6. Olá, qual o IP de www.site.com?
    Servidor Autoritativo (site.com)-->>Resolvedor DNS: 7. O IP é 192.0.2.123.

    Note over Resolvedor DNS: Armazena a resposta (192.0.2.123) em cache.
    Resolvedor DNS-->>Usuário: 8. O IP de www.site.com é 192.0.2.123.

    Usuário->>www.site.com (192.0.2.123): 9. Conecta ao site.
 ```

## Parte 5 | Segurança Cibernética

A segurança de dados vem cada dia mais se tornando algo indispensável a todos, e entender os riscos e como se prevenir é nossa obrigação.

### Segurança de Redes, Tipos de Ataques e Proteções
A Segurança de Redes é a prática de proteger a rede interna e os dados contra invasões, violações e ameaças.
#### Tipos de Ataques Comuns:

- **DDoS (Distributed Denial of Service) e DoS(Denial of Service):**
Sobrecarga de um servidor com tráfego, tornando-o indisponível. O que difere o DoS e DDoS, é seu modus operanti, enquanto o DoS é feito de uma unica fonte, o DDoS usa de uma botnet para efetuar o ataque.
- **Phishing:**
Tentativas de enganar usuários para que revelem informações confidenciais (senhas, dados bancários).
- **Malware:**
Software malicioso (vírus, ransomware, spyware) projetado para danificar ou obter acesso não autorizado.
- **Man-in-the-Middle (MitM):**
Interceptação da comunicação entre duas partes para roubar ou alterar dados.

#### Proteções e Ameaças
A proteção envolve uma abordagem em camadas, incluindo políticas de segurança, criptografia, autenticação e monitoramento contínuo.

### Firewalls e Antivírus
Ferramentas fundamentais para a segurança de rede, que atuando em conjuntos criam camadas de defesa muito solidas, protegendo antes dos dados chegarem a maquina e após chegarem na maquina.
 - **Firewall:**
Atua como uma barreira de segurança na fronteira da rede, filtrando o tráfego de entrada e saída com base em regras predefinidas. Ele protege a rede como um todo.
-- **Filtro de Pacotes:**
Examina cabeçalhos de pacotes (camadas 3 e 4).
-- **Stateful Inspection:**
Monitora o estado das conexões ativas, permitindo apenas pacotes que fazem parte de uma sessão estabelecida.
-- **Proxy (Application-Level Gateway):**
Atua como intermediário, inspecionando o tráfego em nível de aplicação (camada 7).
-- **Next-Generation Firewall (NGFW):**
Combina as capacidades dos firewalls tradicionais com inspeção profunda de pacotes (DPI), controle de aplicações, prevenção de intrusão (IPS) e inteligência contra ameaças.

- **Antivírus:**
É uma solução de segurança de endpoint (dispositivo individual). Ele detecta, previne e remove softwares maliciosos que conseguiram entrar no dispositivo.

#### Segurança da Web, Protocolos e Criptografia
A Segurança da Web foca na proteção de dados transmitidos por navegadores e servidores.

- **Protocolos:**
-- **O HTTPS (Hypertext Transfer Protocol Secure)**
É o protocolo de comunicação da Web que utiliza o SSL/TLS para criptografar a comunicação, garantindo que os dados transmitidos entre o navegador do usuário e o servidor sejam privados e íntegros.
-- **TLS/SSL (Transport Layer Security/Secure Sockets Layer):**
protocolos criptográficos que fornecem segurança de comunicação em uma rede. O SSL é o antecessor do TLS. Eles operam na camada de transporte e são responsáveis por estabelecer o canal seguro que o HTTPS utiliza.


- **Criptografia:**
É a conversão de dados em um código para evitar o acesso não autorizado. É fundamental para garantir a confidencialidade e integridade dos dados.

#### Importância da LGPD
A **LGPD (Lei Geral de Proteção de Dados)** no Brasil estabelece regras sobre a coleta, uso, processamento e armazenamento de dados pessoais. Sua importância reside em:

 1. **Proteção de Dados Pessoais:**
 Garante maior controle aos titulares sobre suas informações.
 2. **Segurança da Informação:**
 Exige que as empresas implementem medidas de segurança robustas, como a criptografia, para proteger os dados contra acessos não autorizados e incidentes.

## Parte 3 | Novas Tendências Tecnológicas

### Blockchain e Web 3.0
O **Blockchain** é um registro digital ***descentralizado e imutável*** que registra transações em múltiplos computadores.
Ele é a tecnologia fundamental por trás da **Web 3.0**, que busca criar uma internet mais transparente, segura e onde os ***usuários têm a propriedade de seus dados e ativos digitais.***

### IoT (Internet das Coisas)
A **IoT (Internet of Things)** é a rede de objetos físicos ("coisas") incorporados com sensores, software e outras tecnologias para conectar e trocar dados com outros dispositivos e sistemas pela Internet. Isso gera um volume massivo de dados e levanta novos desafios de segurança e rede.

### SDN (Software-Defined Networking)

O **SDN** é uma abordagem de arquitetura de rede que permite que o controle da rede seja desacoplado do hardware e seja programável. Isso simplifica o gerenciamento da rede, permitindo que os administradores **configurem, gerenciem e otimizem** os recursos de rede de forma centralizada e dinâmica.

### Machine Learning (ML)
O **Machine Learning (ML)**, um subcampo da IA, está sendo cada vez mais integrado em redes e segurança.
Na segurança, é usado para detectar anomalias e prever ataques **(detecção de intrusão baseada em ML)**. Em redes, otimiza o tráfego e a alocação de recursos de forma autônoma

### Inteligência Artificial (AI)
A **Inteligência Artificial (AI)** abrange o ML e outras técnicas para simular a inteligência humana. A AI é usada para automatizar a gestão de redes e a resposta a incidentes de segurança.

### AGI (Artificial General Intelligence)
A **AGI (Artificial General Intelligence)** refere-se a um tipo de IA hipotética que possui a capacidade de entender, aprender e aplicar sua inteligência para resolver qualquer problema que um ser humano possa resolver.
É o objetivo final da pesquisa em IA e promete transformar radicalmente a forma como as redes e a tecnologia são gerenciadas e operadas.