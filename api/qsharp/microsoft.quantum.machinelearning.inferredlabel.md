---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722519"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="44249-102">InferredLabel (funzione)</span><span class="sxs-lookup"><span data-stu-id="44249-102">InferredLabel function</span></span>

<span data-ttu-id="44249-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="44249-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="44249-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44249-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44249-105">Data la probabilità di classificazione e la distorsione, restituisce l'etichetta dedotta da tale probabilità.</span><span class="sxs-lookup"><span data-stu-id="44249-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="44249-106">Input</span><span class="sxs-lookup"><span data-stu-id="44249-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="44249-107">distorsione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44249-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44249-108">Distorsione tra due classi, in genere il risultato del training di un classificatore.</span><span class="sxs-lookup"><span data-stu-id="44249-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="44249-109">probabilità: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44249-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44249-110">Probabilità di classificazione per un campione specifico, in genere risultanti dalla stima della relativa frequenza di classificazione.</span><span class="sxs-lookup"><span data-stu-id="44249-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="44249-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44249-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44249-112">Etichetta dedotta dalla probabilità di classificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="44249-112">The label inferred from the given classification probability.</span></span>