---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845263"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="ac4b8-102">RightShiftedI (funzione)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-102">RightShiftedI function</span></span>

<span data-ttu-id="ac4b8-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="ac4b8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac4b8-105">Sposta la rappresentazione bit per bit di un numero a destra di un numero specificato di bit.</span><span class="sxs-lookup"><span data-stu-id="ac4b8-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ac4b8-106">Input</span><span class="sxs-lookup"><span data-stu-id="ac4b8-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="ac4b8-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac4b8-108">Numero la cui rappresentazione bit per bit deve essere spostata a destra (meno significativa).</span><span class="sxs-lookup"><span data-stu-id="ac4b8-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="ac4b8-109">importo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac4b8-110">Numero di bit in base al quale deve `value` essere spostato a destra.</span><span class="sxs-lookup"><span data-stu-id="ac4b8-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="ac4b8-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac4b8-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac4b8-112">Valore di `value` , spostato a destra di `amount` bit.</span><span class="sxs-lookup"><span data-stu-id="ac4b8-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac4b8-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac4b8-113">Remarks</span></span>

<span data-ttu-id="ac4b8-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="ac4b8-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```