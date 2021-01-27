---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854548"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="7af6f-102">DeterministicStateOracleFromStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="7af6f-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="7af6f-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="7af6f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="7af6f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7af6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7af6f-105">Converte un oggetto Oracle di tipo `StateOracle` in `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="7af6f-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="7af6f-106">Input</span><span class="sxs-lookup"><span data-stu-id="7af6f-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="7af6f-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7af6f-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7af6f-108">Indice del flag qubit del `stateOracle` $A $, che agisce in modo esplicito su due registri: il flag $f $ e il sistema $s $, ad esempio $A \ket {0} \_ f\ket {\ psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="7af6f-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="7af6f-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="7af6f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="7af6f-110">Una preparazione dello stato Oracle $A $ di tipo `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="7af6f-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="7af6f-111">Output: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="7af6f-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="7af6f-112">Lo stesso stato di preparazione Oracle $A $, ma ora di tipo `DeterministicStateOracle` , quindi agisce su un registro in cui $a, s $ non viene più separato in modo esplicito, ad esempio  $A \ket{0\psi} \_ {As} $.</span><span class="sxs-lookup"><span data-stu-id="7af6f-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af6f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af6f-113">See Also</span></span>

- [<span data-ttu-id="7af6f-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="7af6f-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="7af6f-115">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="7af6f-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)