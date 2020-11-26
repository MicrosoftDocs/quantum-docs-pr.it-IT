---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definito dall'utente SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200255"
---
# <a name="syndromemeasop-user-defined-type"></a>Tipo definito dall'utente SyndromeMeasOp

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un'operazione utilizzata per misurare la sindrome di un blocco di codice di correzione degli errori.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Commenti

La firma `(LogicalRegister => Syndrome)` rappresenta un'operazione che agisce congiuntamente sul qubits in `LogicalRegister` e alcuni qubits ausiliari seguito da una misura del qubits ausiliario per estrarre un `Syndrome` valore che rappresenta l'oggetto `Result[]` di queste misurazioni.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)