---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857706"
---
# <a name="bitsizei-function"></a><span data-ttu-id="98c69-102">BitSizeI (funzione)</span><span class="sxs-lookup"><span data-stu-id="98c69-102">BitSizeI function</span></span>

<span data-ttu-id="98c69-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="98c69-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="98c69-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98c69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98c69-105">Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .</span><span class="sxs-lookup"><span data-stu-id="98c69-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="98c69-106">Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="98c69-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="98c69-107">Input</span><span class="sxs-lookup"><span data-stu-id="98c69-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="98c69-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c69-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c69-109">Integer le cui dimensioni di bit devono essere calcolate.</span><span class="sxs-lookup"><span data-stu-id="98c69-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="98c69-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c69-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c69-111">Dimensioni di bit di `a` .</span><span class="sxs-lookup"><span data-stu-id="98c69-111">The bit-size of `a`.</span></span>