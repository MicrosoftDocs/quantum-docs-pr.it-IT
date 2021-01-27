---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851336"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="696fc-102">IsCoprimeL (funzione)</span><span class="sxs-lookup"><span data-stu-id="696fc-102">IsCoprimeL function</span></span>

<span data-ttu-id="696fc-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="696fc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="696fc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="696fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="696fc-105">Restituisce true se $a $ e $b $ sono co-prime e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="696fc-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="696fc-106">Input</span><span class="sxs-lookup"><span data-stu-id="696fc-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="696fc-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="696fc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="696fc-108">primo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="696fc-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="696fc-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="696fc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="696fc-110">secondo numero di cui è in corso il test di co-primalità</span><span class="sxs-lookup"><span data-stu-id="696fc-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="696fc-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="696fc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="696fc-112">True se $a $ e $b $ sono co-prime (ad esempio, il massimo comune divisore è 1) e false in caso contrario</span><span class="sxs-lookup"><span data-stu-id="696fc-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>