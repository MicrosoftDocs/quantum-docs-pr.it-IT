---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723359"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="e8292-102">IsCoprimeI (funzione)</span><span class="sxs-lookup"><span data-stu-id="e8292-102">IsCoprimeI function</span></span>

<span data-ttu-id="e8292-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e8292-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e8292-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8292-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8292-105">Restituisce true se $a $ e $b $ sono co-prime e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="e8292-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="e8292-106">Input</span><span class="sxs-lookup"><span data-stu-id="e8292-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e8292-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8292-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8292-108">primo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="e8292-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="e8292-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8292-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8292-110">secondo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="e8292-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="e8292-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8292-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e8292-112">True se $a $ e $b $ sono co-prime (ad esempio, il massimo comune divisore è 1) e false in caso contrario</span><span class="sxs-lookup"><span data-stu-id="e8292-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>