---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operazione EvaluateOddPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223222"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="00bdc-102">Operazione EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="00bdc-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="00bdc-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="00bdc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="00bdc-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="00bdc-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="00bdc-105">Valuta un polinomio dispari in una rappresentazione a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="00bdc-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="00bdc-106">Input</span><span class="sxs-lookup"><span data-stu-id="00bdc-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="00bdc-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="00bdc-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="00bdc-108">Coefficienti del polinomio dispari come una doppia matrice, ovvero la matrice $ [a_0, a_1,..., a_k] $ per il $P polinomiale dispari (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="00bdc-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="00bdc-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="00bdc-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="00bdc-110">Numero a virgola fissa di input per il quale valutare il polinomiale.</span><span class="sxs-lookup"><span data-stu-id="00bdc-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="00bdc-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="00bdc-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="00bdc-112">Numero a virgola fissa di output che conterrà P (x).</span><span class="sxs-lookup"><span data-stu-id="00bdc-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="00bdc-113">Deve trovarsi inizialmente in stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="00bdc-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00bdc-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00bdc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

