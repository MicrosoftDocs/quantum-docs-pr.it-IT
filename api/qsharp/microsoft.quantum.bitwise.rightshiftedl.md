---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219516"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="73834-102">RightShiftedL (funzione)</span><span class="sxs-lookup"><span data-stu-id="73834-102">RightShiftedL function</span></span>

<span data-ttu-id="73834-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="73834-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="73834-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73834-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73834-105">Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="73834-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="73834-106">Input</span><span class="sxs-lookup"><span data-stu-id="73834-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="73834-107">valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="73834-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="73834-108">Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).</span><span class="sxs-lookup"><span data-stu-id="73834-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="73834-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73834-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73834-110">Numero di bit in base al quale deve `value` essere spostato a destra.</span><span class="sxs-lookup"><span data-stu-id="73834-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="73834-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="73834-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="73834-112">Valore di `value` , spostato a destra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="73834-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="73834-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="73834-113">Remarks</span></span>

<span data-ttu-id="73834-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="73834-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```