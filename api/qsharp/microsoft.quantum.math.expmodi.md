---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723362"
---
# <a name="expmodi-function"></a><span data-ttu-id="92d18-102">ExpModI (funzione)</span><span class="sxs-lookup"><span data-stu-id="92d18-102">ExpModI function</span></span>

<span data-ttu-id="92d18-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="92d18-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="92d18-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92d18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92d18-105">Restituisce un intero elevato a una determinata potenza, rispetto a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="92d18-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="92d18-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d18-106">Description</span></span>

<span data-ttu-id="92d18-107">È ora necessario indicare expBase per $x $, Power by $p $ e modulo per $N $.</span><span class="sxs-lookup"><span data-stu-id="92d18-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="92d18-108">La funzione restituisce $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="92d18-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="92d18-109">Si presuppone che $N $, $x $ siano positivi e che la potenza sia non negativa.</span><span class="sxs-lookup"><span data-stu-id="92d18-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="92d18-110">Input</span><span class="sxs-lookup"><span data-stu-id="92d18-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="92d18-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92d18-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="92d18-112">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92d18-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="92d18-113">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92d18-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="92d18-114">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92d18-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="92d18-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="92d18-115">Remarks</span></span>

<span data-ttu-id="92d18-116">Richiede tempo proporzionale al numero di bit in `power` , non a `power` se stesso.</span><span class="sxs-lookup"><span data-stu-id="92d18-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>