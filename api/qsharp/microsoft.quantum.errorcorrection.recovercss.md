---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Operazione RecoverCSS
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: c192abbdfd02b26fbdba7b11f51ed08bb1a2030f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853045"
---
# <a name="recovercss-operation"></a>Operazione RecoverCSS

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue un singolo ciclo di correzione degli errori in base a un codice quantico descritto da un `CSS` tipo.

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Input

### <a name="code--css"></a>Codice: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Un errore CSS Quantum: la correzione del codice in pacchetto come `CSS` tipo descrive la codifica e la decodifica dei dati quantistici e come devono essere misurate le sindromi degli errori.


### <a name="fnx--recoveryfn"></a>fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di $X $ Error alle `Pauli[]` operazioni che correggono l'errore rilevato.


### <a name="fnz--recoveryfn"></a>fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Oggetto `RecoveryFn` che esegue il mapping di ogni sindrome di $Z $ Error alle `Pauli[]` operazioni che correggono l'errore rilevato.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits in cui è definito il codice di stabilizzazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)