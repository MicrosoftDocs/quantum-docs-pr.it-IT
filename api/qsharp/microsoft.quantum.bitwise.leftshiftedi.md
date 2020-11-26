---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209860"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="56813-102">LeftShiftedI (funzione)</span><span class="sxs-lookup"><span data-stu-id="56813-102">LeftShiftedI function</span></span>

<span data-ttu-id="56813-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="56813-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="56813-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56813-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56813-105">Sposta la rappresentazione bit per bit di un numero a sinistra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="56813-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="56813-106">Input</span><span class="sxs-lookup"><span data-stu-id="56813-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="56813-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56813-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56813-108">Numero la cui rappresentazione bit per bit deve essere spostata a sinistra (più significativa).</span><span class="sxs-lookup"><span data-stu-id="56813-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="56813-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56813-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56813-110">Numero di bit in base al quale deve `value` essere spostato verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="56813-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="56813-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56813-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56813-112">Valore di `value` , spostato a sinistra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="56813-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="56813-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="56813-113">Remarks</span></span>

<span data-ttu-id="56813-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="56813-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```