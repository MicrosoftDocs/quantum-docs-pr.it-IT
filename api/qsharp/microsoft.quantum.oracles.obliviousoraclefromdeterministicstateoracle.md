---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 8f1fe34e38edefba228fb9d01e1712e4c0916970
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226690"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="7af48-102">ObliviousOracleFromDeterministicStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="7af48-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="7af48-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="7af48-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="7af48-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7af48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7af48-105">Combina gli Oracle `DeterministicStateOracle` e `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="7af48-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="7af48-106">Input</span><span class="sxs-lookup"><span data-stu-id="7af48-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="7af48-107">ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="7af48-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="7af48-108">Una preparazione dello stato Oracle $A $ di tipo che `DeterministicStateOracle` agisce al registro $a $.</span><span class="sxs-lookup"><span data-stu-id="7af48-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="7af48-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="7af48-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="7af48-110">Una $U Oracle $ di tipo che `ObliviousOracle` agisce congiuntamente sul $a di registrazione, s $.</span><span class="sxs-lookup"><span data-stu-id="7af48-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="7af48-111">Output: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="7af48-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="7af48-112">Oracle $O = UA $ di tipo `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="7af48-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af48-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af48-113">See Also</span></span>

- [<span data-ttu-id="7af48-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="7af48-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="7af48-115">Microsoft. Quantum. Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="7af48-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)