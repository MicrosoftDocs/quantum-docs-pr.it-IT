---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844548"
---
# <a name="bounda-function"></a><span data-ttu-id="b6635-102">Bounda (funzione)</span><span class="sxs-lookup"><span data-stu-id="b6635-102">BoundA function</span></span>

<span data-ttu-id="b6635-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6635-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6635-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6635-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6635-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="b6635-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="b6635-106">Il modificatore `A` indica che tutte le operazioni nella matrice sono adjointable.</span><span class="sxs-lookup"><span data-stu-id="b6635-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="b6635-107">Input</span><span class="sxs-lookup"><span data-stu-id="b6635-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="b6635-108">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ []</span><span class="sxs-lookup"><span data-stu-id="b6635-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="b6635-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="b6635-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="b6635-110">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="b6635-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b6635-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="b6635-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b6635-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b6635-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6635-113">T</span><span class="sxs-lookup"><span data-stu-id="b6635-113">'T</span></span>

<span data-ttu-id="b6635-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="b6635-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="b6635-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6635-115">Example</span></span>

<span data-ttu-id="b6635-116">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b6635-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="b6635-117">e</span><span class="sxs-lookup"><span data-stu-id="b6635-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="b6635-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6635-118">See Also</span></span>

- [<span data-ttu-id="b6635-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="b6635-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)