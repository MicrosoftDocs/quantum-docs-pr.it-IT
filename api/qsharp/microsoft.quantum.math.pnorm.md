---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847661"
---
# <a name="pnorm-function"></a><span data-ttu-id="0d839-102">PNorm (funzione)</span><span class="sxs-lookup"><span data-stu-id="0d839-102">PNorm function</span></span>

<span data-ttu-id="0d839-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0d839-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0d839-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d839-105">Restituisce la `L(p)` norma di un vettore di `Double` s.</span><span class="sxs-lookup"><span data-stu-id="0d839-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="0d839-106">Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce l'$p $-norm $ \| x \| \_ p = (\ Sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="0d839-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="0d839-107">Input</span><span class="sxs-lookup"><span data-stu-id="0d839-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="0d839-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d839-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d839-109">L'esponente $p $ nella $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="0d839-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="0d839-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0d839-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="0d839-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d839-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d839-112">Il $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="0d839-112">The $p$-norm $\|x\|_p$.</span></span>