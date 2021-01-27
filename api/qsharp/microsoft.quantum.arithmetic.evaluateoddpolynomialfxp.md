---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operazione EvaluateOddPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846670"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="767e4-102">Operazione EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="767e4-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="767e4-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="767e4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="767e4-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="767e4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="767e4-105">Valuta un polinomio dispari in una rappresentazione a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="767e4-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="767e4-106">Input</span><span class="sxs-lookup"><span data-stu-id="767e4-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="767e4-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="767e4-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="767e4-108">Coefficienti del polinomio dispari come una doppia matrice, ovvero la matrice $ [a_0, a_1,..., a_k] $ per il $P polinomiale dispari (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="767e4-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="767e4-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="767e4-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="767e4-110">Numero a virgola fissa di input per il quale valutare il polinomiale.</span><span class="sxs-lookup"><span data-stu-id="767e4-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="767e4-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="767e4-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="767e4-112">Numero a virgola fissa di output che conterrà P (x).</span><span class="sxs-lookup"><span data-stu-id="767e4-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="767e4-113">Deve trovarsi inizialmente in stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="767e4-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="767e4-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="767e4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

