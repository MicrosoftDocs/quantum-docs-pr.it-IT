---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Tipo definito dall'utente ValidationResults
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211492"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="db2e3-102">Tipo definito dall'utente ValidationResults</span><span class="sxs-lookup"><span data-stu-id="db2e3-102">ValidationResults user defined type</span></span>

<span data-ttu-id="db2e3-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db2e3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="db2e3-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db2e3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="db2e3-105">Risultato della convalida di un classificatore rispetto a un set di campioni.</span><span class="sxs-lookup"><span data-stu-id="db2e3-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="db2e3-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="db2e3-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="db2e3-107">NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db2e3-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db2e3-108">Numero di classificazioni errate osservate durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="db2e3-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="db2e3-109">NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db2e3-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

