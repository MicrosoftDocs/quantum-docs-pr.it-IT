---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: Operazione PrepareChoiStateC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: 7d9e53b1dd8ec08c0d0b200cc51562ca6330b06e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210540"
---
# <a name="preparechoistatec-operation"></a>Operazione PrepareChoiStateC

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara lo stato Choi-Jamiołkowski per un'operazione specificata con una variante controllata sui registri di riferimento e di destinazione specificati.

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Input

### <a name="op--qubit--unit--is-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL




### <a name="reference--qubit"></a>riferimento: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)