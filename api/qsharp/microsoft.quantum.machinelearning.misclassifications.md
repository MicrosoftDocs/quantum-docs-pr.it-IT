---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funzione di classificazione errata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723583"
---
# <a name="misclassifications-function"></a><span data-ttu-id="1f6ac-102">Funzione di classificazione errata</span><span class="sxs-lookup"><span data-stu-id="1f6ac-102">Misclassifications function</span></span>

<span data-ttu-id="1f6ac-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1f6ac-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1f6ac-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f6ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f6ac-105">Dato un set di etichette derivate e un set di etichette corrette, restituisce gli indici per i casi in cui ogni set di etichette è diverso.</span><span class="sxs-lookup"><span data-stu-id="1f6ac-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="1f6ac-106">Input</span><span class="sxs-lookup"><span data-stu-id="1f6ac-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="1f6ac-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f6ac-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f6ac-108">Etichette dedotte per un determinato training o set di convalida.</span><span class="sxs-lookup"><span data-stu-id="1f6ac-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="1f6ac-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f6ac-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f6ac-110">Etichette vere per un determinato training o set di convalida.</span><span class="sxs-lookup"><span data-stu-id="1f6ac-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="1f6ac-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f6ac-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f6ac-112">Matrice di indici di questo `idx` tipo `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="1f6ac-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>