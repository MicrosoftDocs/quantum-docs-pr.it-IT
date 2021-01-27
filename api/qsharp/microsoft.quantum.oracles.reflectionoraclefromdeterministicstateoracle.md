---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842517"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="0991c-102">ReflectionOracleFromDeterministicStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="0991c-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="0991c-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0991c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0991c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0991c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0991c-105">Costruisce la reflection su un dato stato da un Oracle.</span><span class="sxs-lookup"><span data-stu-id="0991c-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="0991c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0991c-106">Description</span></span>

<span data-ttu-id="0991c-107">Dato un Oracle di preparazione dello stato deterministico rappresentato da una matrice unitaria $O $, il risultato di questa funzione è un Oracle che applica una reflection intorno allo stato $ \ket{\psi} $ preparato da Oracle $O $; ovvero lo stato $ \ket{\psi} $ in modo che $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0991c-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="0991c-108">Input</span><span class="sxs-lookup"><span data-stu-id="0991c-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="0991c-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="0991c-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="0991c-110">Oracle che prepara copie dello stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0991c-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="0991c-111">Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="0991c-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="0991c-112">Oracle che riflette lo stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0991c-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="0991c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0991c-113">See Also</span></span>

- [<span data-ttu-id="0991c-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="0991c-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="0991c-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="0991c-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)