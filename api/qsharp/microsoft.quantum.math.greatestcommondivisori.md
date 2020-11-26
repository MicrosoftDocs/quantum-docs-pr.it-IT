---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 2b6ba8a6d5ac78b69e6ee20160f3a3b1df61a879
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228475"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="440c3-102">GreatestCommonDivisorI (funzione)</span><span class="sxs-lookup"><span data-stu-id="440c3-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="440c3-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="440c3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="440c3-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="440c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="440c3-105">Calcola il massimo comun divisore di $a $ e $b $.</span><span class="sxs-lookup"><span data-stu-id="440c3-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="440c3-106">Il MCD è sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="440c3-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="440c3-107">Input</span><span class="sxs-lookup"><span data-stu-id="440c3-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="440c3-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="440c3-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="440c3-109">il primo numero di cui è in corso il calcolo del divisore più comune esteso</span><span class="sxs-lookup"><span data-stu-id="440c3-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="440c3-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="440c3-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="440c3-111">secondo numero di cui è in corso il calcolo del divisore maggiore comune esteso</span><span class="sxs-lookup"><span data-stu-id="440c3-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="440c3-112">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="440c3-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="440c3-113">Massimo comune divisore di $a $ e $b $</span><span class="sxs-lookup"><span data-stu-id="440c3-113">Greatest common divisor of $a$ and $b$</span></span>