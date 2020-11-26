---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operazione ApplyToMostC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208466"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="0b38a-102">Operazione ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="0b38a-102">ApplyToMostC operation</span></span>

<span data-ttu-id="0b38a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b38a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b38a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b38a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b38a-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="0b38a-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="0b38a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b38a-106">Description</span></span>

<span data-ttu-id="0b38a-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0b38a-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0b38a-108">Input</span><span class="sxs-lookup"><span data-stu-id="0b38a-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="0b38a-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="0b38a-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0b38a-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="0b38a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0b38a-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="0b38a-111">targets : 'T[]</span></span>

<span data-ttu-id="0b38a-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="0b38a-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b38a-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b38a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0b38a-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0b38a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b38a-115">T</span><span class="sxs-lookup"><span data-stu-id="0b38a-115">'T</span></span>

<span data-ttu-id="0b38a-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="0b38a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b38a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b38a-117">See Also</span></span>

- [<span data-ttu-id="0b38a-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="0b38a-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="0b38a-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="0b38a-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="0b38a-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="0b38a-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)