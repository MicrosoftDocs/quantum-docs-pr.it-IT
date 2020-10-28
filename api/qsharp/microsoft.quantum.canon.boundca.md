---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716635"
---
# <a name="boundca-function"></a><span data-ttu-id="3d313-102">BoundCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="3d313-102">BoundCA function</span></span>

<span data-ttu-id="3d313-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3d313-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3d313-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d313-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d313-105">Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.</span><span class="sxs-lookup"><span data-stu-id="3d313-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="3d313-106">Il modificatore `CA` indica che tutte le operazioni nella matrice sono adjointable e controllabili.</span><span class="sxs-lookup"><span data-stu-id="3d313-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="3d313-107">Input</span><span class="sxs-lookup"><span data-stu-id="3d313-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="3d313-108">operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="3d313-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="3d313-109">Sequenza di operazioni da eseguire su un input specificato.</span><span class="sxs-lookup"><span data-stu-id="3d313-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="3d313-110">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3d313-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3d313-111">Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.</span><span class="sxs-lookup"><span data-stu-id="3d313-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3d313-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3d313-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3d313-113">T</span><span class="sxs-lookup"><span data-stu-id="3d313-113">'T</span></span>

<span data-ttu-id="3d313-114">Destinazione in cui ogni operazione nell'array agisce.</span><span class="sxs-lookup"><span data-stu-id="3d313-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d313-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d313-115">See Also</span></span>

- [<span data-ttu-id="3d313-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="3d313-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)