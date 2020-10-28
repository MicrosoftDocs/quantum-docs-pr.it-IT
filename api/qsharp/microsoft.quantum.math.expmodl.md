---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723726"
---
# <a name="expmodl-function"></a><span data-ttu-id="20982-102">ExpModL (funzione)</span><span class="sxs-lookup"><span data-stu-id="20982-102">ExpModL function</span></span>

<span data-ttu-id="20982-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="20982-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="20982-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20982-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20982-105">Restituisce un intero elevato a una determinata potenza, rispetto a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="20982-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="20982-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20982-106">Description</span></span>

<span data-ttu-id="20982-107">È ora necessario indicare expBase per $x $, Power by $p $ e modulo per $N $.</span><span class="sxs-lookup"><span data-stu-id="20982-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="20982-108">La funzione restituisce $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="20982-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="20982-109">Si presuppone che $N $, $x $ siano positivi e che la potenza sia non negativa.</span><span class="sxs-lookup"><span data-stu-id="20982-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="20982-110">Input</span><span class="sxs-lookup"><span data-stu-id="20982-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="20982-111">expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20982-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="20982-112">Potenza: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20982-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="20982-113">modulo: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20982-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="20982-114">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20982-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="20982-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="20982-115">Remarks</span></span>

<span data-ttu-id="20982-116">Richiede tempo proporzionale al numero di bit in `power` , non a `power` se stesso.</span><span class="sxs-lookup"><span data-stu-id="20982-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>