Uma Sub-rede é uma divisão lógica de uma rede IP. Realizar a subdivisão de uma rede grande em redes menores permite diminuir o tráfego de rede, simplificar a administração e aumentar a performance dessa rede. Como por exemplo menos pacotes de broadcast circulando.  
  
Os Hosts que pertecem a uma sub-rede são endereçados com um grupo de bit mais significativo comum e idêntico em seus endereços IP. Assim, ocorre uma divisão lógica do IP, em dois campos, um endereço de rede ( prefixo de roteamento ) e um endereço ( identificador ) de host. Esse endereço de host indentifica uma interface de rede específica.

Máscara  
  
Em computação, máscara é um dado utilizado para realizar operações de lógica binária, no geral em campos de bit. Ao utilizarmos uma máscara, um ou mais bits em um byte ( ou outro agrupamento de bits ), pode ser ativado, desativado ou ter seu valor lógico invertido, dependendo da operação lógica aplicada.  
  
As operações lógicas mais comuns aplicadas em máscaras são as operações AND, OR, NOT, e XOR.  
  
Mascara de Sub-Rede  
  
Uma máscara de sub-redes tem a função de identificar em um endereço IPv4 qual porção representa o endereço de rede e qual porção representa o endereço de host. A máscara se assemelha a um endereço IPv4, ou seja, possui 4 bytes dividos por pontos em porções de 8 bits (octetos). A parte dos bits constituída por valores "1" representa qual parcela de um endereço IP serão vistos com endereço de rede e os bits que são todos zeros, representam o endereço de host.  
  
É usada para dizer aos sistemas finais ( incluindo roteadores e outros hosts ) na rede quantos bits do endereço IP são usados para a identificação da rede e da sub-rede. Esses bits são chamados de Prefixo de Rede Estendido. Os bits restantes identificam os hosts dentro da sub-rede.  
  
Os bits da máscara que identificam o número da rede ( e sub-rede ) são ajustados em 1 e os bits do host, em 0. Assim, trata-se de uma máscara de bit que quando aplicada por meio de uma operação lógica AND em um endereço IP na rede, retorna o endereço de rede ( prefixo roteamento ) ou de sub-rede.ji