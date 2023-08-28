Obs: O ultimo octeto não pode ser 255, nem 0, retirando duas possibilidades.  
  
Classe A  
  
Primeiro octeto entre 1 ~ 126  
( Em binário, o primeiro bit do primeiro octeto é zero )  
Máscara Padrão: 255.0.0.0  
Ex: 10.|0.0.2  
255|0.0.2  
Possiblidades:2²⁴ - 2 =16.777.214  
Numero de redes: 128  
  
Classe B  
Primeiro octeto entre 128 ~ 191  
( Em binário, o primeiro bit do primeiro octeto deve ser 1 e o segundo bit 0)  
Máscara Padrão: 255.255.0.0  
Ex: 191.68.|0.13  
255.255.|0.0  
Possibilidades: 2^(16) - 2 = 65.534  
Número de redes: 16.384  
  
Classe C  
Primeiro octeto entre 192 ~ 223  
( Em binário, os dois primeiros bits devem ser 1 e o terceiro 0)  
Máscara Padrão: 255.255.255.0  
Ex: 192.168.0.|1  
255.255.255.0  
Possibilidades: 2^(8) - 2 = 254  
Número de redes: 2.097.152  
  
-------------------------------------------------------------------------  
  
Endereços Especiais  
  
Endereço Público: Usado na interner provido pela empresa que fornece internet.  
  
Endereço Privado: Usado em redes internas.  
  
Classe A: 10.0.0.0 ~ 10.255.255.255  
Classe B: 172.16.0.0 ~ 172.31.255.255  
Classe C: 192.168.0.0 ~ 192.168.255.255  
  
Endereço de Loopack: usado para teste 127.X.X.X  
  
Endereço de auto-configuração: 169.254.X.X  
Quando a Máquina está configurada para trabalhar com um servidor dhcp, mas não consegue acessa-lo, e ninguém configurou um ip manualmente para a mesma.