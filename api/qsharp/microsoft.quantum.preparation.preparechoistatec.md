---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: Operazione PrepareChoiStateC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: 34bb8eaebbc627d246e32a3cffd877ccad45e86e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854383"
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