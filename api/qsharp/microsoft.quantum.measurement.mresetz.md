---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operazione MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711052"
---
# <a name="mresetz-operation"></a>Operazione MResetZ

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto [](https://nuget.org/packages/)


Misura un singolo qubit in base alla Z e lo reimposta su uno stato iniziale fisso dopo la misurazione.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Descrizione

Esegue una misurazione a qubit singolo in $Z $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.

## <a name="input"></a>Input

### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Singolo qubit da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato della misurazione `target` in Pauli $Z $ base.