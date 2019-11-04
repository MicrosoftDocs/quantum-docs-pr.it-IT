---
title: Vettori e matrici | Microsoft Docs
description: Vettori e matrici
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183744"
---
# <a name="vectors-and-matrices"></a>Vettori e matrici

Una certa familiarità con i vettori e le matrici è essenziale per comprendere il quantum computing. Viene fornita una breve introduzione e i lettori interessati sono consigliati per leggere un riferimento standard sull'algebra lineare, ad esempio *Strang, G. (1993). Introduzione all'algebra lineare (vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o un riferimento online, ad esempio [algebra lineare](http://joshua.smcvt.edu/linearalgebra/).

Una colonna Vector (o semplicemente [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ della dimensione (o size) $n $ è una raccolta di $n numeri $ complessi $ (V_1, v_2, \ldots, v_n) $ disposte come colonna:

$ $v = \begin{Bmatrix} V_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{Bmatrix} $ $

La norma di un vettore $v $ è definita come $ \sqrt{\sum\_i | v\_i | ^ 2} $. Un vettore viene detto unità Norm (oppure in alternativa è denominato [*vettore di unità*](https://en.wikipedia.org/wiki/Unit_vector)) se la norma è $1 $. L'oggetto [*contiguo di un vettore*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ è indicato $v ^ \dagger $ ed è definito come il vettore di riga seguente, dove $\*$ indica il coniugato complesso,

$ $ \begin{Bmatrix}V_1 \\\\ \vdots \\\\ v_n \end{Bmatrix} ^ \dagger = \begin{Bmatrix}V_1 ^ * & \cdots & v_n ^ * \end{Bmatrix} $ $

Il modo più comune per moltiplicare due vettori è il [*prodotto interno*](https://en.wikipedia.org/wiki/Inner_product_space), noto anche come prodotto a punti.  Il prodotto interno fornisce la proiezione di un vettore su un altro e non è utile per descrivere come esprimere un vettore come una somma di altri vettori più semplici.  Il prodotto interno tra $u $ e $v $, indicato $ \left\langle u, v\right\rangle $ è definito come

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} V_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Questa notazione consente inoltre di scrivere la norma di un vettore $v $ come $ \sqrt{\langle v, v\rangle} $.

È possibile moltiplicare un vettore con un numero $c $ per formare un nuovo vettore le cui voci vengono moltiplicate per $c $. È anche possibile aggiungere due vettori $u $ e $v $ per formare un nuovo vettore le cui voci sono la somma delle voci di $u $ e $v $. Queste operazioni sono illustrate di seguito:

$ $ \mathrm{If} ~ u = \begin{Bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{Bmatrix} ~ \mathrm{and} ~ v = \begin{Bmatrix} V_1\\\\ v_2\\\\ \vdots @no__ t_10_ \\ v_n \end{Bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{Bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{Bmatrix}.
$$

Una [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) di dimensioni $m \times n $ è una raccolta di $MN numeri $ complessi disposti in $m $ rows e $n $ Columns, come illustrato di seguito:

$ $M = \begin{Bmatrix} m_{11} ~ ~ m_{12} ~ ~ \cdots ~ ~ m_ {1N}\\\\ m_{21} ~ ~ m_{22} ~ ~ \cdots ~ ~ m_ {2n}\\\\ \ddots\\\\ m_ {M1} ~ ~ m_ {m2} ~ ~ \cdots ~ ~ m_ {MN}\\@no__ t_11_ \end{Bmatrix}. $ $

Si noti che un vettore di Dimension $n $ è semplicemente una matrice di dimensioni $n \times $1. Come per i vettori, possiamo moltiplicare una matrice con un numero $c $ per ottenere una nuova matrice in cui ogni voce viene moltiplicata con $c $ ed è possibile aggiungere due matrici con le stesse dimensioni per produrre una nuova matrice le cui voci sono la somma delle rispettive voci delle due matrici. 

## <a name="matrix-multiplication-and-tensor-products"></a>Moltiplicazione di matrici e prodotti tensori

È anche possibile moltiplicare due matrici $M $ of Dimension $m \times n $ e $N $ of Dimension $n \times p $ per ottenere una nuova matrice $P $ of Dimension $m \times p $ come indicato di seguito:

\begin{align} & \begin{Bmatrix} m_{11} ~ ~ m_{12} ~ ~ \cdots ~ ~ m_ {1N}\\\\ m_{21} ~ ~ m_{22} ~ ~ \cdots ~ ~ m_ {2n}\\\\ \ddots\\\\ m_ {M1} ~ ~ m_ {m2} ~ ~ \cdots ~ ~ m_ {MN} \end{Bmatrix} \ Begin {Bmatrix} n{11} ~ ~ n{12} ~ ~ \cdots ~ ~ n {1P}\\\\ n{21} ~ ~ n{22} ~ ~ \cdots ~ ~ n {2P}\\\\ \ddots\\\\ n {n1} ~ ~ n {N2} ~ ~ \cdots ~ ~ n {NP} \end{Bmatrix} = \begin{Bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1P}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2P}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{Bmatrix} \end{align}

dove le voci di $P $ sono $P _ {ik} = \sum_j m_ {IJ} n {JK} $. Ad esempio, la voce $P _{11}$ è il prodotto interno della prima riga di $M $ con la prima colonna di $N $. Si noti che poiché un vettore è semplicemente un caso speciale di una matrice, questa definizione si estende alla moltiplicazione dei vettori di matrici. 

Tutte le matrici considerate saranno matrici quadre, in cui il numero di righe e colonne è uguale, o vettori, che corrisponde solo a una colonna di $1 $. Una matrice quadrata speciale è la [*matrice di identità*](https://en.wikipedia.org/wiki/Identity_matrix), denotata $ \boldone $, che include tutti gli elementi diagonali uguali a $1 $ e gli elementi rimanenti uguali a $0 $:

$ $ \boldone = \begin{Bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{Bmatrix}. $ $

Per una matrice quadrata $A $, si dice una matrice $B $ è la relativa [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone $. L'inverso di una matrice non deve esistere, ma quando esiste è univoco e viene indicato $A ^{-1}$. 

Per qualsiasi matrice $M $, la trasportazione contigua o coniugata di $M $ è una matrice $N $ tale che $N _ {IJ} = m_ {Ji} ^\*$. Il contiguo di $M $ è in genere indicato $M ^ \dagger $. Si dice che una matrice $U $ è [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) se $UU ^ \Dagger = u ^ \dagger U = \boldone $ o equivalente, $U ^{-1} = U ^ \dagger $.  Probabilmente la proprietà più importante delle matrici unitarie è che conservano la norma di un vettore.  Questo problema si verifica perché 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

Una matrice $M $ è [*Hermitiane*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M = M ^ \dagger $.

Infine, il [*prodotto tensore*](https://en.wikipedia.org/wiki/Tensor_product) (o prodotto Kronecker) di due matrici $M $ di dimensioni $m \times n $ e $N $ di dimensioni $p \times q $ è una matrice di dimensioni maggiori $P = M\otimes n $ di dimensione $MP \times NQ $, ed è ottenuta da $M $ e $N $ come indicato di seguito:

\begin{align} M \otimes N & = \begin{Bmatrix} m_{11} ~ ~ \cdots ~ ~ m_ {1N} \\\\ \ddots\\\\ m_ {M1} ~ ~ \cdots ~ ~ m_ {MN} \end{Bmatrix} \otimes \begin{Bmatrix} n{11} ~ ~ \cdots ~ ~ n {1Q}\\\\ \ddots @no__ t_8_ \\ n {P1} ~ ~ \cdots ~ ~ n {PQ} \end{Bmatrix}\\\\ & = \begin{Bmatrix} m_{11} \begin{Bmatrix} n{11} ~ ~ \cdots ~ ~ n {1Q}\\\\ \ddots\\\\ n {P1} ~ ~ \cdots ~ ~ n {PQ} \end{Bmatrix} ~ ~ \cdots ~ ~ m_ {1N} \begin{Bmatrix} n{11} ~ ~ \cdots ~ ~ n {1Q}\\\\ \ddots\\\\ n {P1} ~ ~ \cdots ~ ~ n {PQ} \end{Bmatrix}\\\\ \ddots\\\\ m_ {M1} \begin{Bmatrix} n{11} ~ ~ \ cdots ~ ~ n {1Q}\\\\ \ddots\\\\ n {P1} ~ ~ \cdots ~ ~ n {PQ} \end{Bmatrix} ~ ~ \cdots ~ ~ m_ {MN} \begin{Bmatrix} n{11} ~ ~ \cdots ~ ~ n {1Q}\\\\ \ddots\\\\ n {P1} ~ ~ \cdots ~ ~ n {PQ} \end {bmatrix} \end{bmatrix}.
\end{align}

Si tratta di una dimostrazione migliore con alcuni esempi:

$ $ \begin{Bmatrix} a \\\\ b \end{Bmatrix} \otimes \begin{Bmatrix} c \\\\ d \\\\ e \end{Bmatrix} = \begin{Bmatrix} a \begin{Bmatrix} c \\\\ d \\\\ e \end{Bmatrix} @no__ t_10_ \\[1.5 em] b \begin{Bmatrix} c \\\\ d \\\\ e\end {Bmatrix} \end{Bmatrix} = \begin{Bmatrix} a c \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end {Bmatrix} $ $

e

$ $ \begin{Bmatrix} a \ b \\\\ c \ d \end{Bmatrix} \otimes \begin{Bmatrix} e \ f\\\\g \ h \end{Bmatrix} = \begin{Bmatrix} a\begin {Bmatrix} e \ f\\\\ g \ h \end{Bmatrix} b\begin {Bmatrix} e \ f\\@no__ t_7_ g \ h \end{Bmatrix} \\\\[1em] c\begin {Bmatrix} e \ f\\\\ g \ h \end{Bmatrix} d\begin {Bmatrix} e \ f\\\\ g \ h \end{Bmatrix} \end{Bmatrix} = \begin{Bmatrix} AE \ AF \ be \ BF \\@no__ t_15_ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{Bmatrix}.
$$

Una convenzione di notazione utile finale che circonda i prodotti tensori è che, per qualsiasi vettore $v $ o Matrix $M $, $v ^ {\otimes n} $ o $M ^ {\otimes n} $ è una mano breve per un prodotto tensore ripetuto a $n $-fold.  ad esempio:

\begin{align} & \begin{Bmatrix} 1 \\\\ 0 \end{Bmatrix} ^ {\otimes 1} = \begin{Bmatrix} 1 \\\\ 0 \end{Bmatrix}, \qquad\begin{Bmatrix} 1 \\\\ 0 \end{Bmatrix} ^ {\otimes 2} = \begin{Bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{Bmatrix}, \qquad\begin{Bmatrix} 1 \\\\-1 \end{Bmatrix} ^ {\otimes 2} = \begin{Bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{Bmatrix}, \\\\ & \begin{Bmatrix} 0 & 1 \\\\ 1 & 0 \end{Bmatrix} ^ {\otimes 1} = \begin{Bmatrix} 0 & 1 \\\\ 1 & 0 \end{Bmatrix}, \qquad\begin{Bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{Bmatrix} ^ {\otimes 2} = \begin{Bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ end {Bmatrix}.
\end{align}

