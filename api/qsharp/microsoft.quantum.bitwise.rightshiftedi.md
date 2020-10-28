---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718578"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="f656a-102">RightShiftedI (funzione)</span><span class="sxs-lookup"><span data-stu-id="f656a-102">RightShiftedI function</span></span>

<span data-ttu-id="f656a-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f656a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f656a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f656a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f656a-105">Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="f656a-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f656a-106">Input</span><span class="sxs-lookup"><span data-stu-id="f656a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f656a-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f656a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f656a-108">Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).</span><span class="sxs-lookup"><span data-stu-id="f656a-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="f656a-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f656a-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f656a-110">Numero di bit in base al quale deve `value` essere spostato a destra.</span><span class="sxs-lookup"><span data-stu-id="f656a-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="f656a-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f656a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f656a-112">Valore di `value` , spostato a destra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="f656a-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="f656a-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f656a-113">Remarks</span></span>

<span data-ttu-id="f656a-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="f656a-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```