---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funzione _IdentityTimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710688"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="c0732-102">Funzione _IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="c0732-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="c0732-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c0732-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c0732-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0732-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0732-105">Restituisce un sistema di generazione coerente con l'Hamiltoniana `H(s) = 0` , dove `s` è un parametro di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c0732-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c0732-106">Input</span><span class="sxs-lookup"><span data-stu-id="c0732-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="c0732-107">pianificazione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0732-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0732-108">Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c0732-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c0732-109">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c0732-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c0732-110">Sistema di generazione che rappresenta l'evoluzione nei $H hamiltoniana = $0 per tutti i $s $.</span><span class="sxs-lookup"><span data-stu-id="c0732-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>