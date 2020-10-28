---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724244"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="6f2d0-102">OracleToDiscrete (funzione)</span><span class="sxs-lookup"><span data-stu-id="6f2d0-102">OracleToDiscrete function</span></span>

<span data-ttu-id="6f2d0-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6f2d0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6f2d0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f2d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f2d0-105">Data un'operazione che rappresenta un Oracle "black-box", restituisce un Oracle a tempo discreto che rappresenta il "black-box" Oracle ripetuto più volte.</span><span class="sxs-lookup"><span data-stu-id="6f2d0-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="6f2d0-106">Input</span><span class="sxs-lookup"><span data-stu-id="6f2d0-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="6f2d0-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6f2d0-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6f2d0-108">Operazione da exponentiatedre.</span><span class="sxs-lookup"><span data-stu-id="6f2d0-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="6f2d0-109">Output: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="6f2d0-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="6f2d0-110">Un'operazione è stata applicata parzialmente sul Oracle "black-box" che rappresenta l'Oracle a tempo discreto</span><span class="sxs-lookup"><span data-stu-id="6f2d0-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>