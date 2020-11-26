---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227302"
---
# <a name="squarednorm-function"></a><span data-ttu-id="9b8ad-102">SquaredNorm (funzione)</span><span class="sxs-lookup"><span data-stu-id="9b8ad-102">SquaredNorm function</span></span>

<span data-ttu-id="9b8ad-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9b8ad-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9b8ad-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b8ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b8ad-105">Restituisce la norma 2 quadrata di un vettore.</span><span class="sxs-lookup"><span data-stu-id="9b8ad-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="9b8ad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b8ad-106">Description</span></span>

<span data-ttu-id="9b8ad-107">Restituisce la norma 2 quadrata di un vettore; ovvero, dato un input $ \vec{x} $, restituisce $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="9b8ad-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="9b8ad-108">Input</span><span class="sxs-lookup"><span data-stu-id="9b8ad-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="9b8ad-109">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9b8ad-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9b8ad-110">Vettore di cui deve essere restituita la norma quadrata 2.</span><span class="sxs-lookup"><span data-stu-id="9b8ad-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="9b8ad-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b8ad-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b8ad-112">La norma 2 quadrata di `array` .</span><span class="sxs-lookup"><span data-stu-id="9b8ad-112">The squared 2-norm of `array`.</span></span>