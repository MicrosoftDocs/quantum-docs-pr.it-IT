---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: Operazione SquareFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842908"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="2a7fb-102">Operazione SquareFxP</span><span class="sxs-lookup"><span data-stu-id="2a7fb-102">SquareFxP operation</span></span>

<span data-ttu-id="2a7fb-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2a7fb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2a7fb-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2a7fb-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2a7fb-105">Piazza un numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="2a7fb-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2a7fb-106">Input</span><span class="sxs-lookup"><span data-stu-id="2a7fb-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="2a7fb-107">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2a7fb-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2a7fb-108">Numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="2a7fb-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="2a7fb-109">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2a7fb-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2a7fb-110">Il numero a virgola fissa risultato deve trovarsi nello stato $ \ket {0} $ inizialmente.</span><span class="sxs-lookup"><span data-stu-id="2a7fb-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a7fb-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a7fb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

