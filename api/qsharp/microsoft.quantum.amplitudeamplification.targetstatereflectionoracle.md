---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843899"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="1f88d-102">TargetStateReflectionOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="1f88d-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="1f88d-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1f88d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1f88d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f88d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f88d-105">Costruisce un oggetto `ReflectionOracle` sullo stato di destinazione in modo univoco contrassegnato dal flag qubit.</span><span class="sxs-lookup"><span data-stu-id="1f88d-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="1f88d-106">Lo stato di destinazione ha un solo qubit impostato su 1 e tutti gli altri 0: $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="1f88d-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="1f88d-107">Input</span><span class="sxs-lookup"><span data-stu-id="1f88d-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="1f88d-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f88d-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f88d-109">Indice per contrassegnare qubit $f $ di Oracle.</span><span class="sxs-lookup"><span data-stu-id="1f88d-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="1f88d-110">Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="1f88d-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="1f88d-111">Oggetto `ReflectionOracle` che riflette lo stato contrassegnato da $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="1f88d-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f88d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f88d-112">See Also</span></span>

- [<span data-ttu-id="1f88d-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="1f88d-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)