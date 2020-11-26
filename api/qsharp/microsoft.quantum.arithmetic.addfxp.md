---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operazione AddFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191041"
---
# <a name="addfxp-operation"></a><span data-ttu-id="68db4-102">Operazione AddFxP</span><span class="sxs-lookup"><span data-stu-id="68db4-102">AddFxP operation</span></span>

<span data-ttu-id="68db4-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="68db4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="68db4-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="68db4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="68db4-105">Aggiunge due numeri a virgola fissa archiviati nei registri Quantum.</span><span class="sxs-lookup"><span data-stu-id="68db4-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="68db4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68db4-106">Description</span></span>

<span data-ttu-id="68db4-107">Dato due registri a virgola fissa rispettivamente negli Stati $ \ket{f_1} $ e $ \ket{f_2} $, esegue l'operazione $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="68db4-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="68db4-108">Input</span><span class="sxs-lookup"><span data-stu-id="68db4-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="68db4-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="68db4-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="68db4-110">Primo numero a virgola fissa</span><span class="sxs-lookup"><span data-stu-id="68db4-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="68db4-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="68db4-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="68db4-112">Il secondo numero a virgola fissa verrà aggiornato in modo da contenere la somma dei due input.</span><span class="sxs-lookup"><span data-stu-id="68db4-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="68db4-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68db4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="68db4-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="68db4-114">Remarks</span></span>

<span data-ttu-id="68db4-115">Per l'implementazione corrente è necessario che i due numeri a virgola fissa dispongano della stessa posizione del punto dal bit meno significativo, ad esempio $n _i $ e $p _i $ debbano essere uguali.</span><span class="sxs-lookup"><span data-stu-id="68db4-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>