---
title: 'Tensor não é matriz'
date: 2023-12-08T10:24:28-03:00
type: "post"
draft: false
---

Vejo com frequência a afirmação de que "tensor é uma matriz multidimensional". Embora não esteja muito longe da verdade, essa é uma afirmação falsa. Meu objetivo aqui é elucidar essa diferença, sem entrar em muitos detalhes.

Deixe-me explicar sucintamente: tensor é uma função linear que recebe vetores como argumentos e retorna um número real. Por exemplo, o tensor de métrica $g$ recebe dois vetores, $v_1$ e $v_2$, como argumentos e retorna o produto interno entre eles:
$$
g(v_1,v_2) := \text{"produto interno de $v_1$ com $v_2$"}.
$$

Acontece que, da mesma forma que um vetor pode ser **representado** por suas coordenadas, um tensor também pode (a palavra-chave aqui é "representado"). Assim, se $v_1$ e $v_2$ têm 3 coordenadas cada (ou seja, eles "moram" num espaço de três dimensões), $g$ tem 9 coordenadas ($=3 \times 3$): $g_{11}, g_{12}, g_{13} \ldots, g_{33}$. Note ainda que, quando falamos em coordenadas, inevitavelmente temos de escolher uma base (ou referência).

Tensores que recebem 2 vetores como argumentos, como $g$, podem ter suas coordenadas arranjadas numa matriz (diz-se que a matriz é uma representação de $g$):
$$
\begin{matrix*}
g_{11} & g_{12} & g_{13} \\
g_{21} & g_{22} & g_{23} \\
g_{31} & g_{32} & g_{33}
\end{matrix*}
$$

Daí surge a ideia de que um tensor que recebe 3 vetores como argumento pode ser representado por uma "matriz de três dimensões". Mas note: dizer que um tensor é uma matriz é o mesmo que dizer que um vetor é suas coordenadas. Não são!

Se fosse apenas isso seria apenas uma questão de terminologia. Mas esse não é o caso, pois o importante é que o número $g(v_1,v_2)$ é independente da escolha de base, simplesmente porque $g$ é uma função de $v_1$ e $v_2$, não de suas coordenadas. Isso significa que, quando falamos de $v_1$, $v_2$ e $g$ em termos das suas coordenadas, elas devem respeitar certas regras de transformação que garantam a independência da base. Essa característica sequer faz sentido para um arranjo/matriz qualquer de números.

Em tempo, note que as ocorrências de "vetor" neste texto não refere-se exclusivamente aos _vetores geométricos_, que é o que você provavelmente imaginou (as flechas ou grandezas com intensidade e sentido), mas sim ao conceito mais abstrato de elemento de um espaço vetorial (se está interessado nesse assunto, Álgebra Linear é a área que você busca).

Para finalizar, se nada ficou claro, lembre-se disso: um tensor sempre pode ser representado por um arranjo de números, mas um arranjo de números não necessariamente representa um tensor (note o uso do verbo "representar" ao invés do "ser").

Menções honrosas:
- Matematicamente, matriz é um arranjo de elementos em linhas e colunas. Não existe "matriz multidimensional", a não ser como uma extensão coloquial do termo.
- Na quase-correta asserção de que um tensor é uma matriz multidimensional, as "dimensões da matriz" na verdade referem-se ao posto do tensor (_rank_, em Inglês). As dimensões, propriamente ditas, têm a ver com a quantidade de linhas e colunas. Assim, por exemplo, o tensor de métrica tem _posto_ dois. Por outro lado, o tensor de curvatura de Riemann tem posto quatro, pois espera receber quatro vetores como argumento.

---

1. Mais rigorosamente, tensor é uma função (linear em cada parâmetro) que recebe vetores de um espaço vetorial e/ou covetores de seu espaço dual e retorna um número real.
2. O símbolo ":=" significa "definido como". Em outras palavras, é uma instrução que nos diz: "toda vez que virmos o símbolo $g(v_1,v_2)$, trocamos ele por 'produto interno de $v_1$ com $v_2$'."
