---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operazione EvaluateOddPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721194"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="bd129-102">Operazione EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="bd129-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="bd129-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd129-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd129-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd129-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd129-105">Valuta un polinomio dispari in una rappresentazione a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="bd129-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="bd129-106">Input</span><span class="sxs-lookup"><span data-stu-id="bd129-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="bd129-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bd129-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bd129-108">Coefficienti del polinomio dispari come una doppia matrice, ovvero la matrice $ [a_0, a_1,..., a_k] $ per il $P polinomiale dispari (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="bd129-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="bd129-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bd129-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bd129-110">Numero a virgola fissa di input per il quale valutare il polinomiale.</span><span class="sxs-lookup"><span data-stu-id="bd129-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="bd129-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bd129-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bd129-112">Numero a virgola fissa di output che conterrà P (x).</span><span class="sxs-lookup"><span data-stu-id="bd129-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="bd129-113">Deve trovarsi inizialmente in stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="bd129-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd129-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd129-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

