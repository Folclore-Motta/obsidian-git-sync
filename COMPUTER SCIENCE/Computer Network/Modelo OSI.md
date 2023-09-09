# Definição

O 


| Camada | PDU |
| ---------| ------|
|7. Aplicação| Dados |
|6. presentação | Dados |
|5. Sessão | Dados |
|4. Transporte | Segmento |
|3. Rede | Pacote |
|2. Link de Dados | Quadro |
|1. Física | Bits |


Camada Aplicação:  
  
•Fornece interface de comunicação entre aplicações e serviços de rede.  
•Também define processos de autenticação de usuários nas aplicações.  
•Arquitetura cliente-servidor, habilita usuários (humanos ou sistemas) a acessarem recursos da rede.  
•A camada de aplicação é crucial, pois permite que aplicações sejam acessadas e executadas em ambiente de rede, incluindo a Web.  
  
Camada Apresentação:  
  
• Codificação de caracteres  
• Formatação de Dados  
• Comunicação entre sistemas diferentes  
• Segurança e privacidade nas transmissões de dados  
• Aumento de performance da transmissão  
• Processo de criptografia ou cifragem  
• Compreensão ( Diferente da compreensão no OS)  
  
Camada de Sessão:  
  
• Estabelecer, manter e terminar sessões: Permite que dois processos estabeleçam, usem e finalizem uma conexão.  
• Sincronização: Permite que os processos criem pontos de sincronização de dados. Assim, erros podem ser identificados com mais facilidade, e os dados podem ser re-sincronizados.  
• Controlhe de Diálogo: Os processos podem escolher iniciar a comunicação entre si em modos half-duplex, simplex ou full-duplex.  


  
* Bibiliografia *  
  
• RFC 1123 - [https://tools.ietf.org/html/rfc1123](https://tools.ietf.org/html/rfc1123)  
• Stevens,R. TCP/IP illustrated, Volume 1. Ed. Addison Wesley, 2000.  
• Siyan, K. S.; Parker, T. TCP/IP Unleashed. Ed. SAMS Publishing, 2002.  
• Forouzan, B.A. TCP/IP Protocol Suite, 4° edição Ed.McGraw-Hill, 2020  
• Murhammer; Atakan; Bretz; Pugh; Suzuki; Wood. TCP/IP Tutorial e Técnico - IBM Books. Makron Books

Comunicação e encapsulamente

Comunicação horizontal
Uma camada só consegue conversar com ela mesma, ou seja a camada 2 do destinatário só consegue se comunicar com a camada 2 do destinatário esse comunicação ocorre de forma virtual. Essas informações denominadas **cabeçalhos**.

Cada camada adicionara um novo cabeçalho ao dado que será enviado, e esse processo e chamado de **encapsulamento**

Esse procedimento acontece, repetidamente, até alcançar a camada 1 e a informação ser transmitida ao destino, onde ocorrerá o processo inverso. A informação subira, desencapsulando as informações, da camada 1 até o usuário do serviço.
Ao encapsular é criado o PDU
