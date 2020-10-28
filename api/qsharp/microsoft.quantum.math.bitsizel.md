---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723191"
---
# <a name="bitsizel-function"></a><span data-ttu-id="24eda-102">BitSizeL (funzione)</span><span class="sxs-lookup"><span data-stu-id="24eda-102">BitSizeL function</span></span>

<span data-ttu-id="24eda-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="24eda-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="24eda-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24eda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24eda-105">Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .</span><span class="sxs-lookup"><span data-stu-id="24eda-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="24eda-106">Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="24eda-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="24eda-107">Input</span><span class="sxs-lookup"><span data-stu-id="24eda-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="24eda-108">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="24eda-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="24eda-109">Integer le cui dimensioni di bit devono essere calcolate.</span><span class="sxs-lookup"><span data-stu-id="24eda-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="24eda-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="24eda-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="24eda-111">Dimensioni di bit di `a` .</span><span class="sxs-lookup"><span data-stu-id="24eda-111">The bit-size of `a`.</span></span>