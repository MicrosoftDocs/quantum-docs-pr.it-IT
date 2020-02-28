---
title: Concetti avanzati relativi alle matrici
description: Informazioni su autovettori, autovalori e matrici esponenziali, gli strumenti fondamentali usati per descrivere e simulare gli algoritmi Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: a83911e01ad758bbcb7f701000fd58b4f1c91cd2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907580"
---
# <a name="advanced-matrix-concepts"></a>Concetti avanzati della matrice #

Si estenderà ora la manipolazione delle matrici agli [*autovalori, autovettori*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ed [*esponenziali*](https://en.wikipedia.org/wiki/Matrix_exponential) , che costituiscono un insieme fondamentale di strumenti necessari per descrivere e implementare gli algoritmi Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Autovalori e autovettori ##

$M $ sia una matrice quadrata e $v $ sia un vettore che non è il vettore di tutti gli zeri, ovvero il vettore con tutte le voci uguali a $0 $.

Si dice $v $ è un [*autovettore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) di $M $ if $MV = CV $ per un certo numero $c $. Si dice $c $ è il [*autovalore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corrispondente al autovettore $v $. In generale, una matrice $M $ può trasformare un vettore in qualsiasi altro vettore, ma un autovettore è speciale perché viene lasciato invariato, ad eccezione del fatto che viene moltiplicato per un numero. Si noti che se $v $ è un autovettore con autovalore $c $, $av $ è anche un autovettore (per qualsiasi valore diverso da zero $a $) con lo stesso autovalore.

Per la matrice di identità, ad esempio, ogni vettore $v $ è un autovettore con autovalore $1 $.

Per un altro esempio, si consideri una [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ che ha solo voci diversi da zero sulla diagonale:

$ $ \begin{Bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & D_3 \end{Bmatrix}.
$$

Vettori

$ $ \begin{Bmatrix}1 \\\\ 0 \\\\ 0 \end{Bmatrix}, \begin{Bmatrix}0 \\\\ 1 \\\\ 0 \ end {Bmatrix} e \begin{Bmatrix}0 \\\\ 0 \\\\ 1 \ end {Bmatrix} $ $

sono autovettori di questa matrice con autovalori $d _1 $, $d _2 $ e $d _3 $ rispettivamente. Se $d _1 $, $d _2 $ e $d _3 $ sono numeri distinti, questi vettori (e i relativi multipli) sono l'unico autovettori della matrice $D $. In generale, per una matrice diagonale è facile leggere gli autovalori e autovettori. Gli autovalori sono tutti i numeri visualizzati sulla diagonale e i rispettivi autovettori sono i vettori di unità con una voce uguale a $1 $ e le voci rimanenti uguale a $0 $.

Si noti che nell'esempio precedente il autovettori di $D $ costituisce una base per i vettori $3 $ dimensionali. Una base è costituita da un set di vettori in modo che qualsiasi vettore possa essere scritto come una combinazione lineare. In modo più esplicito, $v _1 $, $v _2 $ e $v _3 $ formano una base se qualsiasi vettore $v $ può essere scritto come $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ per alcuni numeri $a _1 $, $a _2 $ e $a _3 $.

Tenere presente che una matrice Hermitiane (detta anche self-adiacentt) è una matrice quadrata complessa uguale al proprio coniugato complesso, mentre una matrice unitaria è una matrice quadrata complessa il cui inverso è uguale al suo complesso coniugato.
Per le matrici Hermitiane e unitarie, che sono essenzialmente le uniche matrici rilevate nel quantum computing, è presente un risultato generale noto come [*teorema spettrale*](https://en.wikipedia.org/wiki/Spectral_theorem), che asserisce quanto segue: per qualsiasi matrice di Hermitiane o unity $M $, esiste un unity $U $ tale che $M = U ^ \Dagger D U $ per una matrice diagonale $D $. Inoltre, le voci diagonali di $D $ saranno gli autovalori di $M $.

È già noto come calcolare gli autovalori e la autovettori di una matrice diagonale $D $. Con questo teorema sappiamo che se $v $ è un autovettore di $D $ con autovalore $c $, ad esempio $Dv = CV $, $U ^ \dagger v $ sarà un autovettore di $M $ con autovalore $c $. Questo perché

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Esponenziali matrice
Una [*matrice esponenziale*](https://en.wikipedia.org/wiki/Matrix_exponential) può anche essere definita esattamente Analogamente alla funzione esponenziale.  Il valore esponenziale della matrice di una matrice $A $ può essere espresso come

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \cdots $ $

Questo è importante perché l'evoluzione del tempo di Quantum Mechanical è descritta da una matrice unitaria nel formato $e ^ {iB} $ per Hermitiane Matrix $B $.  Per questo motivo, l'esecuzione esponenziale della matrice è una parte fondamentale dell'elaborazione quantistica e in quanto tale Q # offre routine intrinseche per la descrizione di queste operazioni.
Ci sono molti modi per calcolare una matrice esponenziale in un computer classico e, in generale, l'approssimazione di un esponenziale tale esponenziale è irta di rischi.  Vedere [*Cleve Moler e Charles Van Loan. "Diciannove modi dubbi per calcolare l'esponenziale di una matrice". SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) per ulteriori informazioni sui problemi correlati.

Il modo più semplice per comprendere come calcolare l'esponenziale di una matrice è tramite gli autovalori e autovettori di tale matrice.  In particolare, il teorema spettrale illustrato sopra dice che per ogni Hermitiane o matrice unitaria $A $ esiste una matrice unitaria $U $ e una matrice diagonale $D $ tale che $A = U ^ \dagger D U $.  A causa delle proprietà di unitarietà, $A ^ 2 = U ^ \dagger D ^ 2 U $ e allo stesso modo per qualsiasi potenza $p $ $A ^ p = U ^ \dagger D ^ p U $.  Se si sostituisce questa operazione nella definizione dell'operatore dell'operatore esponenziale, si ottiene:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2!} + \cdots \right) U = U ^ \dagger \begin{Bmatrix}\exp (D_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (D_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (D_ {NN}) \end{Bmatrix} U. $ $

In altre parole, se si trasforma in eigenbasis della matrice $A $ then Computing The Matrix esponenziale è equivalente al calcolo dell'esponenziale comune degli autovalori della matrice.  Poiché il numero di operazioni in quantum computing comporta l'esecuzione di esponenziali di matrici, questo espediente di trasformazione nel eigenbasis di una matrice per semplificare l'esecuzione dell'operatore esponenziale viene visualizzato spesso ed è la base dietro molti algoritmi quantistici, ad esempio Trotter – metodi di simulazione Quantum di tipo Suzuki descritti più avanti in questa guida.

Un'altra proprietà utile è se $B $ è sia Unity che hermitiane, ad esempio $B = B ^{-1}= B ^ \dagger $ then $B ^ 2 = \boldone $. Applicando questa regola all'espansione precedente della matrice esponenziale e raggruppando il valore di $ \boldone $ e il $B $ terms insieme, è possibile vedere che per qualsiasi valore reale $x $ the Identity

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


tiene. Questo espediente è particolarmente utile in quanto consente di ragionare sulle azioni esponenziali della matrice, anche se la dimensione di $B $ è esponenzialmente grande, nel caso speciale in cui $B $ sia unitario che Hermitiane.
