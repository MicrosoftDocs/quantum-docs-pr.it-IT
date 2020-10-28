---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719847"
---
# <a name="integerbits-function"></a><span data-ttu-id="1d9f9-102">IntegerBits (funzione)</span><span class="sxs-lookup"><span data-stu-id="1d9f9-102">IntegerBits function</span></span>

<span data-ttu-id="1d9f9-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1d9f9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1d9f9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d9f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d9f9-105">Restituisce tutte le posizioni in cui vengono impostati i bit di un Integer.</span><span class="sxs-lookup"><span data-stu-id="1d9f9-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="1d9f9-106">Input</span><span class="sxs-lookup"><span data-stu-id="1d9f9-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="1d9f9-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d9f9-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d9f9-108">Numero non negativo.</span><span class="sxs-lookup"><span data-stu-id="1d9f9-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="1d9f9-109">Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d9f9-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d9f9-110">Numero di bit nell'espansione binaria di `value` .</span><span class="sxs-lookup"><span data-stu-id="1d9f9-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="1d9f9-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1d9f9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1d9f9-112">Matrice che contiene tutte le posizioni di bit (a partire da 0) che sono 1 nell'espansione binaria, `value` considerando tutti i bit fino alla posizione `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="1d9f9-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="1d9f9-113">Tutte le posizioni vengono ordinate nella matrice in base alla posizione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="1d9f9-113">All positions are ordered in the array by position in an increasing order.</span></span>