[<p style="text-align:right; font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](readme.md)
---
### Endereçamento IPv4 - [IPs Restritos ou Privados e IPs Reservados](https://www.youtube.com/watch?v=a1OSFX6bZPY&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=3)
---

#### Diferenciação de uso entre as classes IP

* As classes A, B e C são de IP's usados na internet, além de redes internas, com intervalos definidos como demonstrados na tabela abaixo.
* As classes D e E são endereços das chamadas **redes especiais**.
* A classe D é destinada a endereços de **multicast**.
* A classe E é usada para testes de novas tecnologias. 
* Os testes de novas tecnologias são efetuados numa rede controla para verificar a **viabilidade / funcionamento** destas.
---
#### Intervalos de octetos dos endereços IP em cada uma das classes

| Classe | Intervalo do ***primeiro*** octeto | Quant. IP's | Observação |
| --- | --- | --- | --- |
| **A** | 0 a 127 | 16.777.216 | endereços de host (dispositivos) |
| **B** | 128 a 191 | 65.536 | endereços de host (dispositivos) |
| **C** | 192 a 223 | 256 | endereços de host (dispositivos) |
| **D** | 224 a 239 | não são hosts de endereços **individuais** | Multicast |
| **E** | 240 a 255 | não são hosts de endereços **individuais** | Teste de novas tecnologias |

---

#### Métodos de ***transmissão*** de dados numa rede de computadores

* Os métodos de trasmissão são dividos / descritos conforme a tabela abaixo:

| Método | Funcionamento |
| --- | --- |
| **Unicast** | trasmissão para um **único** host numa mesma rede |
| **Multicast** | trasmissão para **múltiplos** hosts numa mesma rede |
| **Broadcast** | trasmissão para **todos** os hosts numa mesma rede |
| **Anycast** | trasmissão para **qualquer** host. Efetuada ao destinatário **mais próximo** da rede, sem precisar de autorização |

#### Observação sobre o ***anycast***

* O **anycast** é principalmente aplicado para **aprimorar a distribuição** de conteúdo e **aumentar a disponibilidade** de serviços, especialmente **em redes amplas**. Essa técnica possibilita que diversos servidores, situados em locais distintos, utilizem **um único endereço IP**, fazendo com que o tráfego seja encaminhado para o servidor **mais próximo**. Isso resulta na **diminuição da latência**, melhorando a experiência do usuário.

---
#### Endereços de IP Restritos / Privados e Reservados (RFC 1918)

* IP's restritos / privados são os **intervalos** de endereços IP que **podem ser usados** em redes **privadas** e que **não são roteáveis** na internet **pública**.


#### Observação sobre ***RFC (Request for Comments)***

* Um RFC consiste em um **documento técnico** que detalha especificações, protocolos, normas e sugestões relacionadas à Internet. Esses documentos são elaborados e atualizados pela **Internet Engineering Task Force (IETF)**. Eles constituem a **fundação das tecnologias** da Internet, abrangendo áreas como roteamento, endereçamento e métodos de transporte.
* A IETF (Internet Engineering Task Force) é um grupo internacional aberto, composto de técnicos, agências, fabricantes, fornecedores e pesquisadores, que se ocupa do **desenvolvimento e promoção de standards** para Internet, em estreita cooperação com o **World Wide Web Consortium (W3C)** e ISO/IEC, em particular TCP/IP e o **conjunto de protocolos Internet**. O IETF tem como missão **identificar e propor** soluções a questões/problemas relacionados à **utilização** da Internet, além de propor **padronização das tecnologias** e **protocolos** envolvidos.

---
#### IP's Restritos / Privados

| Prefixo | Faixa de Endereços | Descrição |
| --- | --- | --- |
| **10.0.0.0/8** | 10.0.0.0 a 10.255.255.255 | Uma rede de endereços de **classe A** |
| **172.16.0.0/12** | 172.16.0.0 a 172.31.255.255 | 16 redes contíguas de endereços de **classe B** |
| **192.168.0.0/16** | 192.168.0.0 a 192.168.255.255 | 256 redes contíguas de endereços de **classe C** |

#### Observação sobre ***redes contíguas***

* **Redes contíguas**, no contexto da computação de rede, referem-se àquelas em que **todos** os dispositivos em uma rede (ou sub-rede) conseguem se comunicar **diretamente** entre si, sem a necessidade de recorrer a uma **rede externa** ou a roteadores **intermediários**. Em termos diferentes, isso significa que os dispositivos estão conectados **tanto** fisicamente **quanto** logicamente dentro do mesmo espaço de endereço IP.


---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)  
[RFC 1918](https://www.rfc-editor.org/rfc/rfc1918.html)
