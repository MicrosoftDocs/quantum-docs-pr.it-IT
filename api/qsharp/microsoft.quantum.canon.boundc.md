---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716666"
---
# <a name="boundc-function"></a><span data-ttu-id="37c80-102">BoundC (funzione)</span><span class="sxs-lookup"><span data-stu-id="37c80-102">BoundC function</span></span>

<span data-ttu-id="37c80-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37c80-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37c80-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37c80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37c80-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="37c80-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="37c80-106">Il modificatore `C` indica che tutte le operazioni nella matrice sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="37c80-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="37c80-107">Input</span><span class="sxs-lookup"><span data-stu-id="37c80-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="37c80-108">operazioni:' t = [unità](xref:microsoft.quantum.lang-ref.unit) di> CTL []</span><span class="sxs-lookup"><span data-stu-id="37c80-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="37c80-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="37c80-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="37c80-110">Output:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37c80-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="37c80-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="37c80-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="37c80-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="37c80-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37c80-113">T</span><span class="sxs-lookup"><span data-stu-id="37c80-113">'T</span></span>

<span data-ttu-id="37c80-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="37c80-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="37c80-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37c80-115">See Also</span></span>

- [<span data-ttu-id="37c80-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="37c80-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)