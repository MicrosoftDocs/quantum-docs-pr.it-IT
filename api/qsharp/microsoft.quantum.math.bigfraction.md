---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definito dall'utente BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846913"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="8cd59-102">Tipo definito dall'utente BigFraction</span><span class="sxs-lookup"><span data-stu-id="8cd59-102">BigFraction user defined type</span></span>

<span data-ttu-id="8cd59-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8cd59-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8cd59-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8cd59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8cd59-105">Rappresenta un numero razionale del form `p/q` .</span><span class="sxs-lookup"><span data-stu-id="8cd59-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="8cd59-106">Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.</span><span class="sxs-lookup"><span data-stu-id="8cd59-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="8cd59-107">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="8cd59-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="8cd59-108">Numeratore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8cd59-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8cd59-109">Numeratore della frazione.</span><span class="sxs-lookup"><span data-stu-id="8cd59-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="8cd59-110">Denominatore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8cd59-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8cd59-111">Denominatore della frazione/</span><span class="sxs-lookup"><span data-stu-id="8cd59-111">Denominator of the fraction/</span></span>