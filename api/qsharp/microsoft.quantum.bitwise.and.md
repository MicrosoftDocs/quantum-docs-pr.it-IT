---
uid: Microsoft.Quantum.Bitwise.And
title: And (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842157"
---
# <a name="and-function"></a><span data-ttu-id="d7896-102">And (funzione)</span><span class="sxs-lookup"><span data-stu-id="d7896-102">And function</span></span>

<span data-ttu-id="d7896-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d7896-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d7896-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d7896-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d7896-105">Restituisce l'operatore AND bit per bit di due Integer.</span><span class="sxs-lookup"><span data-stu-id="d7896-105">Returns the bitwise AND of two integers.</span></span>
<span data-ttu-id="d7896-106">Esegue lo stesso calcolo dell' `&&&` operatore incorporato.</span><span class="sxs-lookup"><span data-stu-id="d7896-106">This performs the same computation as the built-in `&&&` operator.</span></span>

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d7896-107">Input</span><span class="sxs-lookup"><span data-stu-id="d7896-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d7896-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7896-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="d7896-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7896-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="d7896-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7896-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="d7896-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7896-111">Example</span></span>

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a><span data-ttu-id="d7896-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="d7896-112">Remarks</span></span>

<span data-ttu-id="d7896-113">Per ulteriori informazioni, vedere l' [ &amp; operatore C#](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binario).</span><span class="sxs-lookup"><span data-stu-id="d7896-113">See the [C# &amp; Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binary) for more details.</span></span>