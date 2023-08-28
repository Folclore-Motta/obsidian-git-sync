Switch - Operação

- Switches analisam apenas o cabeçalho da camada de enlace para determinar o que fazer com um frame que entra por uma de suas portas.

- Para saber o que fazer com o frame, os switches mantém uma tabela interna, chamada "Tabela MAC" que armazena a informação do endereço MAC associado à uma determinada porta do switch.

- Esta tabela é montada dinamicamente, assim que um dispositivo recém conectado à porta do switch faz sua primeira transmissão - Este processo é conhecido como " Learning Process"

- Quando um MAC desconhecido é solicitado o switch manda para todas as portas menos a porta do qual o frame foi enviado