---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 8dc715042f98b90b8cea7e2d6ecb5d02a78d297f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853017"
---
# <a name="steanecoderecoveryfns-function"></a>SteaneCodeRecoveryFns (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Decodificatore per le parti X e Z combinate del gruppo stabilizzatore del codice Quantum Steane ⟧ ⟦ 7, 1, 3.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Output: ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))

Tupla di funzioni di tipo `RecoveryFn` che accetta una misurazione della sindrome `Result[]` e restituisce le `Pauli[]` operazioni che correggono l'errore rilevato.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)