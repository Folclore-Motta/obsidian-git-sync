File transfer protocol
Protocolo para transferência de arquivos entre dois hosts - um cliente e um servidor, baseado em conexão IP e usando TCP.

• Protocolo da camada de aplicação.
• Portas usadas 20 e 21
• Os dados são transferidos pela por 20 e a  porta 21 transmite informações de controlhe

• Necessário autenticação ou não, depende da configuração do servidor
• Da para criptografar os dados com SSL/TLS, na forma de FTPS, ou ainda usando o STFP ( SSH File Transfer Protocol ).

                        Modos de Conexão
                        
• Um modo de conexão determina como a conexão de dados é estabelecida.
• O cliente cria uma conexão TCP a partir de uma porta aleatória com a porta 21 do servidor FTP.
• FTP pode operar em dois modos: Ativo ou Passivo

                           Modo ativo
                        
• No modo ativo (active), o cliente escuta conexões de dados que chegam do servidor em uma porta informada
• O servidor inicia um canal de dados a partir de sua porta 20.
• Problemática se o cliente estiver atrás de um firewall ou roteador NAT

                            Modo passivo

• O cliente usa a conexão de controlhe para enviar um comando PASV ao servidor e recebe um endereço IP e número de porta aleatória como resposta, que serão usadas para iniciar um canal de dados a partir de outra porta aleátoria no cliente.
• Usada geralmente quando o cliente não consegue receber conexões TCP de entrada, por exemplo por conta de um firewall na rede.

              Modo de Representação

Quando os dados são transferidos pela rede, podem ser usados dois tipos principais de apresentação.

• Modo ASCII - Texto
• Modo binário ("imagem") - Para arquivos em geral. Dados são transmitidos byte por byte

                  Modos de transfêrencia

Os dados podem ser transferidos de três modos:

• Modo Stream ( Fluxo ) - Dados enviados em um fluxo contínuo. Todo o processamento é realizado.
• Modo Block (Bloco) - Os dados são dividos em vários blocos pelo FTP, e então repassados ao TCP para a transmissão.
• Modo Comprimido ( Compressed ) - Os dados são comprimidos usando um algoritmo, como o RLE ( Run-Length Enconding )

                            FTP Anônimo

• Um servidor pode oferecer o serviço de FTP Anônimo, no qual os usuários se loguem com uma conta de nome anonymous, sem emprego de senha - o servidor muitas vezes pede o e-mail do usuário como "senha". Porém, nenhuma vetificação é realizada.
• No geral, é empregada por servidores que armazenam atualizações de software para os clientes baixarem.

                      Segurança do FTP

• O FTP não foi feito para ser um protocolo seguro, e está sujeito a diversos tipos de ataques, como ataques de força bruta, captura de pacotes, spoofing, entre outros.
• Além disso, o FTP não criptografa os dados transmitidos, incluindo nomes de usuário e senhas.
• Isso pode ser remediado usando-se uma versão segura do FTP, como o FTPS, ou ainda transmitindo os dados FTP por meio de túnelamento SSH ou uma VPN ( Mais comum ).

