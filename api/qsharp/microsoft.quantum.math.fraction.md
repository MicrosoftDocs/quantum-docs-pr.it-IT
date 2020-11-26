---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definito dall'utente
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210676"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="ea5d2-102">Tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="ea5d2-102">Fraction user defined type</span></span>

<span data-ttu-id="ea5d2-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ea5d2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ea5d2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea5d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea5d2-105">Rappresenta un numero razionale del form `p/q` .</span><span class="sxs-lookup"><span data-stu-id="ea5d2-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="ea5d2-106">Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.</span><span class="sxs-lookup"><span data-stu-id="ea5d2-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="ea5d2-107">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="ea5d2-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ea5d2-108">Numeratore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea5d2-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea5d2-109">Numeratore della frazione.</span><span class="sxs-lookup"><span data-stu-id="ea5d2-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="ea5d2-110">Denominatore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea5d2-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea5d2-111">Denominatore della frazione/</span><span class="sxs-lookup"><span data-stu-id="ea5d2-111">Denominator of the fraction/</span></span>