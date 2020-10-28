---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definito dall'utente
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723656"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="8c2e6-102">Tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="8c2e6-102">Fraction user defined type</span></span>

<span data-ttu-id="8c2e6-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8c2e6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8c2e6-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c2e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c2e6-105">Rappresenta un numero razionale del form `p/q` .</span><span class="sxs-lookup"><span data-stu-id="8c2e6-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="8c2e6-106">Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.</span><span class="sxs-lookup"><span data-stu-id="8c2e6-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="8c2e6-107">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="8c2e6-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="8c2e6-108">Numeratore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c2e6-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c2e6-109">Numeratore della frazione.</span><span class="sxs-lookup"><span data-stu-id="8c2e6-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="8c2e6-110">Denominatore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c2e6-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c2e6-111">Denominatore della frazione/</span><span class="sxs-lookup"><span data-stu-id="8c2e6-111">Denominator of the fraction/</span></span>