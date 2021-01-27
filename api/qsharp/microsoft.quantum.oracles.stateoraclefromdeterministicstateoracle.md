---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842512"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="e25c1-102">StateOracleFromDeterministicStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="e25c1-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="e25c1-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e25c1-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e25c1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e25c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e25c1-105">Converte un oggetto Oracle di tipo `DeterministicStateOracle` in `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="e25c1-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="e25c1-106">Input</span><span class="sxs-lookup"><span data-stu-id="e25c1-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="e25c1-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="e25c1-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="e25c1-108">Una preparazione dello stato Oracle $A $ di tipo `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="e25c1-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="e25c1-109">Output: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e25c1-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e25c1-110">Lo stesso stato di preparazione Oracle $A $, ma ora di tipo `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="e25c1-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="e25c1-111">Si noti che l'indice del flag in questo `StateOracle` oggetto è una variabile fittizia e non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e25c1-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="e25c1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25c1-112">See Also</span></span>

- [<span data-ttu-id="e25c1-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="e25c1-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="e25c1-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="e25c1-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)