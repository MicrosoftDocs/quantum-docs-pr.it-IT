---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definito dall'utente SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850047"
---
# <a name="syndromemeasop-user-defined-type"></a>Tipo definito dall'utente SyndromeMeasOp

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un'operazione utilizzata per misurare la sindrome di un blocco di codice di correzione degli errori.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a>Esempio

Le sindromi delle misure per il codice di Flip bit $S = \langle ZZI, IZZ \rangle $ using Scratch qubits in un modo non a tolleranza di errore:

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a>Commenti

La firma `(LogicalRegister => Syndrome)` rappresenta un'operazione che agisce congiuntamente sul qubits in `LogicalRegister` e alcuni qubits ausiliari seguito da una misura del qubits ausiliario per estrarre un `Syndrome` valore che rappresenta l'oggetto `Result[]` di queste misurazioni.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)