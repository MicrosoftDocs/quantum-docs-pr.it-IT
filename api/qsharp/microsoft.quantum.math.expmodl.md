---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210748"
---
# <a name="expmodl-function"></a><span data-ttu-id="9f945-102">ExpModL (funzione)</span><span class="sxs-lookup"><span data-stu-id="9f945-102">ExpModL function</span></span>

<span data-ttu-id="9f945-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9f945-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9f945-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f945-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f945-105">Restituisce un intero elevato a una determinata potenza, rispetto a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="9f945-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="9f945-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f945-106">Description</span></span>

<span data-ttu-id="9f945-107">È ora necessario indicare expBase per $x $, Power by $p $ e modulo per $N $.</span><span class="sxs-lookup"><span data-stu-id="9f945-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="9f945-108">La funzione restituisce $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="9f945-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="9f945-109">Si presuppone che $N $, $x $ siano positivi e che la potenza sia non negativa.</span><span class="sxs-lookup"><span data-stu-id="9f945-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="9f945-110">Input</span><span class="sxs-lookup"><span data-stu-id="9f945-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="9f945-111">expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9f945-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="9f945-112">Potenza: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9f945-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="9f945-113">modulo: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9f945-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="9f945-114">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9f945-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="9f945-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="9f945-115">Remarks</span></span>

<span data-ttu-id="9f945-116">Richiede tempo proporzionale al numero di bit in `power` , non a `power` se stesso.</span><span class="sxs-lookup"><span data-stu-id="9f945-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>