---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funzione _IdentityTimeDependentGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857997"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="059b0-102">Funzione _IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="059b0-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="059b0-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="059b0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="059b0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="059b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="059b0-105">Restituisce un sistema di generazione coerente con l'Hamiltoniana `H(s) = 0` , dove `s` è un parametro di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="059b0-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="059b0-106">Input</span><span class="sxs-lookup"><span data-stu-id="059b0-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="059b0-107">pianificazione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="059b0-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="059b0-108">Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="059b0-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="059b0-109">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="059b0-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="059b0-110">Sistema di generazione che rappresenta l'evoluzione nei $H hamiltoniana = $0 per tutti i $s $.</span><span class="sxs-lookup"><span data-stu-id="059b0-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>