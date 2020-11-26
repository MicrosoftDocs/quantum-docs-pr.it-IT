---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203094"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="5052b-102">FastHadamardTransformed (funzione)</span><span class="sxs-lookup"><span data-stu-id="5052b-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="5052b-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5052b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5052b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5052b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5052b-105">Calcola la trasformazione Hadamard di una funzione booleana nella {-1,1} codifica usando il metodo di Yates</span><span class="sxs-lookup"><span data-stu-id="5052b-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="5052b-106">Input</span><span class="sxs-lookup"><span data-stu-id="5052b-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="5052b-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5052b-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5052b-108">Tabella di verità nella {-1,1} codifica</span><span class="sxs-lookup"><span data-stu-id="5052b-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="5052b-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5052b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5052b-110">Coefficienti spettrali della funzione</span><span class="sxs-lookup"><span data-stu-id="5052b-110">Spectral coefficients of the function</span></span>