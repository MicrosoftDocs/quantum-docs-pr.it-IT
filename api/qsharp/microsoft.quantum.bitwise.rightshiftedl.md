---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718575"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="bd4e1-102">RightShiftedL (funzione)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-102">RightShiftedL function</span></span>

<span data-ttu-id="bd4e1-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bd4e1-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd4e1-105">Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="bd4e1-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="bd4e1-106">Input</span><span class="sxs-lookup"><span data-stu-id="bd4e1-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="bd4e1-107">valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bd4e1-108">Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).</span><span class="sxs-lookup"><span data-stu-id="bd4e1-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="bd4e1-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bd4e1-110">Numero di bit in base al quale deve `value` essere spostato a destra.</span><span class="sxs-lookup"><span data-stu-id="bd4e1-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="bd4e1-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bd4e1-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bd4e1-112">Valore di `value` , spostato a destra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="bd4e1-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd4e1-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="bd4e1-113">Remarks</span></span>

<span data-ttu-id="bd4e1-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="bd4e1-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```