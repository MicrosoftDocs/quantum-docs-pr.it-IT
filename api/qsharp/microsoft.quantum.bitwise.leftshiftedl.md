---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718635"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="affd7-102">LeftShiftedL (funzione)</span><span class="sxs-lookup"><span data-stu-id="affd7-102">LeftShiftedL function</span></span>

<span data-ttu-id="affd7-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="affd7-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="affd7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="affd7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="affd7-105">Sposta la rappresentazione bit per bit di un numero a sinistra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="affd7-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="affd7-106">Input</span><span class="sxs-lookup"><span data-stu-id="affd7-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="affd7-107">valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="affd7-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="affd7-108">Numero la cui rappresentazione bit per bit deve essere spostata a sinistra (più significativa).</span><span class="sxs-lookup"><span data-stu-id="affd7-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="affd7-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="affd7-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="affd7-110">Numero di bit in base al quale deve `value` essere spostato verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="affd7-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="affd7-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="affd7-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="affd7-112">Valore di `value` , spostato a sinistra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="affd7-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="affd7-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="affd7-113">Remarks</span></span>

<span data-ttu-id="affd7-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="affd7-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```