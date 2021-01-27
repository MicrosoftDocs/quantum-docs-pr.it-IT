---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840678"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un'operazione che implementa l'integratore Trotter – Suzuki per una determinata operazione.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

Numero di operazioni da scomporre in passaggi temporali.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) per la scomposizione.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Seleziona l'ordine di utilizzo di Trotter-Suzuki Integrator.
Ordine 1 e anche Orders 2, 4, 6,... sono attualmente supportati.



## <a name="output--doublet--unit--is-adj--ctl"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Restituisce un Unity che implementa l'integratore Trotter – Suzuki, dove il primo parametro `Double` è la dimensione del passaggio di integrazione e il secondo parametro è la destinazione su cui si è agito.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .

## <a name="remarks"></a>Commenti

Quando viene chiamato con `order` uguale a `1` , questa funzione restituisce un'operazione che può essere simulata da Trotter di ordine più basso-Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ dove è stata seguita la notazione di [quante-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) e si lascia che $ \lambda $ sia il tempo di evoluzione (rappresentato dal primo input dell'operazione restituita), e consentono a $ \{ H_j \} _ {j = 1} ^ {m} $ di essere il set di generatori dinamici (asimmetria-Hermitiane) integrati, in modo che `op(j, lambda, _)` venga simulato dall'operatore unitario $e ^ {H_j \lambda} $.

Analogamente, un oggetto `order` di `2` restituisce il secondo ordine simmetrico Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

I valori pari più elevati di `order` vengono implementati usando la costruzione ricorsiva di [quanti-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Riferimenti

- [*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)