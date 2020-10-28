---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definito dall'utente GeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723905"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="7746e-102">Tipo definito dall'utente GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="7746e-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="7746e-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7746e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7746e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7746e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7746e-105">Rappresenta un singolo termine primitivo nel set di tutti i generatori dinamici, ad esempio operatori hermitiane, per i quali esiste una mappa da tale generatore a Time-Evolution da parte del generatore, fino a `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="7746e-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="7746e-106">Il primo elemento (int [], Double []) è indicizzato con un solo termine, ad esempio, la stringa di Pauli XXY con coefficient 0,5 verrebbe indicizzata da ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="7746e-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="7746e-107">In alternativa, è possibile che i parametri hamiltonians da una variabile continua, ad esempio X cos φ + Y sin φ, siano rappresentati da ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="7746e-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="7746e-108">Il secondo elemento indicizza il sottosistema su cui agisce il generatore.</span><span class="sxs-lookup"><span data-stu-id="7746e-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="7746e-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="7746e-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="7746e-110">L'interpretazione di un oggetto `GeneratorIndex` non è definita ad eccezione del riferimento a un determinato set di generatori.</span><span class="sxs-lookup"><span data-stu-id="7746e-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="7746e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7746e-111">See Also</span></span>

- [<span data-ttu-id="7746e-112">Microsoft. Quantum. Simulation. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="7746e-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="7746e-113">Microsoft. Quantum. Simulation. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="7746e-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)