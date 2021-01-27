---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operazione ApplyToRestC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850485"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="8a5e9-102">Operazione ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="8a5e9-102">ApplyToRestC operation</span></span>

<span data-ttu-id="8a5e9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a5e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a5e9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a5e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a5e9-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="8a5e9-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8a5e9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a5e9-106">Description</span></span>

<span data-ttu-id="8a5e9-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8a5e9-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8a5e9-108">Input</span><span class="sxs-lookup"><span data-stu-id="8a5e9-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8a5e9-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="8a5e9-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8a5e9-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8a5e9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8a5e9-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="8a5e9-111">targets : 'T[]</span></span>

<span data-ttu-id="8a5e9-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="8a5e9-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a5e9-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a5e9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a5e9-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8a5e9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a5e9-115">T</span><span class="sxs-lookup"><span data-stu-id="8a5e9-115">'T</span></span>

<span data-ttu-id="8a5e9-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8a5e9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a5e9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a5e9-117">See Also</span></span>

- [<span data-ttu-id="8a5e9-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="8a5e9-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="8a5e9-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="8a5e9-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="8a5e9-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="8a5e9-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)