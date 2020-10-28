---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operazione MResetX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725000"
---
# <a name="mresetx-operation"></a>Operazione MResetX

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto [](https://nuget.org/packages/)


Misura un singolo qubit in base X e lo reimposta su uno stato iniziale fisso dopo la misurazione.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Descrizione

Esegue una misurazione a qubit singolo in $X $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.

## <a name="input"></a>Input

### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Singolo qubit da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato della misurazione `target` in Pauli $X $ base.