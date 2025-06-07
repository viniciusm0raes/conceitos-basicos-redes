[<p style="font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](../enderecamento-ipv4/README.md)
---
### Endereçamento IPv4 - [Identificação de Rede e de Host (Componentes de um IP)](https://www.youtube.com/watch?v=C_EWtszvmrY&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=4)
---

#### Componentes de um endereço IP

* **Identificação de Redes e Hosts**

| Classe | Intervalo do ***primeiro*** octeto / Exemplo | Identificação | Observação |
| --- | --- | --- | --- |
| **A** | 0 a 127 / 120.200.15.2 | O **primeiro** octeto identifica a **rede** os **três últimos** identificam o **host** | **128 redes** possíveis, com **cada rede** podendo ter **até 16.777.214 hosts** |
| **B** | 128 a 191 / 147.218.30.1 | Os **dois primeiros** octetos identificam a **rede** e os **dois últimos** identificam o **host** | **16.384 redes** possíveis, com **cada rede** podendo ter **até 65.534 hosts**|
| **C** | 192 a 223 / 192.168.0.1 | Os **três primeiros** octetos identificam a **rede** o **último** identifica o **host** | **2.097.152 redes** possíveis, com **cada rede** podendo ter **até 254 hosts** |

#### Observação sobre as ***classes de IP*** e a ***identificação*** de Rede / Host

* O que identifica a **rede** são **os bits 1** convertendo de decimal para **binário**. Essa conversão é explicada em **outro** arquivo **neste** repositório.
* Também utilizando a conversão de decimal para **binário**, são os **bits 0** que identificam o **host**.
* Nas classes de IP **A, B e C**, em cada uma delas há **dois endereços reservados**: o **endereço da rede** (network address) e o **endereço de broadcast** (broadcast address). Esses endereços **não podem ser atribuídos** a dispositivos **individuais dentro da rede**. 
* Como as classes D e E são endereços das chamadas **redes especiais**, multicast e teste de novas tecnologias, estas não se aplicam para identificação de Redes / Host.

#### Observação sobre ***roteadores***

* Roteadores são equipamentos que **só se comunicam** entre redes **diferentes**. Exemplo: um **modem** e um **roteador wifi** num **mesmo ambiente**. Caso o roteador esteja na **mesma rede** que o modem, ocorrerá um erro chamado **overlap** (sobreposição).
* A solução para o exemplo citado é colocar o modem e o roteador em **redes diferentes**. Exemplo: **o modem** na rede 192.168.0.1 e **o roteador** na rede 192.168.1.1. Lembrando que, como são de classe C, os **três primeiros** octetos identificam a **rede**.
* Também no caso do exemplo citado, o **servidor DHCP** (atribuição automática de IP's) **do modem** poderia **ser desativado** e **apenas o roteador** teria o servidor DHCP **ativo**. Essa definição de qual equipamento **distribuiria os IP's** se deve em função de, **no exemplo**, o modem estar se comunicando diretamente **apenas com o roteador**.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
