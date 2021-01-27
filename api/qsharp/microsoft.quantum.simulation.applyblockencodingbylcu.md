---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operazione ApplyBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852817"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="c0aab-102">Operazione ApplyBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="c0aab-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="c0aab-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c0aab-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c0aab-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0aab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0aab-105">Implementazione di `BlockEncodingByLCU`.</span><span class="sxs-lookup"><span data-stu-id="c0aab-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c0aab-106">Input</span><span class="sxs-lookup"><span data-stu-id="c0aab-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="c0aab-107">statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c0aab-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="c0aab-108">selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c0aab-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="c0aab-109">ausiliario:' t</span><span class="sxs-lookup"><span data-stu-id="c0aab-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="c0aab-110">sistema:</span><span class="sxs-lookup"><span data-stu-id="c0aab-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="c0aab-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0aab-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c0aab-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c0aab-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0aab-113">T</span><span class="sxs-lookup"><span data-stu-id="c0aab-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="c0aab-114">Gli</span><span class="sxs-lookup"><span data-stu-id="c0aab-114">'S</span></span>

