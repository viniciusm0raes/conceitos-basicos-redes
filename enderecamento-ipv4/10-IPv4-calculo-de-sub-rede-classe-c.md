[<p style="text-align:right; font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](../readme.md)
---
### Endereçamento IPv4 - [Cálculo de Sub-rede ***Classe C***](https://www.youtube.com/watch?v=I8srQHKA3ig&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=11)
---

### Cálculo de sub-rede e identificação de hosts e broadcast para o IP classe C - ***220.168.0.20/26***:

#### Observação sobre características das sub-redes - classe B
* Em não se usando a **máscara padrão** de classe C, ou seja, 255.255.255.0, toda **sub-rede** possuirá um **octeto misto (1 e 0)** no **quarto** octeto.
* Lembrando que, para ser uma máscara de sub-rede **válida**, no endereço **inteiro**, todos **os bits 1** precisam ficar **à esquerda** e os bits 0 **à direita**.

---
#### ***Primeiro passo***: Observar ***a máscara*** e identificar as ***sub-redes*** possíveis
* Converter a máscara **CIDR** para máscara **padrão**.
* Como a máscara padrão de um ip **classe C** é **255.255.255.0**, **já temos 24 bists**.
* Ocorre que, se **/26** não temos uma máscara **padrão** e que **nesta máscara** de rede **existem 26 bits 1**, sendo que estes precisam ser **separados** em grupos de **octetos (8bits)** e convertendo estes **para decimal**, temos a **máscara de rede** correspondente.

---
* Seperando **os 26 bits** em **octetos**

| Bits | 11111111 | 11111111 | 11111111 | 11000000 |
| --- |  --- | --- | --- | --- |

---
* Convertendo para ***decimal***

| Bits | 11111111 | 11111111 | 11111111 | 11000000 |
| --- |  --- | --- | --- | --- |
| **Máscara** | 255 | 255 | 255 | 192 |

* Como em **todo IP de classe C**, a **máscara padrão** é **255.255.255.0**, a variação de sub-rede acontece na **mesma direção** do **octeto misto**, ou seja, o octeto que **possui 1 e 0**, no caso da máscara **do exemplo, 192**.
* Determinar o **salto**, ou seja, a **variação de ip's** dentro de **cada** sub-rede.
* O salto é determinado pela **subtração** de **256** menos o valor do **octeto misto**, nesse caso, **256 - 192 = 64**.
* Como essa subtração (o salto) resulta em 64, esse é o número **máximo** de ip's disponíveis **em cada sub-rede**.
* Dividir em sub-redes em função do salto, **neste caso** 64.
* Tendo o salto calculado, como se trata de um IP classe C (220.168.0.20), a alteração **nunca** ocorre onde há o 255 correspondente **na máscara**. A padrão é 255.255.255.**0**, mas no caso do exemplo, 255.255.255.**192**.
* Como no caso da classe C os **três primeiros** octetos identificam a rede, estes **se repetirão**.
* O **último** octeto é que será calculado **em função** do salto.
* Em cada sub-rede, o **menor** número **possível** identifica esta.
* Considerando **salto**, a soma para **cada sub-rede** deve ir até o valor **máximo**, ou seja, 256 (atentar para a **observação** abaixo). Logo, para uma **máscara CIDR /26**, serão possíveis **4 sub-redes**.

#### Observação sobre o uso do ***número 256*** no cálculo
* Como visto nos tópicos em arquivos anteriores, o número 256 **não pode ser usado** em endereços IP. Afinal a contagem se **inicia em 0**, ou seja, **255 é o número máximo** para que 256 endereços **individuais** sejam possíveis.
* O uso deste no tópico acima é em função **apenas** do cálculo.

---
#### ***Segundo passo***: Observar ***a máscara*** e identificar os endereços de ***broadcast*** possíveis
* O **broadcast**, é identificado pelo **maior** número possível dentro de **cada** sub-rede.
* O broadcast é calculado pelo valor do **último** octeto da **próxima** sub-rede **menos 1**.

---
#### ***Terceiro passo***: Observar ***a máscara*** e identificar os endereços de ***hosts*** possíveis
* O **primeiro** endereço de **host** possível é calculado pelo valor do **último octeto** da sub-rede **mais 1**.
* O **último** endereço de **host** possível é calculado pelo valor do **último octeto** do broadcast **menos 1**.
* Calcular **em primeiro** a rede, **em segundo** o broadcast e **em terceiro** o intervalo de IP's válidos (hosts), conforme a tabela abaixo.
---
#### Tabela demonstrando os ***valores calculados*** de sub-redes, hosts e broadcast para o IP classe C ***220.168.0.20/26***:

| Sub-rede | Host | Broadcast |
| --- | --- | --- |
| 220.168.0.**0** | 220.168.0.**1** até 220.168.0.**62**| 220.168.0.**63** |
| 220.168.0.**64** | 220.168.0.**65** até 220.168.0.**126** | 220.168.0.**127** |
| 220.168.0.**128** | 220.168.0.**129** até 220.168.0.**190** | 220.168.0.**191** |
| 220.168.0.**192** | 220.168.0.**193** até 220.168.0.**254** | 220.168.0.**255** |
| 220.168.0.**256** (apenas para cálculo)|  | **não utilizada** |

* Observando **o octeto misto** na **máscara convertida** (255.255.255.**192**), buscando este nesta mesma **posição**, não seu **mesmo valor** e conforme tabela calculada, no **intervalo entre as sub-redes**, o IP 220.168.0.**20** se encontra na **primeira** sub-rede (220.168.0.**0**). Pois esta comporta os hosts com **octetos finais** de **x.x.x.1** até **x.x.x.62**, sendo o seu **broadcast** o 220.168.0.63.

#### Observação sobre sub-redes / broadcast das classes
* Nas **subredes**, colocados os números **até o octeto misto**, os demais são completados **com 0**.
* No **broadcast**, colocados os números **até o octeto misto**, os demais são completados **com 255**.
* No intervalo **de hosts**, os **válidos** vão do IP da subrede **mais 1** até o IP do broadcast **menos 1**.
* Para identificação de **a qual subrede** pertence o IP, observar **o octeto misto** e em qual intervalo **este se encontra**.

---
#### Observação sobre os IP's ***disponíveis*** para ***Hosts***
* Lembrando das informações em arquivos anteriores, **nenhum** dispositivo (host) pode utilizar **como IP** tanto os valores **de (sub)rede**, quanto os **de broadcast**.
* Estes valores são destinados a **identificação** (rede) e alcance de **todos os dispositivos** (broadcast) nesta (sub)rede.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Entender as quantidades de host e sub-rede](https://www.cisco.com/c/pt_br/support/docs/ip/routing-information-protocol-rip/13790-8.html)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)  
