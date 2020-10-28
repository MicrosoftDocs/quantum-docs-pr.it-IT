---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operazione ApplyToTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 72b55ec7161d5f6af5e4cb512c648078516c3b4e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716985"
---
# <a name="applytotail-operation"></a><span data-ttu-id="8cf9f-102">Operazione ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="8cf9f-102">ApplyToTail operation</span></span>

<span data-ttu-id="8cf9f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8cf9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8cf9f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8cf9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8cf9f-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8cf9f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cf9f-106">Description</span></span>

<span data-ttu-id="8cf9f-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8cf9f-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8cf9f-108">Input</span><span class="sxs-lookup"><span data-stu-id="8cf9f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="8cf9f-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8cf9f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8cf9f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8cf9f-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="8cf9f-111">targets : 'T[]</span></span>

<span data-ttu-id="8cf9f-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="8cf9f-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8cf9f-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8cf9f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8cf9f-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8cf9f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8cf9f-115">T</span><span class="sxs-lookup"><span data-stu-id="8cf9f-115">'T</span></span>

<span data-ttu-id="8cf9f-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf9f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cf9f-117">See Also</span></span>

- [<span data-ttu-id="8cf9f-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="8cf9f-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="8cf9f-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="8cf9f-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="8cf9f-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="8cf9f-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)