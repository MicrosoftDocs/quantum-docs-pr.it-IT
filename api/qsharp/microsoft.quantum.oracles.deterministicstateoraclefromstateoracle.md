---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226758"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="38070-102">DeterministicStateOracleFromStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="38070-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="38070-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="38070-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="38070-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38070-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38070-105">Converte un oggetto Oracle di tipo `StateOracle` in `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="38070-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="38070-106">Input</span><span class="sxs-lookup"><span data-stu-id="38070-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="38070-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="38070-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="38070-108">Indice del flag qubit del `stateOracle` $A $, che agisce in modo esplicito su due registri: il flag $f $ e il sistema $s $, ad esempio $A \ket {0} \_ f\ket {\ psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="38070-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="38070-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="38070-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="38070-110">Una preparazione dello stato Oracle $A $ di tipo `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="38070-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="38070-111">Output: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="38070-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="38070-112">Lo stesso stato di preparazione Oracle $A $, ma ora di tipo `DeterministicStateOracle` , quindi agisce su un registro in cui $a, s $ non viene più separato in modo esplicito, ad esempio  $A \ket{0\psi} \_ {As} $.</span><span class="sxs-lookup"><span data-stu-id="38070-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="38070-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38070-113">See Also</span></span>

- [<span data-ttu-id="38070-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="38070-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="38070-115">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="38070-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)