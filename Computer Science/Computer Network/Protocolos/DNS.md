• Domain Name System / Sistema de Nomes de Domínio.  
• Traduz nomes legíveis por humanos em endereços IP, utilizados pelos computadores.  
• Assim, só precisamos nos lembrar de "[www.archlinux.org](http://www.archlinux.org)", em vez do IP do site.  
• Basicamente, é um banco de dados de informações sobre hosts.  
• É um sistema hierárquico  
• Banco de dados distribuído  
• 13 Clusters de servidores-raiz (root servers), a partir de onde podemos encontrar quaisquer domínios do mundo.  
• Há centenas de domínios top-level genéricos (gTLDs), como .com, .org, .edu, etc.  
• Cerca de 275 domínios de nível superior para códigos de país (ccTLDs), como .br, .ar, .fr, .jp, etc.  
• Seus nomes são [a.root-servers.net](http://a.root-servers.net) até [m.root-servers.net](http://m.root-servers.net) ( podemos pinga-los a fim de saber o seu ip )  
  
FQDN  
  
• "Fully Qualified Domain Name"  
• Nome completo de um domínio  
• Hierarquia completa de um dispositivo, como um servidor ou máquina cliente ( em uma rede local ) ex: [www.archlinux.org](http://www.archlinux.org)  
• Sequência de rótulos de um nó até a raiz ( root ), separados por pontos.  
  
Nameservers  
  
• "Servidor de Nomes"  
• Programas que armazenam informações sobre o namespace do domínio.  
• No geral, possuem informações completas sobre uma parte do namespace, chamada de Zona, que é carregada a partir de um arquivo de ou de outro nameserver  
• Um nameserver é Autoritativo para essa Zona  
Tipos de Nameservers  
  
• Primario: lê os dados de uma zona a partir de um arquivo em seu host.  
• Secundário: Obtém os dados da zona apartir de outro servidor de nomes autoritativo para a Zona, chamadamo de Servidor Mestre, que geralmente é o servidor primário ( mas nem sempre ).