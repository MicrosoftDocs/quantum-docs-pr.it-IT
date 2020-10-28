---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operazione ApplyToTailCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716943"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="64ee7-102">Operazione ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="64ee7-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="64ee7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64ee7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64ee7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64ee7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64ee7-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="64ee7-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="64ee7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64ee7-106">Description</span></span>

<span data-ttu-id="64ee7-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="64ee7-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="64ee7-108">Input</span><span class="sxs-lookup"><span data-stu-id="64ee7-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="64ee7-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="64ee7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="64ee7-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="64ee7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="64ee7-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="64ee7-111">targets : 'T[]</span></span>

<span data-ttu-id="64ee7-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="64ee7-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64ee7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64ee7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="64ee7-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="64ee7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64ee7-115">T</span><span class="sxs-lookup"><span data-stu-id="64ee7-115">'T</span></span>

<span data-ttu-id="64ee7-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="64ee7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="64ee7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64ee7-117">See Also</span></span>

- [<span data-ttu-id="64ee7-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="64ee7-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="64ee7-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="64ee7-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="64ee7-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="64ee7-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)