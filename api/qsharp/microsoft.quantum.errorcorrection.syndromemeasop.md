---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definito dall'utente SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712116"
---
# <a name="syndromemeasop-user-defined-type"></a>Tipo definito dall'utente SyndromeMeasOp

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un'operazione utilizzata per misurare la sindrome di un blocco di codice di correzione degli errori.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Commenti

La firma `(LogicalRegister => Syndrome)` rappresenta un'operazione che agisce congiuntamente sul qubits in `LogicalRegister` e alcuni qubits ausiliari seguito da una misura del qubits ausiliario per estrarre un `Syndrome` valore che rappresenta l'oggetto `Result[]` di queste misurazioni.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)