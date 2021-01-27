---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operazione ApplyToRestA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841256"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="87c93-102">Operazione ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="87c93-102">ApplyToRestA operation</span></span>

<span data-ttu-id="87c93-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87c93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87c93-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87c93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87c93-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="87c93-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="87c93-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87c93-106">Description</span></span>

<span data-ttu-id="87c93-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="87c93-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="87c93-108">Input</span><span class="sxs-lookup"><span data-stu-id="87c93-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="87c93-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="87c93-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="87c93-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="87c93-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="87c93-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="87c93-111">targets : 'T[]</span></span>

<span data-ttu-id="87c93-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="87c93-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87c93-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87c93-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87c93-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="87c93-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87c93-115">T</span><span class="sxs-lookup"><span data-stu-id="87c93-115">'T</span></span>

<span data-ttu-id="87c93-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="87c93-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="87c93-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87c93-117">See Also</span></span>

- [<span data-ttu-id="87c93-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="87c93-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="87c93-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="87c93-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="87c93-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="87c93-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)