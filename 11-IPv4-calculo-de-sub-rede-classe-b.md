### Endereçamento IPv4 - [Cálculo de Sub-rede ***Classe B***](https://www.youtube.com/watch?v=X9desSE4lnk&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=12)
---

### Cálculo de sub-rede e identificação de hosts e broadcast para o IP classe B ***172.16.40.30 - 255.255.192.0***:

#### Observação sobre características das sub-redes - classe B
* Em não se usando a **máscara padrão** de classe B, ou seja, 255.255.0.0, toda **sub-rede** possuirá um **octeto misto (1 e 0)** no **terceiro** octeto.
* Lembrando que, para ser uma máscara de sub-rede **válida**, no endereço **inteiro**, todos **os bits 1** precisam ficar **à esquerda** e os bits 0 **à direita**.

---
#### ***Passos para o cálculo de sub-redes classe B***:
* Observar **a máscara** e identificar o **octeto misto**. No caso da **máscara exemplificada** (255.255.192.0), **192**.
* Calcular o **salto** subtraindo **o octeto misto** de **256**. Neste caso, 256 - 192 = **64**.
* Tendo o salto calculado, como se trata de um IP classe B (172.16.40.30), a alteração **nunca** ocorre onde há o 255 correspondente **na máscara**. A padrão é 255.255.**0.0**, mas no caso do exemplo, 255.255.**192.0**.
* Como o octeto misto é o terceiro, **é neste** que o salto ocorrerá. 
* Calcular **em primeiro** a rede, **em segundo** o broadcast e **em terceiro** o intervalo de IP's válidos (hosts), conforme a tabela abaixo.

#### Observação sobre o uso do ***número 256*** no cálculo
* Como visto nos tópicos em arquivos anteriores, o número 256 **não pode ser usado** em endereços IP. Afinal a contagem se **inicia em 0**, ou seja, **255 é o número máximo** para que 256 endereços **individuais** sejam possíveis.
* O uso deste no tópico acima é em função **apenas** do cálculo.

---
#### Tabela demonstrando os ***valores calculados*** de sub-redes, hosts e broadcast para o IP classe B ***172.16.40.30 - 255.255.192.0***:

| Sub-rede | Host | Broadcast |
| --- | --- | --- |
| 172.16.**0.0** | 172.16.**0.1** até 172.16.**63.254**| 172.16.**63.255** |
| 172.16.**64.0** | 172.16.**64.1** até 172.16.**127.254** | 172.16.**127.255** |
| 172.16.**128.0** | 172.16.**128.1** até 172.16.**191.254** | 172.16.**191.255** |
| 172.16.**192.0** | 172.16.**192.1** até 172.16.**255.254** | 172.16.**255.255** |
| 172.16.**256.0**  (apenas para cálculo)|  | **não utilizada** |

* Observando **o octeto misto** na **máscara** (255.255.**192**.0), buscando este nesta mesma **posição**, não o seu **mesmo valor** e conforme tabela calculada, o IP 172.16.**40**.30 está na **primeira** sub-rede (172.16.**0**.0). Pois esta comporta os hosts com **octetos finais** de  **x.x.0.1** até **x.x.63.254**, sendo o seu **broadcast** o 176.16.63.255.

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
[**Curso em Vídeo** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)  
[**Cisco** - Entender as quantidades de host e sub-rede](https://www.cisco.com/c/pt_br/support/docs/ip/routing-information-protocol-rip/13790-8.html)  
