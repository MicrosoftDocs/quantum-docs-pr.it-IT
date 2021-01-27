---
uid: Microsoft.Quantum.Arrays.Merged
title: Funzione unita
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845618"
---
# <a name="merged-function"></a><span data-ttu-id="e26e4-102">Funzione unita</span><span class="sxs-lookup"><span data-stu-id="e26e4-102">Merged function</span></span>

<span data-ttu-id="e26e4-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e26e4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e26e4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e26e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e26e4-105">Date due matrici ordinate, restituisce una singola matrice contenente gli elementi di entrambi gli elementi in ordine ordinato.</span><span class="sxs-lookup"><span data-stu-id="e26e4-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="e26e4-106">Utilizzato internamente dall'ordinamento di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="e26e4-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e26e4-107">Input</span><span class="sxs-lookup"><span data-stu-id="e26e4-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="e26e4-108">confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e26e4-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="e26e4-109">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="e26e4-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="e26e4-110">a destra:' t []</span><span class="sxs-lookup"><span data-stu-id="e26e4-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="e26e4-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="e26e4-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e26e4-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e26e4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e26e4-113">T</span><span class="sxs-lookup"><span data-stu-id="e26e4-113">'T</span></span>

