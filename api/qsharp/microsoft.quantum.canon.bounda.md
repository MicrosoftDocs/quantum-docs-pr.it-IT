---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716691"
---
# <a name="bounda-function"></a><span data-ttu-id="5a3c2-102">Bounda (funzione)</span><span class="sxs-lookup"><span data-stu-id="5a3c2-102">BoundA function</span></span>

<span data-ttu-id="5a3c2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a3c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a3c2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a3c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a3c2-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="5a3c2-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="5a3c2-106">Il modificatore `A` indica che tutte le operazioni nella matrice sono adjointable.</span><span class="sxs-lookup"><span data-stu-id="5a3c2-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="5a3c2-107">Input</span><span class="sxs-lookup"><span data-stu-id="5a3c2-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="5a3c2-108">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ []</span><span class="sxs-lookup"><span data-stu-id="5a3c2-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="5a3c2-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="5a3c2-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="5a3c2-110">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="5a3c2-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5a3c2-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="5a3c2-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5a3c2-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5a3c2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a3c2-113">T</span><span class="sxs-lookup"><span data-stu-id="5a3c2-113">'T</span></span>

<span data-ttu-id="5a3c2-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="5a3c2-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a3c2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a3c2-115">See Also</span></span>

- [<span data-ttu-id="5a3c2-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="5a3c2-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)