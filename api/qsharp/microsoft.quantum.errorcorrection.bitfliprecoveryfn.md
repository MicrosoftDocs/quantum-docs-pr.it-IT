---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712494"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="69eec-102">BitFlipRecoveryFn (funzione)</span><span class="sxs-lookup"><span data-stu-id="69eec-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="69eec-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="69eec-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="69eec-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69eec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69eec-105">Funzione per il recupero delle operazioni di Pauli per la misurazione della sindrome specificata mediante ricerca di tabelle per il codice Flip ⟦ 3, 1, 1 ⟧ bit.</span><span class="sxs-lookup"><span data-stu-id="69eec-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="69eec-106">Output: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="69eec-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="69eec-107">Funzione di tipo `RecoveryFn` che accetta una misurazione della sindrome `Result[]` e restituisce le `Pauli[]` operazioni che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="69eec-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="69eec-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69eec-108">See Also</span></span>

- [<span data-ttu-id="69eec-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="69eec-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)