---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712326"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="004cd-102">FiveQubitCodeRecoveryFn (funzione)</span><span class="sxs-lookup"><span data-stu-id="004cd-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="004cd-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="004cd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="004cd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="004cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="004cd-105">Restituisce una funzione che esegue il mapping delle misurazioni della sindrome di errore alla correzione degli errori appropriata degli operatori Pauli mediante ricerca nella tabella per il codice quantico ⟧ ⟦ 5, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="004cd-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="004cd-106">Output: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="004cd-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="004cd-107">Funzione di tipo `RecoveryFn` che accetta una misurazione della sindrome `Result[]` e restituisce gli `Pauli[]` operatori che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="004cd-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="004cd-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="004cd-108">Remarks</span></span>

<span data-ttu-id="004cd-109">Scorrendo tutti gli errori di peso $1 $, si ottiene un totale di $3 \ volte 5 = 15 $ possibili sindromi non semplici.</span><span class="sxs-lookup"><span data-stu-id="004cd-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="004cd-110">Insieme all'identità, viene compilata una tabella di errori e una sindrome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="004cd-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="004cd-111">Per il codice 5 qubit questa tabella viene fornita da: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ con $Y _i $ ottenuta aggiungendo la $X _i $ e $Z _i $ sindroms.</span><span class="sxs-lookup"><span data-stu-id="004cd-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="004cd-112">Si noti che l'ordinamento nel ripristino della ricerca della tabella viene fornito convertendo bitvectors in numeri interi (usando little endian).</span><span class="sxs-lookup"><span data-stu-id="004cd-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="004cd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="004cd-113">See Also</span></span>

- [<span data-ttu-id="004cd-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="004cd-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)