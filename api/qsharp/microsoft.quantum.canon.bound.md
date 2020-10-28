---
uid: Microsoft.Quantum.Canon.Bound
title: Funzione associata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716705"
---
# <a name="bound-function"></a><span data-ttu-id="cc8bf-102">Funzione associata</span><span class="sxs-lookup"><span data-stu-id="cc8bf-102">Bound function</span></span>

<span data-ttu-id="cc8bf-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc8bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc8bf-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc8bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc8bf-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="cc8bf-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="cc8bf-106">Input</span><span class="sxs-lookup"><span data-stu-id="cc8bf-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="cc8bf-107">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="cc8bf-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="cc8bf-108">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="cc8bf-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="cc8bf-109">Output:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="cc8bf-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cc8bf-110">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="cc8bf-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cc8bf-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="cc8bf-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc8bf-112">T</span><span class="sxs-lookup"><span data-stu-id="cc8bf-112">'T</span></span>

<span data-ttu-id="cc8bf-113">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="cc8bf-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc8bf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc8bf-114">See Also</span></span>

- [<span data-ttu-id="cc8bf-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="cc8bf-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="cc8bf-116">Microsoft. Quantum. Canon. Bounda</span><span class="sxs-lookup"><span data-stu-id="cc8bf-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="cc8bf-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="cc8bf-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)