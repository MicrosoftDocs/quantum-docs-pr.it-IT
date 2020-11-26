---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operazione ApplyToMostA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208500"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="dffc7-102">Operazione ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="dffc7-102">ApplyToMostA operation</span></span>

<span data-ttu-id="dffc7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dffc7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dffc7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dffc7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dffc7-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="dffc7-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="dffc7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dffc7-106">Description</span></span>

<span data-ttu-id="dffc7-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="dffc7-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="dffc7-108">Input</span><span class="sxs-lookup"><span data-stu-id="dffc7-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="dffc7-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="dffc7-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dffc7-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="dffc7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="dffc7-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="dffc7-111">targets : 'T[]</span></span>

<span data-ttu-id="dffc7-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="dffc7-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dffc7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dffc7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dffc7-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="dffc7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dffc7-115">T</span><span class="sxs-lookup"><span data-stu-id="dffc7-115">'T</span></span>

<span data-ttu-id="dffc7-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="dffc7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dffc7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffc7-117">See Also</span></span>

- [<span data-ttu-id="dffc7-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="dffc7-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="dffc7-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="dffc7-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="dffc7-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="dffc7-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)