---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Operazione PrepareChoiStateCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709442"
---
# <a name="preparechoistateca-operation"></a>Operazione PrepareChoiStateCA

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Prepara lo stato Choi-Jamiłkowski per un'operazione specificata con varianti controllate e adiacenti nei registri di riferimento e di destinazione specificati.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-adj--ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL




### <a name="reference--qubit"></a>riferimento: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)