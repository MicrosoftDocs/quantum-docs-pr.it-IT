---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operazione ApplyToRestA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208305"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="00338-102">Operazione ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="00338-102">ApplyToRestA operation</span></span>

<span data-ttu-id="00338-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00338-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00338-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00338-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00338-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="00338-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="00338-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00338-106">Description</span></span>

<span data-ttu-id="00338-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="00338-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="00338-108">Input</span><span class="sxs-lookup"><span data-stu-id="00338-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="00338-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="00338-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="00338-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="00338-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="00338-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="00338-111">targets : 'T[]</span></span>

<span data-ttu-id="00338-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="00338-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00338-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00338-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="00338-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="00338-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00338-115">T</span><span class="sxs-lookup"><span data-stu-id="00338-115">'T</span></span>

<span data-ttu-id="00338-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="00338-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="00338-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00338-117">See Also</span></span>

- [<span data-ttu-id="00338-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="00338-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="00338-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="00338-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="00338-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="00338-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)