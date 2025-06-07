[<p style="font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](../enderecamento-ipv4/README.md)
---
### Endereçamento IPv4 - [Sub-redes de tamanho variável (VLSM)](https://www.youtube.com/watch?v=TJMDckXt3Mo&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=14)
---

### Máscara de Sub-rede de Comprimento Variável - VLSM (Variable Length Subnet Masking):

#### Compreendendo a necessidade de uso de uma VLSM
* A VLSM permite criar sub-redes com saltos de comprimento variável. Dessa forma, caso seja necessário criar sub-redes que pertençam a uma rede maior, seja de classe A, B ou C, é possível segmentar essas em sub-redes menores, utilizando máscaras que permitam segmentar a rede e utilizar **apenas** a quantidade mais próxima do número de hots necessários. Essa técnica permite **subutilizar o mínimo possível** de endereços de hosts, não utilizando **saltos** de **tamanho único** entre as sub-redes.

#### Lembrando a quantidade de hosts disponíveis nas classes de rede A, B e C

| Classe | Intervalo do ***primeiro*** octeto | Quant. Hosts (IP's) |
| --- | --- | --- |
| **A** | 0 a 127 | 16.777.216 |
| **B** | 128 a 191 | 65.536 |
| **C** | 192 a 223 | 256 |

---
#### Subdividindo uma rede ***classe C*** em 4 sub-redes de tamanhos ***diferentes***

#### Exemplo:
**192.168.0.0/24** (Rede de classe C com **até 256** endereços de host)

#### Definindo o tamanho ***necessário*** para cada sub-rede no ***exemplo***

| Sub-rede | Hosts necessários
| --- | --- |
| Sub-rede 1 | **20** |
| Sub-rede 2 | **60** |
| Sub-rede 3 | **120** |
| Sub-rede 4 | **6** |

---
* **Primeiro passo**: Observar o **limite** de hosts pela classe **da rede que será segmentada**. Sendo, no exemplo, uma rede de **classe C** e lembrando que endereços de **rede e broadcast** são **reservados**, esta permite **254** endereços únicos de host **utilizáveis**.

#### Observação sobre o limite de hosts únicos para cada classe de rede

* Caso a necessidade **total** de hosts seja **maior que** os 254 possíveis, uma hipótese seria **alterar a rede maior** para uma classe que comporte mais hosts únicos ou **criar várias** redes classe C modificando o IP. Exemplos: 192.168.0.0, 192.168.1.0, 192.168.2.0, etc.

---
* **Segundo passo**: Organizar as demandas de hosts de forma **decrescente**.

| Sub-rede | Hosts necessários
| --- | --- |
| Sub-rede 3 | **120** |
| Sub-rede 2 | **60** |
| Sub-rede 1 | **20** |
| Sub-rede 4 | **6** |

---
* **Terceiro passo**: Criar máscaras de sub-rede que **mais se aproximem** da demanda real.

### Sub-rede 3 (120 hosts)

* A forma de se calcular essa proximidade é lembrar as bases 2 **em binário**.
* Considerando as bases 2 possíveis numa sub-rede, 128 é o mais **próximo** para o preenchimento do octeto da máscara em função da demanda (120 hosts).
* Se **128 hosts são possíveis**, excluindo os **2 reservados** (rede / broadcast), temos 126 endereços de host **aplicáveis** nesta sub-rede.
* Os 6 hosts restantes **não podem** ser utilizados para outras sub-redes. Estas terão **máscara própria**, além de a demanda ser por **4 sub-redes**.

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

* A máscara de rede que comporta o número **mais próximo** de **120 hosts** é 255.255.255.**128** (128 totais e 126 hosts utilizáveis).

#### Observação sobre o cálculo

* Dado o número 128 **em binário**, basta calcular 2 elevado ao **número de zeros** existentes. No caso do 128 (10000000), **2<sup>7</sup>**.
* **Não esquecer** que, para ser uma máscara de rede **válida**, os octetos desta **necessáriamente** precisam organizar **todos** os números 1 **à esquerda** e os números 0 **à direita**.

### Sub-rede 2 (60 hosts)

* O número mais próximo dos **60 hosts** requisitados é 64. Ocorre que, 64 **em binário** é 1000000 (7 bits), para **completar o octeto**, colocaríamos **um 0 à esquerda**. No entanto, dado essa sequência **não respeitar** a regra da organização de 1 e 0, 255.255.255.64 é uma máscara de rede padrão **inválida** para a classe C.
* Lembrando a observação sobre 2 elevado ao **número de zeros** teríamos **2<sup>6</sup>**. Para **completar o octeto**, colocamos **dois números 1 à esquerda** e temos **11000000**.

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |

* 11000000 **em decimal** é **192**, logo a máscara de rede válida para **60 hosts** é 255.255.255.**192** (64 totais e 62 hosts utilizáveis).

#### Observação sobre como ***facilitar*** o cálculo

* Como são todos os 1 à esquerda e todos os 0 à direita, basta **somar as bases 2** dos bits 1 e temos o valor correspondente para a máscara (128 + 64 = 192).

### Sub-rede 1 (20 hosts)

* Para 20 hosts, o mais próximo é 32 (**2<sup>5</sup>**).

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 0| 0 | 1 | 0 | 0 | 0 | 0 | 0 |

* Como 32 em binário é 100000 (6 bits), **não podendo** completar o octeto com **0 à esquerda** e lembrando da **soma dos bits 1**, o número válido para uma máscara de rede **padrão** classe C, seria **224** (11100000).

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 |

* Dessa forma, a máscara de rede padrão classe C que atende a demanda de **20 hosts** é 255.255.255.**224** (32 totais e 30 hosts utilizáveis).

### Sub-rede 4 (6 hosts)

* Para 6 hosts, o mais próximo é 8 (**2<sup>3</sup>**).

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 0| 0 | 0 | 0 | 1 | 0 | 0 | 0 |

* Como 8 em binário é 1000 e **não podendo** completar o octeto com **0 à esquerda**, novamente lembrando da **soma dos bits 1**, o número válido para uma máscara de rede **padrão** classe C, seria **248** (11111000).

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 |

* Assim, a máscara de rede padrão classe C que atende **exatamente** a demanda de **6 hosts** é 255.255.255.**248** (8 totais e 6 hosts utilizáveis).

---

### Tabela de redes e suas respectivas máscaras

| Sub-rede | Demanda | Hosts totais | Hosts Utilizáveis | Máscara |
| --- | --- | --- | --- | --- |
| Sub-rede 3 | **120** | 128 | **126** | 255.255.255.**128** |
| Sub-rede 2 | **60** | 64 | **62** | 255.255.255.**192** |
| Sub-rede 1 | **20** | 32 | **30** | 255.255.255.**224** |
| Sub-rede 4 | **6** | 8 | **6** | 255.255.255.**248** |

* A **vantagem** do VLSM é que todas essas sub-redes estarão utilizando **a mesma rede**, no caso **192.168.0.0**.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)  
[**Cisco** - Entender as quantidades de host e sub-rede](https://www.cisco.com/c/pt_br/support/docs/ip/routing-information-protocol-rip/13790-8.html)  
