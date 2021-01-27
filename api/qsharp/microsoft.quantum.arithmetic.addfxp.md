---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operazione AddFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843864"
---
# <a name="addfxp-operation"></a><span data-ttu-id="5446e-102">Operazione AddFxP</span><span class="sxs-lookup"><span data-stu-id="5446e-102">AddFxP operation</span></span>

<span data-ttu-id="5446e-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5446e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5446e-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5446e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5446e-105">Aggiunge due numeri a virgola fissa archiviati nei registri Quantum.</span><span class="sxs-lookup"><span data-stu-id="5446e-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5446e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5446e-106">Description</span></span>

<span data-ttu-id="5446e-107">Dato due registri a virgola fissa rispettivamente negli Stati $ \ket{f_1} $ e $ \ket{f_2} $, esegue l'operazione $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="5446e-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="5446e-108">Input</span><span class="sxs-lookup"><span data-stu-id="5446e-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="5446e-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5446e-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5446e-110">Primo numero a virgola fissa</span><span class="sxs-lookup"><span data-stu-id="5446e-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="5446e-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5446e-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5446e-112">Il secondo numero a virgola fissa verrà aggiornato in modo da contenere la somma dei due input.</span><span class="sxs-lookup"><span data-stu-id="5446e-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5446e-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5446e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5446e-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="5446e-114">Remarks</span></span>

<span data-ttu-id="5446e-115">Per l'implementazione corrente è necessario che i due numeri a virgola fissa dispongano della stessa posizione del punto dal bit meno significativo, ad esempio $n _i $ e $p _i $ debbano essere uguali.</span><span class="sxs-lookup"><span data-stu-id="5446e-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>