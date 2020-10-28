---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722183"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="5e3bf-102">ReflectionOracleFromDeterministicStateOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="5e3bf-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="5e3bf-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5e3bf-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5e3bf-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e3bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e3bf-105">Costruisce la reflection su un dato stato da un Oracle.</span><span class="sxs-lookup"><span data-stu-id="5e3bf-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="5e3bf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e3bf-106">Description</span></span>

<span data-ttu-id="5e3bf-107">Dato un Oracle di preparazione dello stato deterministico rappresentato da una matrice unitaria $O $, il risultato di questa funzione è un Oracle che applica una reflection intorno allo stato $ \ket{\psi} $ preparato da Oracle $O $; ovvero lo stato $ \ket{\psi} $ in modo che $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="5e3bf-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="5e3bf-108">Input</span><span class="sxs-lookup"><span data-stu-id="5e3bf-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="5e3bf-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="5e3bf-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="5e3bf-110">Oracle che prepara copie dello stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="5e3bf-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="5e3bf-111">Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="5e3bf-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="5e3bf-112">Oracle che riflette lo stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="5e3bf-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e3bf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e3bf-113">See Also</span></span>

- [<span data-ttu-id="5e3bf-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="5e3bf-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="5e3bf-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="5e3bf-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)