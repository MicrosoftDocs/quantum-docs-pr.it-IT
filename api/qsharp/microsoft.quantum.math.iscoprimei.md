---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851361"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="f7cac-102">IsCoprimeI (funzione)</span><span class="sxs-lookup"><span data-stu-id="f7cac-102">IsCoprimeI function</span></span>

<span data-ttu-id="f7cac-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f7cac-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f7cac-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7cac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7cac-105">Restituisce true se $a $ e $b $ sono co-prime e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f7cac-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f7cac-106">Input</span><span class="sxs-lookup"><span data-stu-id="f7cac-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f7cac-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7cac-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7cac-108">primo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="f7cac-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="f7cac-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7cac-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7cac-110">secondo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="f7cac-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="f7cac-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f7cac-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f7cac-112">True se $a $ e $b $ sono co-prime (ad esempio, il massimo comune divisore è 1) e false in caso contrario</span><span class="sxs-lookup"><span data-stu-id="f7cac-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>