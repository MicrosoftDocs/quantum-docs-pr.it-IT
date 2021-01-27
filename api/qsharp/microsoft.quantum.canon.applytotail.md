---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operazione ApplyToTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850446"
---
# <a name="applytotail-operation"></a><span data-ttu-id="eb0f0-102">Operazione ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="eb0f0-102">ApplyToTail operation</span></span>

<span data-ttu-id="eb0f0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb0f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb0f0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb0f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb0f0-105">Applica un'operazione all'ultimo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="eb0f0-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="eb0f0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb0f0-106">Description</span></span>

<span data-ttu-id="eb0f0-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="eb0f0-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="eb0f0-108">Input</span><span class="sxs-lookup"><span data-stu-id="eb0f0-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="eb0f0-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="eb0f0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb0f0-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="eb0f0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="eb0f0-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="eb0f0-111">targets : 'T[]</span></span>

<span data-ttu-id="eb0f0-112">Matrice di destinazioni a cui verrà applicato l'ultimo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="eb0f0-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb0f0-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb0f0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb0f0-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="eb0f0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb0f0-115">T</span><span class="sxs-lookup"><span data-stu-id="eb0f0-115">'T</span></span>

<span data-ttu-id="eb0f0-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="eb0f0-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="eb0f0-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb0f0-117">Example</span></span>

<span data-ttu-id="eb0f0-118">I frammenti di codice Q # seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="eb0f0-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="eb0f0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb0f0-119">See Also</span></span>

- [<span data-ttu-id="eb0f0-120">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="eb0f0-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="eb0f0-121">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="eb0f0-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="eb0f0-122">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="eb0f0-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)