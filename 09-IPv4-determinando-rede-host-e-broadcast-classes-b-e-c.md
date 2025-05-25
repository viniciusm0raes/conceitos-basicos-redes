### Endereçamento IPv4 - [Determinando Rede, Host e Broadcast ***Classes B e C***](https://www.youtube.com/watch?v=9KmZ5wxMfys&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=10)
---

### Como ***determinar*** os endereços de Rede, Host e Broadcast

#### Para um endereço de ***Classe B*** com ***máscara padrão*** (255.255.0.0)

* Primeiro passo, compreender os **componentes** do endereço IP **na sua classe** e montar a **tabela** de rede host e broadcast.
* Num IP de classe B, os **dois primeiros** octetos (24 bits) determinam a **rede** e os **dois últimos** (24 bits) determinam o **host**.
* Como citado anteriormente, o endereço de **broadcast** é o **último** endereço de IP **possível** numa rede.
* Seguindo esse raciocínio e para facilitar o processo, faz sentido determinar **primeiro** o endereço de **rede**, depois o de **broadcast** e, dessa forma, os que estiverem **dentro do intervalo**, são os IP's **possíveis** nesta rede / sub-rede (**classe B**).

---
**Exemplo 1**:  
**172.16.40.30**

| Rede | Host | Broadcast |
| --- | --- | --- |
| **172.16**.0.0 | 172.16.**0.1** até 172.16.**255.254** | 172.16.**255.255** |

---
#### Para um endereço de ***Classe C*** com ***máscara padrão*** (255.255.255.0)

* Num IP de classe C, os **três primeiros** octetos (24 bits) determinam a **rede** e o **último** (8 bits) determina o **host**.
* Também seguindo esse raciocínio e para facilitar o processo, determinar **primeiro** o endereço de **rede**, depois o de **broadcast** e, dessa forma, os que estiverem **dentro do intervalo**, são os IP's **possíveis** nesta rede / sub-rede (**classe C**).

---
**Exemplo 2**:  
**192.168.10.1**

| Rede | Host | Broadcast |
| --- | --- | --- |
| **192.168.10**.0 | 192.168.10.**1** até 192.168.10.**254** | 192.168.10.**255** |

---		
**Fontes**:  
[**Curso em Vídeo** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
