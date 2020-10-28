---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operazione ApplyToRestA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717083"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="fdeb2-102">Operazione ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="fdeb2-102">ApplyToRestA operation</span></span>

<span data-ttu-id="fdeb2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fdeb2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fdeb2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdeb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdeb2-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="fdeb2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdeb2-106">Description</span></span>

<span data-ttu-id="fdeb2-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="fdeb2-108">Input</span><span class="sxs-lookup"><span data-stu-id="fdeb2-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="fdeb2-109">op:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="fdeb2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fdeb2-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fdeb2-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="fdeb2-111">targets : 'T[]</span></span>

<span data-ttu-id="fdeb2-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fdeb2-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdeb2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fdeb2-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="fdeb2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fdeb2-115">T</span><span class="sxs-lookup"><span data-stu-id="fdeb2-115">'T</span></span>

<span data-ttu-id="fdeb2-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdeb2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdeb2-117">See Also</span></span>

- [<span data-ttu-id="fdeb2-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="fdeb2-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="fdeb2-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="fdeb2-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="fdeb2-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="fdeb2-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)