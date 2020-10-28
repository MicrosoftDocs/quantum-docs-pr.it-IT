---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723642"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="b2a3b-102">GreatestCommonDivisorL (funzione)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="b2a3b-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b2a3b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2a3b-105">Calcola il massimo comun divisore di $a $ e $b $.</span><span class="sxs-lookup"><span data-stu-id="b2a3b-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="b2a3b-106">Il MCD è sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="b2a3b-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b2a3b-107">Input</span><span class="sxs-lookup"><span data-stu-id="b2a3b-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b2a3b-108">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2a3b-109">il primo numero di cui è in corso il calcolo del divisore più comune esteso</span><span class="sxs-lookup"><span data-stu-id="b2a3b-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b2a3b-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2a3b-111">secondo numero di cui è in corso il calcolo del divisore maggiore comune esteso</span><span class="sxs-lookup"><span data-stu-id="b2a3b-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b2a3b-112">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2a3b-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2a3b-113">Massimo comune divisore di $a $ e $b $</span><span class="sxs-lookup"><span data-stu-id="b2a3b-113">Greatest common divisor of $a$ and $b$</span></span>