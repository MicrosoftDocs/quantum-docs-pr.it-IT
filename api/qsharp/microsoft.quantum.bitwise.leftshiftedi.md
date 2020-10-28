---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718662"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="b7b36-102">LeftShiftedI (funzione)</span><span class="sxs-lookup"><span data-stu-id="b7b36-102">LeftShiftedI function</span></span>

<span data-ttu-id="b7b36-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="b7b36-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="b7b36-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7b36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7b36-105">Sposta la rappresentazione bit per bit di un numero a sinistra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="b7b36-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b7b36-106">Input</span><span class="sxs-lookup"><span data-stu-id="b7b36-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="b7b36-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7b36-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7b36-108">Numero la cui rappresentazione bit per bit deve essere spostata a sinistra (più significativa).</span><span class="sxs-lookup"><span data-stu-id="b7b36-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="b7b36-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7b36-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7b36-110">Numero di bit in base al quale deve `value` essere spostato verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="b7b36-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="b7b36-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7b36-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7b36-112">Valore di `value` , spostato a sinistra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="b7b36-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7b36-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="b7b36-113">Remarks</span></span>

<span data-ttu-id="b7b36-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b7b36-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```