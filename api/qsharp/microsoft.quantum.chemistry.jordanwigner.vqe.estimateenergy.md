---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operazione EstimateEnergy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: a64ac3970e3e67568f91b4e67775d834a80c04a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835719"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="bb62d-102">Operazione EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="bb62d-102">EstimateEnergy operation</span></span>

<span data-ttu-id="bb62d-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="bb62d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="bb62d-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bb62d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bb62d-105">Stima l'energia della molecola sommando l'energia fornita dai singoli termini di Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="bb62d-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="bb62d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb62d-106">Description</span></span>

<span data-ttu-id="bb62d-107">Questa operazione si basa in modo implicito sulla convenzione di indicizzazione della selezione.</span><span class="sxs-lookup"><span data-stu-id="bb62d-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="bb62d-108">Input</span><span class="sxs-lookup"><span data-stu-id="bb62d-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="bb62d-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="bb62d-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="bb62d-110">Il Jordan-Wigner hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="bb62d-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="bb62d-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb62d-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb62d-112">Il numero di campioni da utilizzare per la stima del termine aspettative.</span><span class="sxs-lookup"><span data-stu-id="bb62d-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="bb62d-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb62d-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb62d-114">Energia stimata della molecola</span><span class="sxs-lookup"><span data-stu-id="bb62d-114">The estimated energy of the molecule</span></span>