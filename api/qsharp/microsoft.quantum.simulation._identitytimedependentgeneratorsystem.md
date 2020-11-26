---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funzione _IdentityTimeDependentGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225602"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="03c0a-102">Funzione _IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="03c0a-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="03c0a-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="03c0a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="03c0a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03c0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03c0a-105">Restituisce un sistema di generazione coerente con l'Hamiltoniana `H(s) = 0` , dove `s` è un parametro di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="03c0a-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="03c0a-106">Input</span><span class="sxs-lookup"><span data-stu-id="03c0a-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="03c0a-107">pianificazione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="03c0a-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="03c0a-108">Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="03c0a-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="03c0a-109">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="03c0a-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="03c0a-110">Sistema di generazione che rappresenta l'evoluzione nei $H hamiltoniana = $0 per tutti i $s $.</span><span class="sxs-lookup"><span data-stu-id="03c0a-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>