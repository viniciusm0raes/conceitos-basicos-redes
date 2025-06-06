[<p style="text-align:right; font-weight: 710;font-size: 1.5em; margin-right:0;">↩︎<span style="font-size: .75em"> índice</span></p>](../readme.md)
---
### Endereçamento IPv4 - [Sub-redes, Hosts e Broadcast com VLSM](https://www.youtube.com/watch?v=jqdhb44J5b0&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=15)
---

### Identificando (sub)redes, hosts e broadcast

* Para exemplo utilizaremos as sub-redes calculadas no [arquivo anterior](./13%20-%20IPv4%20-%20sub-redes_de_tamanho_variavel-vlsm.md)
* A rede de classe C dividida e 4 sub-redes no arquivo citado é a **192.168.0.0**.

---
* **Primeiro passo**: Calcular o **salto**, ou seja, **256 menos o octeto misto** da máscara de sub-rede.

| Sub-rede | Máscara | Salto |
| --- | --- | --- |
| Sub-rede 3 | 255.255.255.**128** | 256 - 128 = **128** |
| Sub-rede 2 | 255.255.255.**192** | 256 - 192 = **64** |
| Sub-rede 1 | 255.255.255.**224** | 256 - 224 = **32** |
| Sub-rede 4 | 255.255.255.**248** | 256 - 248 = **8** |

---
* **Segundo passo**: Identificar os endereços de **Rede, Host e Broadcast** de cada sub-rede.

| Sub-rede | Endereço de Rede | Endereços de Host | Endereço de Broadcast |
| --- | --- | --- | --- |
|  **Sub-rede 3**  | 192.168.0.**0** | 192.168.0.**1** até 192.168.0.**126** | 192.168.0.**127** |
|  **Sub-rede 2**  | 192.168.0.**128** | 192.168.0.**129** até 192.168.0.**190** | 192.168.0.**191** |
|  **Sub-rede 1**  | 192.168.0.**192** | 192.168.0.**193** até 192.168.0.**222** | 192.168.0.**223** |
|  **Sub-rede 4**  | 192.168.0.**224** | 192.168.0.**225** até 192.168.0.**230** | 192.168.0.**231** |

#### Observação sobre a separação das Sub-redes

* Apesar de as sub-redes estarem dentro de uma **mesma rede** (192.168.0.0), estas são **separadas** e **não se comunicam** entre si.
* Essa limitação de **cada sub-rede**, além de melhorar o sigilo / privacidade destas, amplia a segurança, pois como as sub-redes **não tem** comunicação direta, isso **limita** a propagação de ataques, **dificultando** o acesso de outras partes da rede.
* Outro ponto positivo desta segmentação é a possibilidade de aplicação de políticas de segurança **específica** para cada sub-rede, controlando as permissões de acesso e para quais recursos este se direciona.
* A segmentação também permite o **isolamento** de dispositivos de **alto risco**, como servidores, sistemas de produção e outros dispositivos vitais.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)  
[**Cisco** - Entender as quantidades de host e sub-rede](https://www.cisco.com/c/pt_br/support/docs/ip/routing-information-protocol-rip/13790-8.html)  
