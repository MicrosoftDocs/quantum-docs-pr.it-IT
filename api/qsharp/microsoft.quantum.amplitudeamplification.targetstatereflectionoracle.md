---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191109"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="b0457-102">TargetStateReflectionOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="b0457-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="b0457-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b0457-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b0457-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0457-105">Costruisce un oggetto `ReflectionOracle` sullo stato di destinazione in modo univoco contrassegnato dal flag qubit.</span><span class="sxs-lookup"><span data-stu-id="b0457-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="b0457-106">Lo stato di destinazione ha un solo qubit impostato su 1 e tutti gli altri 0: $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="b0457-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="b0457-107">Input</span><span class="sxs-lookup"><span data-stu-id="b0457-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="b0457-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0457-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0457-109">Indice per contrassegnare qubit $f $ di Oracle.</span><span class="sxs-lookup"><span data-stu-id="b0457-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="b0457-110">Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b0457-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b0457-111">Oggetto `ReflectionOracle` che riflette lo stato contrassegnato da $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="b0457-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0457-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0457-112">See Also</span></span>

- [<span data-ttu-id="b0457-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b0457-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)