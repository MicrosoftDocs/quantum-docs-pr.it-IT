---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operazione MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856123"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="107fd-102">Operazione MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="107fd-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="107fd-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="107fd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="107fd-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="107fd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="107fd-105">Data una matrice di dati e una distribuzione sugli indici, tenta di scegliere un elemento in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="107fd-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="107fd-106">Input</span><span class="sxs-lookup"><span data-stu-id="107fd-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="107fd-107">dati:' t []</span><span class="sxs-lookup"><span data-stu-id="107fd-107">data : 'T[]</span></span>

<span data-ttu-id="107fd-108">Matrice da cui scegliere un elemento.</span><span class="sxs-lookup"><span data-stu-id="107fd-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="107fd-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="107fd-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="107fd-110">Distribuzione sugli indici di `data` .</span><span class="sxs-lookup"><span data-stu-id="107fd-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="107fd-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t)</span><span class="sxs-lookup"><span data-stu-id="107fd-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="107fd-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="107fd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="107fd-113">T</span><span class="sxs-lookup"><span data-stu-id="107fd-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="107fd-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="107fd-114">Example</span></span>

<span data-ttu-id="107fd-115">Il frammento di codice Q # seguente sceglie un elemento in modo casuale da una matrice:</span><span class="sxs-lookup"><span data-stu-id="107fd-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```