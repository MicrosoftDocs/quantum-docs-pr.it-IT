---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operazione EvaluatePolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 4f6ed4b34af2e63dd8ee31fb9b93119e06e3ecbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223188"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="dd735-102">Operazione EvaluatePolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="dd735-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="dd735-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dd735-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dd735-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="dd735-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="dd735-105">Valuta un polinomiale in una rappresentazione a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="dd735-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd735-106">Input</span><span class="sxs-lookup"><span data-stu-id="dd735-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="dd735-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd735-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd735-108">Coefficienti del polinomi come una doppia matrice, ad esempio, la matrice $ [a_0, a_1,..., a_d] $ per la $P polinomiale (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="dd735-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="dd735-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="dd735-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="dd735-110">Numero a virgola fissa di input per il quale valutare il polinomiale.</span><span class="sxs-lookup"><span data-stu-id="dd735-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="dd735-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="dd735-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="dd735-112">Numero a virgola fissa di output che conterrà $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="dd735-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="dd735-113">Deve trovarsi inizialmente in stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="dd735-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd735-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd735-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

