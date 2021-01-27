---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844522"
---
# <a name="boundca-function"></a><span data-ttu-id="c5e07-102">BoundCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="c5e07-102">BoundCA function</span></span>

<span data-ttu-id="c5e07-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5e07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5e07-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5e07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5e07-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="c5e07-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="c5e07-106">Il modificatore `CA` indica che tutte le operazioni nella matrice sono adjointable e controllabili.</span><span class="sxs-lookup"><span data-stu-id="c5e07-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c5e07-107">Input</span><span class="sxs-lookup"><span data-stu-id="c5e07-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="c5e07-108">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="c5e07-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="c5e07-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="c5e07-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="c5e07-110">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c5e07-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c5e07-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="c5e07-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5e07-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c5e07-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5e07-113">T</span><span class="sxs-lookup"><span data-stu-id="c5e07-113">'T</span></span>

<span data-ttu-id="c5e07-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="c5e07-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="c5e07-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5e07-115">Example</span></span>

<span data-ttu-id="c5e07-116">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c5e07-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="c5e07-117">e</span><span class="sxs-lookup"><span data-stu-id="c5e07-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="c5e07-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5e07-118">See Also</span></span>

- [<span data-ttu-id="c5e07-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="c5e07-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)