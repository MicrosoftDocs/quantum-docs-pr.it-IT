---
uid: Microsoft.Quantum.Arrays.Merged
title: Funzione unita
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719010"
---
# <a name="merged-function"></a><span data-ttu-id="8a69b-102">Funzione unita</span><span class="sxs-lookup"><span data-stu-id="8a69b-102">Merged function</span></span>

<span data-ttu-id="8a69b-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8a69b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8a69b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a69b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a69b-105">Date due matrici ordinate, restituisce una singola matrice contenente gli elementi di entrambi gli elementi in ordine ordinato.</span><span class="sxs-lookup"><span data-stu-id="8a69b-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="8a69b-106">Utilizzato internamente dall'ordinamento di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="8a69b-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8a69b-107">Input</span><span class="sxs-lookup"><span data-stu-id="8a69b-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="8a69b-108">confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8a69b-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="8a69b-109">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="8a69b-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="8a69b-110">a destra:' t []</span><span class="sxs-lookup"><span data-stu-id="8a69b-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="8a69b-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="8a69b-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a69b-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8a69b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a69b-113">T</span><span class="sxs-lookup"><span data-stu-id="8a69b-113">'T</span></span>

