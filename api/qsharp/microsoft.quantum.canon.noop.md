---
uid: Microsoft.Quantum.Canon.NoOp
title: Operazione NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715756"
---
# <a name="noop-operation"></a><span data-ttu-id="95690-102">Operazione NoOp</span><span class="sxs-lookup"><span data-stu-id="95690-102">NoOp operation</span></span>

<span data-ttu-id="95690-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95690-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95690-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95690-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95690-105">Esegue l'operazione di identità (no-op) su un argomento.</span><span class="sxs-lookup"><span data-stu-id="95690-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="95690-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95690-106">Description</span></span>

<span data-ttu-id="95690-107">Questa operazione accetta un valore di qualsiasi tipo e non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="95690-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="95690-108">Questo può essere utile quando è previsto un input di un tipo di operazione, ma non è necessario intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="95690-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="95690-109">Se, ad esempio, una particolare sindrome di correzione degli errori indica che non si è verificato alcun errore, `NoOp<Qubit[]>` può essere la procedura di recupero corretta.</span><span class="sxs-lookup"><span data-stu-id="95690-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="95690-110">Analogamente, se un'operazione prevede una procedura di preparazione dello stato come input, `NoOp<Qubit[]>` può essere usata per preparare lo stato $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="95690-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="95690-111">Input</span><span class="sxs-lookup"><span data-stu-id="95690-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="95690-112">input:' t</span><span class="sxs-lookup"><span data-stu-id="95690-112">input : 'T</span></span>

<span data-ttu-id="95690-113">Valore da ignorare.</span><span class="sxs-lookup"><span data-stu-id="95690-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95690-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95690-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95690-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="95690-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95690-116">T</span><span class="sxs-lookup"><span data-stu-id="95690-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="95690-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="95690-117">Remarks</span></span>

<span data-ttu-id="95690-118">In quasi tutti i casi, il parametro di tipo per `NoOp` deve essere specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="95690-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="95690-119">Ad esempio, `NoOp<Qubit>` è identico a <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="95690-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="95690-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95690-120">See Also</span></span>

- [<span data-ttu-id="95690-121">Microsoft. Quantum. Intrinsic. I</span><span class="sxs-lookup"><span data-stu-id="95690-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)