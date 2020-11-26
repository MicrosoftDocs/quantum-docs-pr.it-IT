---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228135"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="d2a8d-102">IsCoprimeL (funzione)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-102">IsCoprimeL function</span></span>

<span data-ttu-id="d2a8d-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d2a8d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2a8d-105">Restituisce true se $a $ e $b $ sono co-prime e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d2a8d-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d2a8d-106">Input</span><span class="sxs-lookup"><span data-stu-id="d2a8d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d2a8d-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d2a8d-108">primo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="d2a8d-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d2a8d-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d2a8d-110">secondo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="d2a8d-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="d2a8d-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d2a8d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d2a8d-112">True se $a $ e $b $ sono co-prime (ad esempio, il massimo comune divisore è 1) e false in caso contrario</span><span class="sxs-lookup"><span data-stu-id="d2a8d-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>