---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Operazione di ripristino
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712211"
---
# <a name="recover-operation"></a>Operazione di ripristino

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Esegue un singolo ciclo di correzione degli errori in base a un codice quantico descritto da un `QECC` tipo.

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Input

### <a name="code--qecc"></a>Codice: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Un codice di correzione degli errori Quantum in pacchetto come `QECC` tipo descrive la codifica e la decodifica dei dati quantistici e come devono essere misurate le sindromi degli errori.


### <a name="fn--recoveryfn"></a>FN: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di errore alle `Pauli[]` operazioni che correggono l'errore rilevato.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits in cui è definito il codice di stabilizzazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)