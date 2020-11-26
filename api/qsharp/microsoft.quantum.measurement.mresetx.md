---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operazione MResetX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194203"
---
# <a name="mresetx-operation"></a>Operazione MResetX

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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