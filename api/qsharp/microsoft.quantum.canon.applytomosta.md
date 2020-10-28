---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operazione ApplyToMostA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717209"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="38dc5-102">Operazione ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="38dc5-102">ApplyToMostA operation</span></span>

<span data-ttu-id="38dc5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38dc5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38dc5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38dc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38dc5-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="38dc5-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="38dc5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38dc5-106">Description</span></span>

<span data-ttu-id="38dc5-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="38dc5-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="38dc5-108">Input</span><span class="sxs-lookup"><span data-stu-id="38dc5-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="38dc5-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="38dc5-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="38dc5-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="38dc5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="38dc5-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="38dc5-111">targets : 'T[]</span></span>

<span data-ttu-id="38dc5-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="38dc5-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38dc5-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38dc5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="38dc5-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="38dc5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38dc5-115">T</span><span class="sxs-lookup"><span data-stu-id="38dc5-115">'T</span></span>

<span data-ttu-id="38dc5-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="38dc5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="38dc5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38dc5-117">See Also</span></span>

- [<span data-ttu-id="38dc5-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="38dc5-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="38dc5-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="38dc5-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="38dc5-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="38dc5-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)