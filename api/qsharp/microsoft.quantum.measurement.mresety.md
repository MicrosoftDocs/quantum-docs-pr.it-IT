---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operazione MResetY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854645"
---
# <a name="mresety-operation"></a>Operazione MResetY

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Misura un singolo qubit in base Y e lo reimposta su uno stato iniziale fisso dopo la misurazione.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Descrizione

Esegue una misurazione a qubit singolo in $Y $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.

## <a name="input"></a>Input

### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Singolo qubit da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato della misurazione `target` in Pauli $Y $ base.