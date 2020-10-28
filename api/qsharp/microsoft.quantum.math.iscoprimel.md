---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722309"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="bf528-102">IsCoprimeL (funzione)</span><span class="sxs-lookup"><span data-stu-id="bf528-102">IsCoprimeL function</span></span>

<span data-ttu-id="bf528-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bf528-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bf528-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf528-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf528-105">Restituisce true se $a $ e $b $ sono co-prime e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="bf528-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="bf528-106">Input</span><span class="sxs-lookup"><span data-stu-id="bf528-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="bf528-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bf528-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bf528-108">primo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="bf528-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="bf528-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bf528-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bf528-110">secondo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="bf528-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="bf528-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf528-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf528-112">True se $a $ e $b $ sono co-prime (ad esempio, il massimo comune divisore è 1) e false in caso contrario</span><span class="sxs-lookup"><span data-stu-id="bf528-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>