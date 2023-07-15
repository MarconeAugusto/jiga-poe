# JIGA PoE

![JIGA](/Fotos/JIGA_PoE_10.jpg)

JIGA Confeccionada para avaliar a capacidade máxima de potência PoE que pode ser entregue pelo equipamento, diretamente pelas portas PoE, utilizada para auxiliar no desenvolvimento de Switches PoE.

### **Testes**

- Testes realizados nas etapas de validação e verificação

	> **Teste de fontes PoE:** Com a ajuda de cargas, seja eletrônica ou variável(mecânica), é possível extrair a capacidade máxima que a fonte pode entregar.

	> **Teste de portas PoE:** Nesse caso, conseguimos com ajuda do testador PoE ([PoE Pro](https://www.trend-networks.com/product/poe-pro/)), verificar a classe (0 - 8), os pares utilizados na alimentação, o tipo (af/at/bt), e a potência máxima que pode ser entregue por cada porta.

	> **Teste de barramento:** Quando possível, a equipe devia recorrer a adaptações técnicas para auxiliar na execução dos testes.

	> **Testes de compatibilidade:** Testes realizados com os principais equipamentos intelbras que utilizam a tecnologia PoE para alimentação, principalmente câmeras IP.


### **Motivação**

Mesmo com todos os testes que são realizados, não havia uma forma de verificar se o switch entregava ao menos a potência nominal descrita.

### **Desenvolvimento**

A JIGA tem a capacidade de extrair, por porta, aproximadamente 15 W de potência, nas 12 portas disponíveis, totalizando **180 W**. Existe a possibilidade de extrair valores inferiores a 15 W, através da porta **1**, utilizando uma carga variável.

![JIGA](/Fotos/JIGA_PoE_02.jpg)

Para isso devemos utilizar o DIP SWITCH, para selecionar a carga utilizada para o teste, conforme descrito, a chave está na posição “LIGADA” quando pressionada para baixo.

> Atenção: A chave é composta por 4 switches, e para o seu funcionamento devem ser ativados ao menos dois, como por exemplo, nas imagens a seguir.

|Frontal					|Superior				|
|---------------------------|-----------------------|
|![Chave de Seleção de Carga](/Fotos/JIGA_PoE_07.jpg)|![Chave de Seleção de Carga](/Fotos/JIGA_PoE_06.jpg)|


> Se as duas chaves mais próximas da palavra “CARGA FIXA”, estiverem ativadas, a porta 1 extrairá aproximadamente 15 W de potência, por outro lado, se as duas chaves mais próximas de “CARGA EXTERNA” estiverem ativadas, a extração de potência será controlada através da carga variável que deve ser conectada ao conector (CN1) próximo ao DIP SWITCH.

> A tensão de saída no conector (CN1), será de aproximadamente 12 Volts.

Para verificar a tensão que está sendo entregue pelo DUT, as vias do cabo UTP da porta 1, estão interligados aos conectores próximos as portas RJ45. Seguindo a seguinte distribuição.

|Conector                       |Vias                         |
|-------------------------------|-----------------------------|
|`CN1`           				|1 e 2				          |
|`CN2`           				|3 e 4		    		      |
|`CN3`           				|5 e 6		          		  |
|`CN4`           				|7 e 8		  		          |

![JIGA](/Fotos/JIGA_PoE_08.jpg)

Os cabos UTP que interligam os *Spliters* as portas RJ45, foram montados sem a "capa", para que com a ajuda de um alicate amperímetro possa ser aferida a corrente nos pares do cabos UTP.

Com isso, podemos aferir a potência entregue pelo Switch, através da seguinte fórmula:

P = V x I

> P = Potência Elétrica dissipada;

> V = Tensão Elétrica entre os terminais;

> I = Corrente Elétrica.


Para utilizar a JIGA PoE, favor ligar os Coolers para auxiliar na refrigeração dos resistores de potência.

![JIGA](/Fotos/JIGA_PoE_03.jpg)

