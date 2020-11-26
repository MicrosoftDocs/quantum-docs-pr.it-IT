---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operazione ApplyBlockEncodingByLCU
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225483"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="c925d-102">Operazione ApplyBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="c925d-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="c925d-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c925d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c925d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c925d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c925d-105">Implementazione di `BlockEncodingByLCU`.</span><span class="sxs-lookup"><span data-stu-id="c925d-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c925d-106">Input</span><span class="sxs-lookup"><span data-stu-id="c925d-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="c925d-107">statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c925d-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="c925d-108">selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c925d-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="c925d-109">ausiliario:' t</span><span class="sxs-lookup"><span data-stu-id="c925d-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="c925d-110">sistema:</span><span class="sxs-lookup"><span data-stu-id="c925d-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="c925d-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c925d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c925d-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c925d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c925d-113">T</span><span class="sxs-lookup"><span data-stu-id="c925d-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="c925d-114">Gli</span><span class="sxs-lookup"><span data-stu-id="c925d-114">'S</span></span>

