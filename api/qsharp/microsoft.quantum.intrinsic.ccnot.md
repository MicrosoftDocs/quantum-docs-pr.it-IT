---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operazione CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711539"
---
# <a name="ccnot-operation"></a>Operazione CCNOT

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica il Gate CCNOT (doppiamente controllata) a tre qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo controllo qubit per CCNOT Gate.


### <a name="control2--qubit"></a>controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit di controllo per CCNOT Gate.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di destinazione per CCNOT Gate.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivalente a:

```qsharp
Controlled X([control1, control2], target);
```