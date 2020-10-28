---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712141"
---
# <a name="steanecoderecoveryfns-function"></a>SteaneCodeRecoveryFns (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Decodificatore per le parti X e Z combinate del gruppo stabilizzatore del codice Quantum Steane ⟧ ⟦ 7, 1, 3.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Output: ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))

Tupla di funzioni di tipo `RecoveryFn` che accetta una misurazione della sindrome `Result[]` e restituisce le `Pauli[]` operazioni che correggono l'errore rilevato.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)