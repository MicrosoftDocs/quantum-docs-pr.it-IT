---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definito dall'utente GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858416"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="3fb24-102">Tipo definito dall'utente GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3fb24-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="3fb24-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3fb24-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3fb24-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fb24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fb24-105">Rappresenta una raccolta di `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="3fb24-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="3fb24-106">Viene eseguita l'iterazione della raccolta usando un Integer a indice singolo e la dimensione della raccolta si presuppone che sia nota.</span><span class="sxs-lookup"><span data-stu-id="3fb24-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="3fb24-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="3fb24-107">Remarks</span></span>

<span data-ttu-id="3fb24-108">`GeneratorSystem`È possibile definire facilmente le istanze di utilizzando la <xref:microsoft.quantum.arrays.lookupfunction> funzione.</span><span class="sxs-lookup"><span data-stu-id="3fb24-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fb24-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fb24-109">See Also</span></span>

- [<span data-ttu-id="3fb24-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="3fb24-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)