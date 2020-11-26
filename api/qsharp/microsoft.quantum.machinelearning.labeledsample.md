---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definito dall'utente LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196328"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="f9354-102">Tipo definito dall'utente LabeledSample</span><span class="sxs-lookup"><span data-stu-id="f9354-102">LabeledSample user defined type</span></span>

<span data-ttu-id="f9354-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9354-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f9354-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9354-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f9354-105">Esempio, etichettato con una classe a cui appartiene l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f9354-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="f9354-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="f9354-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="f9354-107">Funzionalità: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f9354-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f9354-108">Vettore di funzionalità per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="f9354-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="f9354-109">Etichetta: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9354-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9354-110">Etichetta integer per la classe a cui appartiene l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f9354-110">An integer label for the class to which this sample belongs.</span></span>