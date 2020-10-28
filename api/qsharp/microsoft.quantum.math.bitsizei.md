---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723194"
---
# <a name="bitsizei-function"></a><span data-ttu-id="a5c32-102">BitSizeI (funzione)</span><span class="sxs-lookup"><span data-stu-id="a5c32-102">BitSizeI function</span></span>

<span data-ttu-id="a5c32-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a5c32-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a5c32-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5c32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5c32-105">Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .</span><span class="sxs-lookup"><span data-stu-id="a5c32-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="a5c32-106">Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="a5c32-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a5c32-107">Input</span><span class="sxs-lookup"><span data-stu-id="a5c32-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a5c32-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5c32-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5c32-109">Integer le cui dimensioni di bit devono essere calcolate.</span><span class="sxs-lookup"><span data-stu-id="a5c32-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="a5c32-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5c32-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5c32-111">Dimensioni di bit di `a` .</span><span class="sxs-lookup"><span data-stu-id="a5c32-111">The bit-size of `a`.</span></span>