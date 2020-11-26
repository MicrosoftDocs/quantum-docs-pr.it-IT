---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200782"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una funzione che esegue il mapping delle misurazioni della sindrome di errore alla correzione degli errori appropriata degli operatori Pauli mediante ricerca nella tabella per il codice quantico ⟧ ⟦ 5, 1, 3.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Output: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Funzione di tipo `RecoveryFn` che accetta una misurazione della sindrome `Result[]` e restituisce gli `Pauli[]` operatori che correggono l'errore rilevato.

## <a name="remarks"></a>Commenti

Scorrendo tutti gli errori di peso $1 $, si ottiene un totale di $3 \ volte 5 = 15 $ possibili sindromi non semplici.
Insieme all'identità, viene compilata una tabella di errori e una sindrome corrispondente. Per il codice 5 qubit questa tabella viene fornita da: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ con $Y _i $ ottenuta aggiungendo la $X _i $ e $Z _i $ sindroms. Si noti che l'ordinamento nel ripristino della ricerca della tabella viene fornito convertendo bitvectors in numeri interi (usando little endian).

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)