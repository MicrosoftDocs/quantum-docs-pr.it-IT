---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Operazione RecoverCSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712200"
---
# <a name="recovercss-operation"></a>Operazione RecoverCSS

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


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