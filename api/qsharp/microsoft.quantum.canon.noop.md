---
uid: Microsoft.Quantum.Canon.NoOp
title: Operazione NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852401"
---
# <a name="noop-operation"></a><span data-ttu-id="333c2-102">Operazione NoOp</span><span class="sxs-lookup"><span data-stu-id="333c2-102">NoOp operation</span></span>

<span data-ttu-id="333c2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="333c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="333c2-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="333c2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="333c2-105">Esegue l'operazione di identità (no-op) su un argomento.</span><span class="sxs-lookup"><span data-stu-id="333c2-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="333c2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="333c2-106">Description</span></span>

<span data-ttu-id="333c2-107">Questa operazione accetta un valore di qualsiasi tipo e non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="333c2-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="333c2-108">Questo può essere utile quando è previsto un input di un tipo di operazione, ma non è necessario intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="333c2-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="333c2-109">Se, ad esempio, una particolare sindrome di correzione degli errori indica che non si è verificato alcun errore, `NoOp<Qubit[]>` può essere la procedura di recupero corretta.</span><span class="sxs-lookup"><span data-stu-id="333c2-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="333c2-110">Analogamente, se un'operazione prevede una procedura di preparazione dello stato come input, `NoOp<Qubit[]>` può essere usata per preparare lo stato $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="333c2-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="333c2-111">Input</span><span class="sxs-lookup"><span data-stu-id="333c2-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="333c2-112">input:' t</span><span class="sxs-lookup"><span data-stu-id="333c2-112">input : 'T</span></span>

<span data-ttu-id="333c2-113">Valore da ignorare.</span><span class="sxs-lookup"><span data-stu-id="333c2-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="333c2-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="333c2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="333c2-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="333c2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="333c2-116">T</span><span class="sxs-lookup"><span data-stu-id="333c2-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="333c2-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="333c2-117">Remarks</span></span>

<span data-ttu-id="333c2-118">In quasi tutti i casi, il parametro di tipo per `NoOp` deve essere specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="333c2-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="333c2-119">Ad esempio, `NoOp<Qubit>` è identico a <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="333c2-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="333c2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="333c2-120">See Also</span></span>

- [<span data-ttu-id="333c2-121">Microsoft. Quantum. Intrinsic. I</span><span class="sxs-lookup"><span data-stu-id="333c2-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)