---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856366"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="b305a-102">GreatestCommonDivisorL (funzione)</span><span class="sxs-lookup"><span data-stu-id="b305a-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="b305a-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b305a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b305a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b305a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b305a-105">Calcola il massimo comun divisore di $a $ e $b $.</span><span class="sxs-lookup"><span data-stu-id="b305a-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="b305a-106">Il MCD è sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="b305a-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b305a-107">Input</span><span class="sxs-lookup"><span data-stu-id="b305a-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b305a-108">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b305a-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b305a-109">il primo numero di cui è in corso il calcolo del divisore più comune esteso</span><span class="sxs-lookup"><span data-stu-id="b305a-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b305a-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b305a-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b305a-111">secondo numero di cui è in corso il calcolo del divisore maggiore comune esteso</span><span class="sxs-lookup"><span data-stu-id="b305a-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b305a-112">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b305a-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b305a-113">Massimo comune divisore di $a $ e $b $</span><span class="sxs-lookup"><span data-stu-id="b305a-113">Greatest common divisor of $a$ and $b$</span></span>