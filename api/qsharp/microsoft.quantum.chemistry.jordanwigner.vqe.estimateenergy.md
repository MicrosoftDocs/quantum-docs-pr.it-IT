---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operazione EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713751"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="e76b5-102">Operazione EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="e76b5-102">EstimateEnergy operation</span></span>

<span data-ttu-id="e76b5-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="e76b5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="e76b5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e76b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e76b5-105">Stima l'energia della molecola sommando l'energia fornita dai singoli termini di Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="e76b5-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="e76b5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e76b5-106">Description</span></span>

<span data-ttu-id="e76b5-107">Questa operazione si basa in modo implicito sulla convenzione di indicizzazione della selezione.</span><span class="sxs-lookup"><span data-stu-id="e76b5-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="e76b5-108">Input</span><span class="sxs-lookup"><span data-stu-id="e76b5-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="e76b5-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="e76b5-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="e76b5-110">Il Jordan-Wigner hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="e76b5-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="e76b5-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e76b5-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e76b5-112">Il numero di campioni da utilizzare per la stima del termine aspettative.</span><span class="sxs-lookup"><span data-stu-id="e76b5-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="e76b5-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e76b5-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e76b5-114">Energia stimata della molecola</span><span class="sxs-lookup"><span data-stu-id="e76b5-114">The estimated energy of the molecule</span></span>