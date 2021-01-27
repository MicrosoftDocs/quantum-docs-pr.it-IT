---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855460"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="8a923-102">FastHadamardTransformed (funzione)</span><span class="sxs-lookup"><span data-stu-id="8a923-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="8a923-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8a923-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8a923-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a923-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a923-105">Calcola la trasformazione Hadamard di una funzione booleana nella {-1,1} codifica usando il metodo di Yates</span><span class="sxs-lookup"><span data-stu-id="8a923-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="8a923-106">Input</span><span class="sxs-lookup"><span data-stu-id="8a923-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="8a923-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8a923-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8a923-108">Tabella di verità nella {-1,1} codifica</span><span class="sxs-lookup"><span data-stu-id="8a923-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="8a923-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8a923-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8a923-110">Coefficienti spettrali della funzione</span><span class="sxs-lookup"><span data-stu-id="8a923-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="8a923-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a923-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```