---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848207"
---
# <a name="squarednorm-function"></a><span data-ttu-id="1b995-102">SquaredNorm (funzione)</span><span class="sxs-lookup"><span data-stu-id="1b995-102">SquaredNorm function</span></span>

<span data-ttu-id="1b995-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1b995-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1b995-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b995-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b995-105">Restituisce la norma 2 quadrata di un vettore.</span><span class="sxs-lookup"><span data-stu-id="1b995-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="1b995-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b995-106">Description</span></span>

<span data-ttu-id="1b995-107">Restituisce la norma 2 quadrata di un vettore; ovvero, dato un input $ \vec{x} $, restituisce $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="1b995-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="1b995-108">Input</span><span class="sxs-lookup"><span data-stu-id="1b995-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="1b995-109">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1b995-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1b995-110">Vettore di cui deve essere restituita la norma quadrata 2.</span><span class="sxs-lookup"><span data-stu-id="1b995-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="1b995-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b995-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b995-112">La norma 2 quadrata di `array` .</span><span class="sxs-lookup"><span data-stu-id="1b995-112">The squared 2-norm of `array`.</span></span>