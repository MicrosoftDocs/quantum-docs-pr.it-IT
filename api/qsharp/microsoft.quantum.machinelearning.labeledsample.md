---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definito dall'utente LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711332"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="71700-102">Tipo definito dall'utente LabeledSample</span><span class="sxs-lookup"><span data-stu-id="71700-102">LabeledSample user defined type</span></span>

<span data-ttu-id="71700-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="71700-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="71700-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71700-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71700-105">Esempio, etichettato con una classe a cui appartiene l'esempio.</span><span class="sxs-lookup"><span data-stu-id="71700-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="71700-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="71700-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="71700-107">Funzionalità: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="71700-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="71700-108">Vettore di funzionalità per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="71700-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="71700-109">Etichetta: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71700-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71700-110">Etichetta integer per la classe a cui appartiene l'esempio.</span><span class="sxs-lookup"><span data-stu-id="71700-110">An integer label for the class to which this sample belongs.</span></span>