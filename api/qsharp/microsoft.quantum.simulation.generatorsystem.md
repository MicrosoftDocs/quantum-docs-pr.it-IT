---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definito dall'utente GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724563"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="8181d-102">Tipo definito dall'utente GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="8181d-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="8181d-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8181d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8181d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8181d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8181d-105">Rappresenta una raccolta di `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="8181d-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="8181d-106">Viene eseguita l'iterazione della raccolta usando un Integer a indice singolo e la dimensione della raccolta si presuppone che sia nota.</span><span class="sxs-lookup"><span data-stu-id="8181d-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="8181d-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="8181d-107">Remarks</span></span>

<span data-ttu-id="8181d-108">`GeneratorSystem`È possibile definire facilmente le istanze di utilizzando la <xref:microsoft.quantum.arrays.lookupfunction> funzione.</span><span class="sxs-lookup"><span data-stu-id="8181d-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8181d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8181d-109">See Also</span></span>

- [<span data-ttu-id="8181d-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="8181d-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)