---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operazione ApplyToMostA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850579"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="d1525-102">Operazione ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="d1525-102">ApplyToMostA operation</span></span>

<span data-ttu-id="d1525-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1525-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1525-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1525-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1525-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d1525-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="d1525-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1525-106">Description</span></span>

<span data-ttu-id="d1525-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d1525-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d1525-108">Input</span><span class="sxs-lookup"><span data-stu-id="d1525-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d1525-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="d1525-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d1525-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d1525-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d1525-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="d1525-111">targets : 'T[]</span></span>

<span data-ttu-id="d1525-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="d1525-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1525-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1525-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1525-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d1525-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1525-115">T</span><span class="sxs-lookup"><span data-stu-id="d1525-115">'T</span></span>

<span data-ttu-id="d1525-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d1525-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1525-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1525-117">See Also</span></span>

- [<span data-ttu-id="d1525-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="d1525-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="d1525-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d1525-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="d1525-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="d1525-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)