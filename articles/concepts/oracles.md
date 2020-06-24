---
title: Oracoli quantistici
description: Informazioni su come usare e definire Oracle Quantum, black box operazioni usate come input per un altro algoritmo.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269559"
---
# <a name="quantum-oracles"></a>Oracle Quantum

Un $O Oracle $ è un'operazione "black box" utilizzata come input per un altro algoritmo.
Tali operazioni vengono spesso definite utilizzando una funzione classica $f: \\ {0, 1 \\ } ^ n per \\ {0, 1 \\ } ^ m $ , che accetta un $ input binario a $n bit e produce un output binario a $m $ bit.
A tale scopo, si consideri un particolare input binario $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.
È possibile etichettare gli Stati qubit come $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1} \otimes \cdots \otimes \ket{ } x_ {n-1 } } $.

È possibile prima di tutto tentare di definire $O in $ modo che $O \ket {x } = \ket{f (x)} $, ma ciò presenta un paio di problemi.
In primo luogo, $f $ possono avere dimensioni diverse di input e output ($n \ne m $ ), in modo che l'applicazione di $O $ modifichi il numero di qubits nel registro.
In secondo luogo, anche se $n = m $ , la funzione potrebbe non essere invertibile: se $f (x) = f (y) $ per alcuni $x \ne y $ , quindi $O \ket {x } = o \ket {y } $ ma $O ^ \dagger o \ket {x } \ne o ^ \dagger o \ket {y } $.
Ciò significa che non sarà possibile costruire l'operazione contigua $O ^ \dagger $ e che per tali Oracle deve essere definito un oggetto adiacente.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definizione di un Oracle per effetto sugli stati di base di calcolo
È possibile gestire entrambi questi problemi introducendo un secondo registro di $m $ qubits per la risposta.
Si definirà quindi l'effetto di Oracle su tutti gli Stati di base computazionale: per tutti $x \In \\ {0, 1 \\ } ^ n $ e $y \In \\ {0, 1 \\ } ^ m $ ,

$ $ \begin{align}
    O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.
\end{align}
$$

A questo punto $O = O ^ \dagger $ per costruzione, quindi sono stati risolti entrambi i problemi precedenti.

> [!TIP]
> Per verificare che $O = O ^ {\dagger } $, si noti che $O ^ 2 = \boldone $ da $a \oplus b \oplus b = a $ per tutti $a, b \In \{ 0, 1 \} $.
> Di conseguenza, $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.

In particolare, la definizione di un Oracle in questo modo per ogni stato di base computazionale $ \ket{x } \ket{y } $ definisce anche il modo in cui $O $ agisce per qualsiasi altro stato.
Questa operazione segue immediatamente il fatto che $O $ , come tutte le operazioni Quantum, è lineare nello stato su cui agisce.
Si consideri l'operazione Hadamard, ad esempio, definita da $H \ket{0 } = \ket { +} $ e $H \ket{1 } = \ket { -} $.
Se si vuole ottenere informazioni su come $H $ agisce su $ \ket { +} $, è possibile usare tale $H $ lineare,

$ $ \begin{align}
H \ket { +} & = \frac{1 } {\sqrt{2 } } h (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + h \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .
\end{align}
$$

Nel caso di definire il $O Oracle $ , è possibile usare in modo analogo che qualsiasi stato $ \ket { \psi } $ su $n + m $ qubits può essere scritto come

$ $ \begin{align}
\ket { \psi } & = \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y}
\end{align}
$$

dove $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m per \mathbb{C } $ rappresenta i coefficienti dello stato $ \ket { \psi } $. Pertanto

$ $ \begin{align}
O \ket { \psi } & = O \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ Sum_ {x \In \\ {0,1} \\ ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0,1 \\ } ^ m } \Alpha (x, y) \ket{x \ket{y \oplus } f (x)}.
\end{align}
$$

## <a name="phase-oracles"></a>Oracle della fase
In alternativa, è possibile codificare $f $ in un $O Oracle $ applicando una _fase_ basata sull'input per $O $ .
È ad esempio possibile definire $O $ tale che $ $ \begin{align}
    O \ket{x } = (-1) ^ {f (x)} \ket{x } .
\end{align}
$ $ Se una fase Oracle agisce inizialmente su un registro con uno stato di base computazionale $ \ket{x } $, questa fase è una fase globale e pertanto non è osservabile.
Tale Oracle, tuttavia, può essere una risorsa molto potente se applicata a una superposizione o come operazione controllata.
Si consideri, ad esempio, una fase Orcale $O _f $ per una funzione single-qubit $f $ .
Quindi, $ $ \begin{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.
\end{align}
$$

Più in generale, entrambe le visualizzazioni di Oracle possono essere ampliate per rappresentare funzioni classiche che restituiscono numeri reali anziché solo un bit singolo.

La scelta del modo migliore per implementare un Oracle dipende in larga misura dal modo in cui tale Oracle verrà utilizzato all'interno di un determinato algoritmo.
Ad esempio, l' [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) si basa su Oracle implementato nel primo modo, mentre l' [algoritmo di Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) si basa su Oracle implementato nel secondo modo.


Per altri dettagli, è consigliabile discutere in [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
