---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195852"
---
# <a name="bitsizei-function"></a><span data-ttu-id="c5ce9-102">BitSizeI (funzione)</span><span class="sxs-lookup"><span data-stu-id="c5ce9-102">BitSizeI function</span></span>

<span data-ttu-id="c5ce9-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c5ce9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c5ce9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5ce9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5ce9-105">Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .</span><span class="sxs-lookup"><span data-stu-id="c5ce9-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="c5ce9-106">Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c5ce9-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="c5ce9-107">Input</span><span class="sxs-lookup"><span data-stu-id="c5ce9-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c5ce9-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5ce9-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5ce9-109">Integer le cui dimensioni di bit devono essere calcolate.</span><span class="sxs-lookup"><span data-stu-id="c5ce9-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5ce9-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5ce9-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5ce9-111">Dimensioni di bit di `a` .</span><span class="sxs-lookup"><span data-stu-id="c5ce9-111">The bit-size of `a`.</span></span>