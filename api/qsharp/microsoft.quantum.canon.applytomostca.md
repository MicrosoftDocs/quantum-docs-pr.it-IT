---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operazione ApplyToMostCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841320"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="621fb-102">Operazione ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="621fb-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="621fb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="621fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="621fb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="621fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="621fb-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="621fb-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="621fb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="621fb-106">Description</span></span>

<span data-ttu-id="621fb-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="621fb-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="621fb-108">Input</span><span class="sxs-lookup"><span data-stu-id="621fb-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="621fb-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="621fb-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="621fb-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="621fb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="621fb-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="621fb-111">targets : 'T[]</span></span>

<span data-ttu-id="621fb-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="621fb-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="621fb-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="621fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="621fb-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="621fb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="621fb-115">T</span><span class="sxs-lookup"><span data-stu-id="621fb-115">'T</span></span>

<span data-ttu-id="621fb-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="621fb-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="621fb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="621fb-117">See Also</span></span>

- [<span data-ttu-id="621fb-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="621fb-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="621fb-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="621fb-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="621fb-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="621fb-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)