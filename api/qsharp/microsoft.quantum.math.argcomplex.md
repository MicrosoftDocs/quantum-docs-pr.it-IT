---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211101"
---
# <a name="argcomplex-function"></a><span data-ttu-id="c10c9-102">ArgComplex (funzione)</span><span class="sxs-lookup"><span data-stu-id="c10c9-102">ArgComplex function</span></span>

<span data-ttu-id="c10c9-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c10c9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c10c9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c10c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c10c9-105">Restituisce la fase di un numero complesso di tipo `Complex` .</span><span class="sxs-lookup"><span data-stu-id="c10c9-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="c10c9-106">Input</span><span class="sxs-lookup"><span data-stu-id="c10c9-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="c10c9-107">input: [complesso](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c10c9-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c10c9-108">Numero complesso $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="c10c9-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="c10c9-109">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c10c9-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c10c9-110">Fase $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\Pi, \Pi] $.</span><span class="sxs-lookup"><span data-stu-id="c10c9-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>