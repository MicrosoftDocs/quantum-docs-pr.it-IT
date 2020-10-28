---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725025"
---
# <a name="squarednorm-function"></a><span data-ttu-id="37772-102">SquaredNorm (funzione)</span><span class="sxs-lookup"><span data-stu-id="37772-102">SquaredNorm function</span></span>

<span data-ttu-id="37772-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="37772-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="37772-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37772-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37772-105">Restituisce la norma 2 quadrata di un vettore.</span><span class="sxs-lookup"><span data-stu-id="37772-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="37772-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37772-106">Description</span></span>

<span data-ttu-id="37772-107">Restituisce la norma 2 quadrata di un vettore; ovvero, dato un input $ \vec{x} $, restituisce $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="37772-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="37772-108">Input</span><span class="sxs-lookup"><span data-stu-id="37772-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="37772-109">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="37772-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="37772-110">Vettore di cui deve essere restituita la norma quadrata 2.</span><span class="sxs-lookup"><span data-stu-id="37772-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="37772-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37772-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37772-112">La norma 2 quadrata di `array` .</span><span class="sxs-lookup"><span data-stu-id="37772-112">The squared 2-norm of `array`.</span></span>