---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funzione di classificazione errata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853921"
---
# <a name="misclassifications-function"></a><span data-ttu-id="ea1d7-102">Funzione di classificazione errata</span><span class="sxs-lookup"><span data-stu-id="ea1d7-102">Misclassifications function</span></span>

<span data-ttu-id="ea1d7-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ea1d7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ea1d7-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ea1d7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ea1d7-105">Dato un set di etichette derivate e un set di etichette corrette, restituisce gli indici per i casi in cui ogni set di etichette è diverso.</span><span class="sxs-lookup"><span data-stu-id="ea1d7-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ea1d7-106">Input</span><span class="sxs-lookup"><span data-stu-id="ea1d7-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="ea1d7-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ea1d7-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ea1d7-108">Etichette dedotte per un determinato training o set di convalida.</span><span class="sxs-lookup"><span data-stu-id="ea1d7-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="ea1d7-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ea1d7-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ea1d7-110">Etichette vere per un determinato training o set di convalida.</span><span class="sxs-lookup"><span data-stu-id="ea1d7-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="ea1d7-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ea1d7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ea1d7-112">Matrice di indici di questo `idx` tipo `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="ea1d7-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="ea1d7-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea1d7-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```