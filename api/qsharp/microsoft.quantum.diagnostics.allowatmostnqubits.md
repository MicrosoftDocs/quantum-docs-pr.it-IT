---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operazione AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713054"
---
# <a name="allowatmostnqubits-operation"></a>Operazione AllowAtMostNQubits

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Tra una chiamata a questa operazione e la relativa contigua, asserisce che al massimo un determinato numero di qubits aggiuntivi viene allocato con istruzioni using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero massimo di qubits che possono essere allocati.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da visualizzare in caso di errore.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.