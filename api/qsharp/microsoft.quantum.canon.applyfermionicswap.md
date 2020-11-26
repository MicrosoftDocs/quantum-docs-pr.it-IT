---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operazione ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218802"
---
# <a name="applyfermionicswap-operation"></a>Operazione ApplyFermionicSWAP

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica lo scambio fermioniche.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa operazione sostanzialmente scambia il qubits durante l'applicazione di una fase globale di-1 se entrambi i qubits sono 1S. Conserva l'anti-symmetrization degli orbitali.
Per altre informazioni, vedere .

Questa operazione è rappresentata dall'operatore unitario \begin{align} f_ {swap} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{Bmatrix}.
\end{align}

## <a name="input"></a>Input

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo qubit da scambiare.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit da scambiare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, grance Kin-Lic Chan*, arXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Intrinsic. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)