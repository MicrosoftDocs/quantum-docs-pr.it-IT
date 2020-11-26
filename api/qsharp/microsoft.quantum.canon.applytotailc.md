---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Operazione ApplyToTailC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217289"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="d526b-102">Operazione ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="d526b-102">ApplyToTailC operation</span></span>

<span data-ttu-id="d526b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d526b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d526b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d526b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d526b-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d526b-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="d526b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d526b-106">Description</span></span>

<span data-ttu-id="d526b-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d526b-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d526b-108">Input</span><span class="sxs-lookup"><span data-stu-id="d526b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d526b-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="d526b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d526b-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d526b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d526b-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="d526b-111">targets : 'T[]</span></span>

<span data-ttu-id="d526b-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="d526b-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d526b-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d526b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d526b-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d526b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d526b-115">T</span><span class="sxs-lookup"><span data-stu-id="d526b-115">'T</span></span>

<span data-ttu-id="d526b-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d526b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d526b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d526b-117">See Also</span></span>

- [<span data-ttu-id="d526b-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="d526b-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="d526b-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="d526b-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="d526b-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="d526b-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)