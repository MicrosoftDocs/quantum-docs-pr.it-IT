---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841040"
---
# <a name="boundc-function"></a><span data-ttu-id="231a8-102">BoundC (funzione)</span><span class="sxs-lookup"><span data-stu-id="231a8-102">BoundC function</span></span>

<span data-ttu-id="231a8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="231a8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="231a8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="231a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="231a8-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="231a8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="231a8-106">Il modificatore `C` indica che tutte le operazioni nella matrice sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="231a8-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="231a8-107">Input</span><span class="sxs-lookup"><span data-stu-id="231a8-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="231a8-108">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL []</span><span class="sxs-lookup"><span data-stu-id="231a8-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="231a8-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="231a8-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="231a8-110">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="231a8-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="231a8-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="231a8-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="231a8-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="231a8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="231a8-113">T</span><span class="sxs-lookup"><span data-stu-id="231a8-113">'T</span></span>

<span data-ttu-id="231a8-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="231a8-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="231a8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="231a8-115">Example</span></span>

<span data-ttu-id="231a8-116">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="231a8-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="231a8-117">e</span><span class="sxs-lookup"><span data-stu-id="231a8-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="231a8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="231a8-118">See Also</span></span>

- [<span data-ttu-id="231a8-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="231a8-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)