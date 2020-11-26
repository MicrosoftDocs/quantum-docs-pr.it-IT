---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Operazione EvaluateEvenPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: 21c700ccb2b87b906fc4d8b65eddf962353948c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223256"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="df5b7-102">Operazione EvaluateEvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="df5b7-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="df5b7-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="df5b7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="df5b7-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="df5b7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="df5b7-105">Valuta un polinomio uniforme in una rappresentazione a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="df5b7-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="df5b7-106">Input</span><span class="sxs-lookup"><span data-stu-id="df5b7-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="df5b7-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="df5b7-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="df5b7-108">Coefficienti del polinomio uniforme come una matrice doppia, ovvero la matrice $ [a_0, a_1,..., a_k] $ per la $P polinomiale (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2K} $.</span><span class="sxs-lookup"><span data-stu-id="df5b7-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="df5b7-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="df5b7-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="df5b7-110">Numero a virgola fissa di input per il quale valutare il polinomiale.</span><span class="sxs-lookup"><span data-stu-id="df5b7-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="df5b7-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="df5b7-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="df5b7-112">Numero a virgola fissa di output che conterrà $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="df5b7-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="df5b7-113">Deve trovarsi inizialmente in stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="df5b7-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df5b7-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df5b7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

