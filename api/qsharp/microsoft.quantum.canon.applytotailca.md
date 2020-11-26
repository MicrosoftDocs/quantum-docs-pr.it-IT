---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operazione ApplyToTailCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207854"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="7cd9a-102">Operazione ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="7cd9a-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="7cd9a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7cd9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7cd9a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7cd9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7cd9a-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="7cd9a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7cd9a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cd9a-106">Description</span></span>

<span data-ttu-id="7cd9a-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="7cd9a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="7cd9a-108">Input</span><span class="sxs-lookup"><span data-stu-id="7cd9a-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="7cd9a-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="7cd9a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7cd9a-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="7cd9a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7cd9a-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="7cd9a-111">targets : 'T[]</span></span>

<span data-ttu-id="7cd9a-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="7cd9a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7cd9a-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cd9a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7cd9a-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7cd9a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cd9a-115">T</span><span class="sxs-lookup"><span data-stu-id="7cd9a-115">'T</span></span>

<span data-ttu-id="7cd9a-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="7cd9a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cd9a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd9a-117">See Also</span></span>

- [<span data-ttu-id="7cd9a-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="7cd9a-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="7cd9a-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="7cd9a-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="7cd9a-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="7cd9a-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)