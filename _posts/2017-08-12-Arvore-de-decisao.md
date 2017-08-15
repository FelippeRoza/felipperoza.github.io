---
layout: post
title: Árvore de Decisão
---

O aprendizado por Árvore de Decisão (DT) é um método que permite a modelagem de sistemas discretos 
em que o modelo obtido é uma Árvore de Decisão, sendo um método muito utilizado para a inferência 
indutiva por ser robusto a ruído nos dados, além de ser de simples compreensão, 
permitindo uma representação gráfica do modelo gerado.

Outras razões motivam a popularidade desse método, como a simplicidade em se
montar as árvores, com algoritmos eficientes que escalam bem com o aumento do tamanho
da base de dados utilizada. Outro ponto é que a maioria dos algoritmos podem trabalhar
tanto com variáveis de entrada contínuas quanto categóricas. Além disso, as árvores de
decisão são não-paramétricas, ou seja, não necessitam de nenhuma informação *a priori*
quanto à distribuição dos atributos de entrada ou da função-objetivo.

A sua representação consiste em uma estrutura em que cada nodo interno corresponde a um teste 
sobre um dado atributo, cada ramo descendente representa uma possibilidade para esse teste e 
cada folha, contendo a classe respectiva às instâncias por ela
classificadas, é a decisão obtida após testar os atributos de forma sequencial. O caminho
percorrido para chegar à classe corresponde a uma regra de classificação.

### Entropia

A entropia caracteriza a organização de uma coleção de exemplos. Dado um
conjunto S , contendo valores positivos e negativos para um atributo-alvo, a entropia de S
relativa à essa classificação é dada por:

![Alt text](https://github.com/FelippeRoza/felipperoza.github.io/blob/new-post/images/decision-tree/entropy.png?raw=true)

onde p+ é a proporção de exemplos em que a saída é positiva e p− a proporção de exemplos
em que a saída é negativa. Para os cálculos envolvendo entropia se assumirá 0 * log2(0) como
sendo 0.

Ao analisar a Equação acima , nota-se que a entropia é 0 quando todos os elementos
de S pertencem à mesma classe, e 1 quando a coleção contém um mesmo número de
elementos cuja saída é positiva e negativa. Além disso, o resultado da soma entre p+ e p−
sempre será 1, de forma que pode-se escrever p− = 1 − p+ . A figura abaixo mostra a relação
entre a proporção p+ e a entropia:

![Alt text](https://github.com/FelippeRoza/felipperoza.github.io/blob/new-post/images/decision-tree/entropy_p_function.png?raw=true "Entropia de S em função de p+")

Generalizando o cálculo da entropia para casos em que o atributo-objetivo possui
mais que dois valores possíveis, define-se a entropia como:

![Alt text](https://github.com/FelippeRoza/felipperoza.github.io/blob/new-post/images/decision-tree/entropy_n.png?raw=true)

onde p*i* é a proporção de *S* pertencente à classe *i* e *c* é o número de classes do atributo-
objetivo.

### Ganho de Informação

Utilizando a entropia, que representa a medida da impureza de um conjunto de
exemplos de treinamento, pode-se definir uma medida para a eficácia de um atributo em
classificar esses exemplos. Essa medida é chamada ganho de informação, e é
definida como:

![Alt text](https://github.com/FelippeRoza/felipperoza.github.io/blob/new-post/images/decision-tree/information_gain.png?raw=true)

onde V alues ( A ) são todos os valores possíveis para o atributo A e S v é o subconjunto de
S em que o atributo A tem valor v, i.e.:

![Alt text](https://github.com/FelippeRoza/felipperoza.github.io/blob/new-post/images/decision-tree/sub_A.png?raw=true)

O ganho de informação mede, então, a redução esperada da entropia ao classificar
um conjunto utilizando determinado atributo.
