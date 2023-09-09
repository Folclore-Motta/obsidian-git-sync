# Camada de Transporte
Garantir a entrega de processo a processo de todos os dados enviados pelo usuário que por sua vez podem chegar em ordem diferente se enviados através de [[Datagrama]]

Sendo uma das mais complexas dentro da estrutura do modelo OSI. Para garantir que as mensagens da camada de aplicação sejam entregues corretamente, diversão funções são necessárias.

# Segmentação 
A camada de transporte receberá os dados originados na camada de sessão (PDU da camada de sessão). e irá dividi-lós em pedaços,
segmentos de dados (PDU da camada de transporte), que possam ser enviados e, na camada de transporte de destino, irá remontá-los na ordem correta. Para isso, será necessário estabelecer números de sequência para garantir que, independentemente da ordem de chegada, os dados sejam remontados na ordem correta.

# Controle de erros fim a fim
A camada de transporte verificará se ocorreram erros de comunicação fim a fim, ou seja, entre os processos da camada de aplicação. Na origem, serão adicionadas informações que permitam identificar no destino se durante o tráfego pela rede ocorreu algum erro e, possivelmente, corrigi-lo.

# Controle de fluxo
A camada de transporte será encarregada de evitar que o processo na origem sobrecarregue o processo no destino.

# Controle conexão
A camada de transporte pode ser orientada ou não à conexão. No serviço orientado à conexão, a camada de transporte será responsável por estabelecer a conexão entre os processos de origem e destino.

# Endereçamento do ponto de acesso ao serviço
Em dispositivo, normalmente, estão em andamento diversos tipos de serviços executados por vários processos e não apenas um. A camada de transporte será responsável por fazer a entrega para o processo correto e, para isso, será utilizado o chamado endereço de porta. Ele indicará o serviço correto que deverá receber os dados.

# Controle de congestionamento
No mundo real, as máquinas não estão diretamente conectadas, ou seja, não há uma comunicação ponto a ponto direta. Entre a máquina de origem e de destino existem diversos outros dispositivos cuja finalidade é fazer a informação ir de um ponto a outro. Como esses equipamentos transmitirão dados de diversas outras origens, poderá haver uma sobrecarga desses dispositivos. A camada de transporte será responsável por monitorar esse congestionamento e, possivelmente, tratá-lo.