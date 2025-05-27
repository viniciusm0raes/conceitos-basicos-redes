### Endereçamento IPv4 - [Máscara CIDR](https://www.youtube.com/watch?v=INT-5Qa8Hls&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=8)
---

### Máscara CIDR (Classless Inter-Domain Routing)

* Antes de 1993, ano de criação do **CIDR (Classless Inter-Domain Routing)**, a **ICANN** (Internet Corporation for Assigned Names and Numbers) atribuía endereços de **classe A** para demandantes. 
* Mesmo que essa demanda **só precisasse de poucos IP's** (10, 100, etc.), como se tratava de **IP classe A**, seriam **reservados** para esta **16.777.216** números de IP's. Dessa forma, se dava uma distribuição completamente **ineficiente**.
* O grande volume de IP's **restantes e não utilizados** pelos demandantes, **não poderia** ser atribuídos para **outro demandante**. Afinal, caso isso fosse feito, essas redes teriam **visualização cruzada**. O que além de afetar sua **segurança**, colocaria em risco a **privacidade / sigilo** destas.
* Com a criação do CIDR, a distribuição de IP's passou a se dar por **máscaras** que se **aproximem o máximo possível** da necessidade **real**.
* O CIDR (Classless Inter-Domain Routing) foi introduzido pela **Internet Engineering Task Force (IETF)** em 1993. É um método criado para **substituir** a arquitetura de endereçamento de rede **anterior** com classes na Internet e, dessa forma, aderir a uma utilização **mais eficiente** dos endereços IP. 
* O CIDR é um método de **alocação de endereços IP** que melhora a eficiência **do roteamento**. 
* Permite uma alocação **mais flexível e eficiente** para os endereços IP, evitando a **escassez** destes.
* Com uma **notação compacta**, o CIDR representa **um ou mais ** endereços IP e sua **máscara de rede**. 
* A conexão entre o CIDR e as **sub-redes** reside no fato de que o CIDR é uma **metodologia** que auxilia na **formação e estruturação de sub-redes** em uma **rede maior**.
* O conceito de **sub-rede** refere-se à **subdivisão** de uma rede em **partes menores**, enquanto o CIDR oferece uma forma de notação que possibilita um **gerenciamento mais eficaz e adaptável** do espaço dos endereços IP durante a administração das sub-redes.
* O **Classless (sem classes)** no nome CIDR, se dá em função de **não** se seguir **obrigatoriamente** o padrão de classes.
* Como o CIDR **não determina** o uso de classes IP e seu padrão de **alocação fixa** do número total destes, esse método permite uma **segmentação** mais eficiente e com uma **aproximação mais precisa** da **real** necessidade de **cada** rede / sub-rede.

---
### Conversão de uma máscara ***padrão classe A*** (255.0.0.0) para CIDR

* Uma das características principais de uma máscara CIDR é ser precedida de uma **barra padrão** (/) e depois, informada a **quantidade de bits 1** da máscara padrão.
* Primeiro convertemos **o 255** da máscara padrão em **binário**.
* Em segundo lugar, informamos a **quantidade de bits 1** nesta máscara **padrão**.

#### Observação sobre a ***Identificação de Rede e de Host***

* Verificar no arquivo sobre a **identificação de Rede e Host**, a relação dos **bits 1 e 0** para identificação destes.

---
* **Exemplo 1**:

| Base 2 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |

**Convertendo** uma máscara padrão **classe A** em CIDR, como temos **8 bits 1**, informamos **/ e esta quantidade**  ao final da máscara padrão. Dessa forma, temos um CIDR: **255.0.0.0/8**

---
### Conversão de uma máscara ***padrão classe B*** (255.255.0.0) para CIDR

* **Exemplo 2**:

Seguindo o **exemplo anterior**, convertemos **os 255** da máscara padrão em **binário**.
Como temos **16 bits 1 (8 em cada octeto)**, convertendo uma máscara padrão **classe B**, temos um CIDR: **255.255.0.0/16**

---
### Conversão de uma máscara ***padrão classe C*** (255.255.255.0) para CIDR

* **Exemplo 3**:

Seguindo o mesmo raciocínio e convertendo **os 255** da máscara padrão em **binário**, temos **24 bits 1 (8 em cada octeto)**. Logo, para uma máscara padrão **classe C**, temos um CIDR: **255.255.255.0/24**

---
### Conversão de ***sub-redes*** para CIDR

* **Exemplo 4**:

Para o caso de uma máscara de sub-rede igual a **255.255.248.0**, já sabemos ter 16 bits nos **dois primeiros** octetos.
Convertendo **o 248** para binário teremos:

| Base 2 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 |

Seguindo a mesma lógica e como temos a **soma de 21 bits 1**, o CIDR para a sub-rede exemplificada seria: **255.255.248.0/21**

---
### Sobre máscaras de ***sub-redes***

* Apesar de sub-redes serem tratadas num **outro arquivo** neste repositório, para ser uma máscara de sub-rede **válida**, no endereço **inteiro**, todos **os bits 1** precisam ficar **à esquerda** e os bits 0 **à direita**.
* **Alternância** entre os bits 1 e 0 formam uma máscara de sub-rede **inválida**.
* Dentro desta lógica, os **únicos** números válidos em uma máscara de **sub-rede** são: **255, 254, 252, 248, 240, 224, 192, 128 e 0**
* Essa ***"limitação"*** se dá por conta de, em função da supracitada determinação na sequência de 1 e 0, **apenas** esse conjunto de números, na sua **conversão para binário**, manter todos os números 1 **à esquerda** e os números 0 **à direita**. Dessa forma, se não houver **exatamente** esses números, **não é** uma máscara de **sub-rede** válida.
 * O valor **diferente** de 255, **necessáriamente** precisa ser o **último** na declaração dos octetos. Afinal, apesar de os números válidos **seguirem a ordem** de 0 e 1, se colocados como no **exemplo** 255.248.255.0, **o 248**, no **conjunto dos octetos**, alteraria a ordem de 1 à esquerda e 0 à direita e seria uma máscara de sub-rede **inválida**.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
