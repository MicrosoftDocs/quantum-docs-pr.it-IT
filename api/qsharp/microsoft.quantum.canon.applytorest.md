---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operazione ApplyToRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850502"
---
# <a name="applytorest-operation"></a><span data-ttu-id="a8c27-102">Operazione ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="a8c27-102">ApplyToRest operation</span></span>

<span data-ttu-id="a8c27-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8c27-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8c27-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8c27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8c27-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a8c27-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a8c27-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8c27-106">Description</span></span>

<span data-ttu-id="a8c27-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a8c27-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a8c27-108">Input</span><span class="sxs-lookup"><span data-stu-id="a8c27-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="a8c27-109">op:' t [] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a8c27-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8c27-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a8c27-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a8c27-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="a8c27-111">targets : 'T[]</span></span>

<span data-ttu-id="a8c27-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="a8c27-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8c27-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8c27-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8c27-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a8c27-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8c27-115">T</span><span class="sxs-lookup"><span data-stu-id="a8c27-115">'T</span></span>

<span data-ttu-id="a8c27-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a8c27-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="a8c27-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8c27-117">Example</span></span>

<span data-ttu-id="a8c27-118">I frammenti di codice Q # seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="a8c27-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="a8c27-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8c27-119">See Also</span></span>

- [<span data-ttu-id="a8c27-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="a8c27-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="a8c27-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="a8c27-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="a8c27-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="a8c27-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)