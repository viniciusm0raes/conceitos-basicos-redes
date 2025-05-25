### Endereçamento IPv4 - [Conversão de Binário para Decimal e Decimal para Binário](https://www.youtube.com/watch?v=Qs0xC9gDU94&list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp&index=7)
---

### Conversão de Decimal para ***Binário*** (simplificada)

* Como os números de IP são formados por **quatro octetos** de 8 bits e cada octeto **em base 10** varia entre **0 e 255**, numa conversão **para binário**, usamos uma tabela das **bases de 2**. Sempre da **direita para a esquerda**, iniciando no número 1 **até** o número **exato ou menor** mais próximo, nesse caso **256**.
* Tendo essa tabela em mente, os números que **somados** equivalem ao número de **base 10**, são substituídos **por 1** e os que **não fazem parte** dessa soma, são substituídos **por 0**.
* A **soma** dos valores **sempre** deve ser feita no sentido **inverso** à construção da tabela, ou seja, da **esquerda para a direita**.
* A razão dessa ordem (**esquerda para a direita**) é que a da soma dos valores (bits) em uma conversão de decimal para binário **altera o resultado**.
* A ordem dos dígitos binários **é crucial**, pois cada posição representa uma potência de 2 (2<sup>0</sup>, 2<sup>1</sup>, 2<sup>2</sup>, etc.), e a **posição** do 1 ou 0 em cada potência contribui para o valor decimal final.
* Os valores **zero à esquerda** são ignorados, **exceto** quando necessários para totalizarem os 8 bits.
* Os valores restantes **precisam** equivaler **exatamente** ao octeto integrante do IP.
* Se o octeto binário resultante tiver **menos de 8 bits** (8 dígitos), **adicionar** zeros à esquerda para completar os 8 bits ocupados por **cada octeto**.

---
#### Exemplos de conversão de Decimal para ***Binário***

#### Exemplo 1:
**(123)<sub>10</sub>**

Na conversão para binário, primeiro construímos a tabela, somamos os valores que resultam em 123<sub>10</sub>, substituímos estes por 1 e os demais por 0:

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 0 | 1 | 1 | 1 | 1 | 0 | 1 | 1 |

Dessa forma, **(123)<sub>10</sub>** é igual a **(001111011)<sub>2</sub>**. Ignorando os **zeros à esquerda** o (123)<sub>10</sub> resulta em (1111011)<sub>2</sub>, mas como esse número ocupa **apenas 7 bits**, adicionamos **um zero à esquerda** e temos um **octeto válido**, ou seja, **(01111011)<sub>2</sub>**.

---
#### Exemplo 2:
**(126)<sub>10</sub>**

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 0 | 1 | 1 | 1 | 1 | 1| 1 | 0 |

**(126)<sub>10</sub>** é igual a **(001111110)<sub>2</sub>**. **Ignorando** os zeros à esquerda o (126)<sub>10</sub> resulta em (1111110)<sub>2</sub>. Como esse número ocupa **apenas 7 bits**, adicionamos **um zero à esquerda** e temos **(01111110)<sub>2</sub>** como **octeto válido**.

---
#### Exemplo 3:
**(192)<sub>10</sub>**

| Base 2 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Binário** | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |

**(192)<sub>10</sub>** é igual a **(11000000)<sub>2</sub>**. Como esse número ocupa **exatamente 8 bits**, (11000000)<sub>2</sub> já **é um octeto válido**.

---
### Conversão de Binário para ***Decimal*** (simplificada)

* Primeiro se pega o número em base 2 (binário), **sem os zeros** inclusos para completar os 8 bits. O que já não ocorrerá quando se pegar **diretamente** um número binário.
* Se constrói uma tabela com **o mesmo** número de dígitos desse binário (**sem os zeros à esquerda**).
* Sempre da **direita para a esquerda**, se inicia com o número 1 e inclui as **bases de 2** até o total de dígitos do número binário original.
* Agora basta **somar** as bases de 2 e o respectivo valor **decimal** será encontrado.

---
#### Exemplos de conversão de Binário para ***Decimal***

#### Exemplo 1:
**(1110001)<sub>2</sub>**

| Binário | 1 | 1 | 1 | 0 | 0 | 0 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Base 2** | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

* Somando 1 + 16 + 32 + 64 = **(113)<sub>10</sub>**

---
#### Exemplo 2:
**(11101011)<sub>2</sub>**

| Binário | 1 | 1 | 1 | 0 | 1 | 0 | 1 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Base 2** | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

* Somando 1 + 2 + 8 + 32 + 64 + 128 = **(235)<sub>10</sub>**

---		
**Fontes**:  
[**Curso em Vídeo** - Curso de Endereçamento IPv4](https://www.youtube.com/playlist?list=PLAp37wMSBouCU49LV0qFbItufigjYk-sp)  
[**Cisco** - Conceitos Básicos de Redes](https://www.netacad.com/pt/courses/networking-basics?courseLang=pt-BR)
