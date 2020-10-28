---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operazione ApplyToMostC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717170"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="d5e13-102">Operazione ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d5e13-102">ApplyToMostC operation</span></span>

<span data-ttu-id="d5e13-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5e13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5e13-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5e13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5e13-105">Applica un'operazione a tutti gli elementi tranne l'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d5e13-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d5e13-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5e13-106">Description</span></span>

<span data-ttu-id="d5e13-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d5e13-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d5e13-108">Input</span><span class="sxs-lookup"><span data-stu-id="d5e13-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="d5e13-109">op:' t [] => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5e13-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d5e13-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d5e13-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d5e13-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="d5e13-111">targets : 'T[]</span></span>

<span data-ttu-id="d5e13-112">Matrice di destinazioni, di cui verranno applicati tutti gli ultimi, tranne l'ultimo `op` .</span><span class="sxs-lookup"><span data-stu-id="d5e13-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5e13-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5e13-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d5e13-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d5e13-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5e13-115">T</span><span class="sxs-lookup"><span data-stu-id="d5e13-115">'T</span></span>

<span data-ttu-id="d5e13-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d5e13-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5e13-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5e13-117">See Also</span></span>

- [<span data-ttu-id="d5e13-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="d5e13-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="d5e13-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="d5e13-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="d5e13-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="d5e13-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)