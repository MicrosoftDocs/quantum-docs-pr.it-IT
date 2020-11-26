---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operazione ApplyToTailA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207922"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="61811-102">Operazione ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="61811-102">ApplyToTailA operation</span></span>

<span data-ttu-id="61811-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61811-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61811-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61811-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61811-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="61811-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="61811-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61811-106">Description</span></span>

<span data-ttu-id="61811-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="61811-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="61811-108">Input</span><span class="sxs-lookup"><span data-stu-id="61811-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="61811-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="61811-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="61811-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="61811-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="61811-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="61811-111">targets : 'T[]</span></span>

<span data-ttu-id="61811-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="61811-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61811-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61811-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61811-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="61811-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61811-115">T</span><span class="sxs-lookup"><span data-stu-id="61811-115">'T</span></span>

<span data-ttu-id="61811-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="61811-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="61811-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61811-117">See Also</span></span>

- [<span data-ttu-id="61811-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="61811-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="61811-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="61811-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="61811-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="61811-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)