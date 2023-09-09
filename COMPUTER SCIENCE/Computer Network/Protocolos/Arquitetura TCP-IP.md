A arquitetura foi batizada por TCP/IP por causa dos seus principais protocolos:
Transmission Control Protocol(TCP) e Internet Protocol(IP).

A arquitetura foi criada utilizando cinco camadas: [[Camada de Aplicação|Aplicação]], [[Camada de Transporte|Transporte]], [[Camada de Rede|Rede]], [[Camada de Enlace|Enlance]], [[Camada Física|Física]].


As funções das camadas de apresentação e sessão serão acumuladas pela camada de aplicação e as funções das camadas de enlace e física serão executadas pela camada de acesso à rede. Observe a relação entre os dois modelos a seguir.

Uma grande diferença que temos entre o modelo de referência [[Modelo OSI|OSI]] e a arquitetura TCP/IP é:

Modelo OSI
é baseado, principalmente, nas funcionalidades das camadas.

Arquitetura TCP/IP
Não ficou presa apenas nas funcionalidades, mas ampliou para o desenvolvimento de protocolos relativamente independentes e hierárquicos. A hierarquia baseia-se em um protocolo de nível superior é suportado pelos protocolos de nível inferior.

|Serviço| Protocolo | 
|---------| -------|
|Web| [[HTTP]], [[HTTPS]] |
|Correio Eletrônico| [[SMTP]], [[POP]] e [[IMAP]] |
|Nomes| [[DNS]] |
|Transferência de arquivos| [[FTP]] e [[TFTP]] |
|Áudio e vídeo em tempo real| [[RTP]] |
|Configurações atuomática de estações DHCP| [[DHCP]] |

Os protocolos apresentados são implementados por meio de softwares, que são executados nos diversos dispositivos computacionais, e podem estar associados a dois tipos principais de arquitetura:

# Cliente-Servidor
Na arquitetura cliente-servidor, como já evidencia o nome, existirá um cliente e um servidor. O cliente será executado por um usuário como nós e irá requisitar um serviço do servidor. Por exemplo, para o serviço Web, o cliente é o navegador que acessa determinado servidor, por exemplo, o servidor que está disponibilizando esse conteúdo.

## Par a par (peer-to-peer (P2P))
A arquitetura P2P foi pensada no emprego mínimo de servidores, caso exista algum. A ideia da arquitetura peer-to-peer é que os usuários possam trocar informações de forma direta. Esse tipo de arquitetura ficou muito conhecida com os programas de compartilhamento de arquivos, mas também pode ser utilizada em outras situações, como em um chat entre duas pessoas.

# Internet
A camada Internet ou simplesmente camada de rede tem por objetivo permitir que os dados injetados na rede pela máquina de origem possam alcançar destino. O principal protocolo da camada de rede é o IP (Internet Protocol).

TCP (Transmission Control Protocol)
é um protocolo orientado à conexão e confere confiabilidade

UDP (User Datagram Protocol)
