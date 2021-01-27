---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operazione ApplyToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841191"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="683c8-102">Operazione ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="683c8-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="683c8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="683c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="683c8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="683c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="683c8-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="683c8-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="683c8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="683c8-106">Description</span></span>

<span data-ttu-id="683c8-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="683c8-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="683c8-108">Input</span><span class="sxs-lookup"><span data-stu-id="683c8-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="683c8-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="683c8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="683c8-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="683c8-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="683c8-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="683c8-111">targets : 'T[]</span></span>

<span data-ttu-id="683c8-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="683c8-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="683c8-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="683c8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="683c8-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="683c8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="683c8-115">T</span><span class="sxs-lookup"><span data-stu-id="683c8-115">'T</span></span>

<span data-ttu-id="683c8-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="683c8-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="683c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="683c8-117">See Also</span></span>

- [<span data-ttu-id="683c8-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="683c8-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="683c8-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="683c8-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="683c8-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="683c8-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)