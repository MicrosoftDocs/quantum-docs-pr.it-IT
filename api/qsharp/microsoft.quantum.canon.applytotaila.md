---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operazione ApplyToTailA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841178"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="8ac85-102">Operazione ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="8ac85-102">ApplyToTailA operation</span></span>

<span data-ttu-id="8ac85-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ac85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ac85-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ac85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ac85-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="8ac85-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="8ac85-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ac85-106">Description</span></span>

<span data-ttu-id="8ac85-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8ac85-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8ac85-108">Input</span><span class="sxs-lookup"><span data-stu-id="8ac85-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="8ac85-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="8ac85-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8ac85-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8ac85-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8ac85-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="8ac85-111">targets : 'T[]</span></span>

<span data-ttu-id="8ac85-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="8ac85-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ac85-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ac85-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ac85-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8ac85-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ac85-115">T</span><span class="sxs-lookup"><span data-stu-id="8ac85-115">'T</span></span>

<span data-ttu-id="8ac85-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8ac85-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ac85-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ac85-117">See Also</span></span>

- [<span data-ttu-id="8ac85-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="8ac85-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="8ac85-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="8ac85-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="8ac85-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="8ac85-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)