[<p style="font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](../enderecamento-ipv4/README.md)
---
### Endereçamento IPv4 - [Determinando Rede, Host e Broadcast ***Classe A***](https://www.youtube.com/watch?v=p2_kNrLBAXA&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=9)
---

### Grupos de IP

* **Todo IP**, faz parte de um dos grupos mencionados abaixo:

#### **Rede**
* É **primeiro** endereço de IP **possível** numa rede.
* É a parte do IP que ***identifica / nomeia*** a rede.  
**Exemplo**:  
Se um endereço IP for **192.168.0.13**, a parte **192.168.0** identifica a **rede**, e o **13** identifica o **dispositivo (host)**.  
Também no caso da rede exemplificada, o endereço de IP **192.168.0.0** é ***reservado***, sendo o ip **192.168.0.1** o primeiro endereço de IP **disponível**.

#### Observação sobre o endereço ***reservado***
O IP que está **no começo** do intervalo de endereços de uma rede (como o .0) é destinado a **identificar** a rede em si, e **não pode** ser designado a um dispositivo específico. Esta informação é utilizada no **processo de roteamento** e serve para mostrar **a qual rede** um pacote se relaciona, ao invés de ser um endereço alocado para **um host** (dispositivo) específico.

* O endereço **de rede é igual** para **todos** os dispositivos, sendo o endereço **de host** que os identifica.

----
#### **Host**
* É o endereço IP que identifica um **dispositivo específico** na rede.
* Cada host na rede tem um endereço IP **exclusivo**.

---
#### **Broadcast**
* É **último** endereço de IP **possível** numa rede.
* O endereço de broadcast serve para transmitir informações para **todos os dispositivos** que estão conectados em uma rede, incluindo **avisos** de roteamento, **alertas ou dados** que precisam ser **compartilhados amplamente**.
* Esse endereço de broadcast **é único** para **cada rede** ou **sub-rede** e é **definido pela máscara** de sub-rede.

---
### Como ***determinar*** os endereços de Rede, Host e Broadcast

#### Para um endereço de ***Classe A*** com ***máscara padrão*** (255.0.0.0)

* Primeiro passo, compreender os **componentes** do endereço IP **na sua classe** e montar a **tabela** de rede host e broadcast.
* Como citado acima, num IP de classe A, o **primeiro** (**8 bits**) determina a **rede**, enquanto os **três últimos** (**24 bits**) determinam o **host**.
* Como citado anteriormente, o endereço de **broadcast** é o **último** endereço de IP **possível** numa rede.
* Seguindo esse raciocínio e para facilitar o processo, faz sentido determinar **primeiro** o endereço de **rede**, depois o de **broadcast** e, dessa forma, os que estiverem **dentro do intervalo**, são os IP's **possíveis** nesta rede / sub-rede.

---
**Exemplo**:

**10.10.100.1**

| Rede | Host | Broadcast |
| --- | --- | --- |
| **10**.0.0.**0** | **10**.0.0.**1** até **10**.255.255.**254** | **10**.255.255.**255** |

---
### Observação sobre as classes ***D*** e ***E***

* As classes **D** e **E** do IPv4 **não seguem** a estrutura padrão de rede, host e broadcast, pois foram criadas para **finalidades específicas** que **não se encaixam** nesse modelo.
* A **classe D** é usada para **multicast** (envio de um **único pacote** para um grupo **específico** de dispositivos), **diferente** do **broadcast**, que envia **para todos**. 
* A **classe E** é reservada para pesquisa e testes, **sem uma função definida** dentro da **estrutura de rede, host e broadcast**.


---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
