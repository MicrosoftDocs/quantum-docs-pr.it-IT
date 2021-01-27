---
uid: Microsoft.Quantum.Canon.MultiplexerFromGenerator
title: MultiplexerFromGenerator (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: b86238debe66747ba23c3b41164813594f80b27c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852556"
---
# <a name="multiplexerfromgenerator-function"></a>MultiplexerFromGenerator (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un'operazione unitaria controllata da Multiply $U $ che applica un $V unitario _j $ se controllato da n-qubit numero stato $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
function MultiplexerFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL)

Tupla in cui il primo elemento `Int` è il numero di unitaries $N $ e il secondo elemento `(Int -> ('T => () is Adj + Ctl))` è una funzione che accetta un intero $j $ in $ [0, N-1] $ e restituisce l'operazione unitaria $V _J $.



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a>Output: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione unitaria controllata da Multiply $U $ che applica unitaries descritto da `unitaryGenerator` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)