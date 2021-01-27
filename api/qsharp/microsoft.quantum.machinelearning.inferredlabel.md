---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848411"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="2573d-102">InferredLabel (funzione)</span><span class="sxs-lookup"><span data-stu-id="2573d-102">InferredLabel function</span></span>

<span data-ttu-id="2573d-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2573d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2573d-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2573d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2573d-105">Data la probabilità di classificazione e la distorsione, restituisce l'etichetta dedotta da tale probabilità.</span><span class="sxs-lookup"><span data-stu-id="2573d-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="2573d-106">Input</span><span class="sxs-lookup"><span data-stu-id="2573d-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="2573d-107">distorsione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2573d-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2573d-108">Distorsione tra due classi, in genere il risultato del training di un classificatore.</span><span class="sxs-lookup"><span data-stu-id="2573d-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="2573d-109">probabilità: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2573d-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2573d-110">Probabilità di classificazione per un campione specifico, in genere risultanti dalla stima della relativa frequenza di classificazione.</span><span class="sxs-lookup"><span data-stu-id="2573d-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="2573d-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2573d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2573d-112">Etichetta dedotta dalla probabilità di classificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="2573d-112">The label inferred from the given classification probability.</span></span>