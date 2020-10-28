---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definito dall'utente BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723208"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="1e050-102">Tipo definito dall'utente BigFraction</span><span class="sxs-lookup"><span data-stu-id="1e050-102">BigFraction user defined type</span></span>

<span data-ttu-id="1e050-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1e050-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1e050-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e050-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e050-105">Rappresenta un numero razionale del form `p/q` .</span><span class="sxs-lookup"><span data-stu-id="1e050-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="1e050-106">Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.</span><span class="sxs-lookup"><span data-stu-id="1e050-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="1e050-107">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="1e050-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="1e050-108">Numeratore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1e050-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1e050-109">Numeratore della frazione.</span><span class="sxs-lookup"><span data-stu-id="1e050-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="1e050-110">Denominatore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1e050-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1e050-111">Denominatore della frazione/</span><span class="sxs-lookup"><span data-stu-id="1e050-111">Denominator of the fraction/</span></span>