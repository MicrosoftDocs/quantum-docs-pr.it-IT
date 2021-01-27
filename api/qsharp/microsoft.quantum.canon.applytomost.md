---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operazione ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850598"
---
# <a name="applytomost-operation"></a><span data-ttu-id="0f31e-102">Operazione ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="0f31e-102">ApplyToMost operation</span></span>

<span data-ttu-id="0f31e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f31e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f31e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f31e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f31e-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="0f31e-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0f31e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f31e-106">Description</span></span>

<span data-ttu-id="0f31e-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0f31e-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0f31e-108">Input</span><span class="sxs-lookup"><span data-stu-id="0f31e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="0f31e-109">op:' t [] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0f31e-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f31e-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="0f31e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0f31e-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="0f31e-111">targets : 'T[]</span></span>

<span data-ttu-id="0f31e-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="0f31e-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f31e-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f31e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f31e-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0f31e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f31e-115">T</span><span class="sxs-lookup"><span data-stu-id="0f31e-115">'T</span></span>

<span data-ttu-id="0f31e-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="0f31e-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="0f31e-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f31e-117">Example</span></span>

<span data-ttu-id="0f31e-118">I frammenti di codice Q # seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="0f31e-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="0f31e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f31e-119">See Also</span></span>

- [<span data-ttu-id="0f31e-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="0f31e-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="0f31e-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="0f31e-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="0f31e-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="0f31e-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)