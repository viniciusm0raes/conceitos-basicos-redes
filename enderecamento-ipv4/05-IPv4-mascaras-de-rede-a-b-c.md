### Endereçamento IPv4 - [Máscaras de Rede A, B e C](https://www.youtube.com/watch?v=7OLSanO98-k&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=6)
---

#### Máscaras de Rede ***Padrão***

* Apenas as classes A, B e C possuem máscara de rede.
* A mascara de rede define qual o padrão de identificação os dispositivos **na rede devem utilizar**. É esse padrão definido que permite que os dispositivos **de rede** identifiquem a **qual classe** a rede pertece e qual **parte dos IP's** determinam **rede e host**.

---
#### Tabela ***simplificada*** de Máscaras de Rede ***Padrão***

| Classe | Exemplo IP | Máscara de Rede |
| --- | --- | --- |
| **A** | **10**.0.12.15 | **255**.0.0.0 |
| **B** | **172.16**.0.10 | **255.255**.0.0 |
| **C** | **192.168.0**.1 | **255.255.255**.0 |


#### Observação sobre as Máscaras de Rede ***Padrão***
* Essa configuração de máscaras são para uma **rede**. Uma **sub-rede** obedece um padrão **específico**. Sendo este, **diretamente relacionado**.
* O que a máscara de rede faz é **informar ao equipamento** qual(is) parte(s) dos octetos do IP **identificam a rede** (255) e qual parte deste **identificam o host** (0).
* Essa definição é feita substituindo a(s) parte(s) dos octetos que identificam **a rede** por **255** e a parte dos octetos que identificam **o host** por **0**.
* A razão de uso do 255 é por esse ser o **maior número** possível no IP **com 8 bits**. Logo, aquele **intervalo** é que definirá **qual classe** e **quais IP's** pertencem a **esta rede**.

---		
**Fontes**:  
[**Hardware Redes Brasil** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
