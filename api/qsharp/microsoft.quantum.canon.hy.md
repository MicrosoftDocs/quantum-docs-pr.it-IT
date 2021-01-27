---
uid: Microsoft.Quantum.Canon.HY
title: Operazione HY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840451"
---
# <a name="hy-operation"></a><span data-ttu-id="c0e14-102">Operazione HY</span><span class="sxs-lookup"><span data-stu-id="c0e14-102">HY operation</span></span>

<span data-ttu-id="c0e14-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0e14-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0e14-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0e14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0e14-105">Applica l'analogico di base Y alla trasformazione Hadamard che scambia gli assi Z e Y.</span><span class="sxs-lookup"><span data-stu-id="c0e14-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="c0e14-106">La trasformazione Y Hadamard $H _Y = S H $ in un singolo qubit è:</span><span class="sxs-lookup"><span data-stu-id="c0e14-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="c0e14-107">\begin{align} H_Y \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="c0e14-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="c0e14-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c0e14-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c0e14-109">Input</span><span class="sxs-lookup"><span data-stu-id="c0e14-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="c0e14-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0e14-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0e14-111">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="c0e14-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0e14-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0e14-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c0e14-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0e14-113">See Also</span></span>

- [<span data-ttu-id="c0e14-114">Microsoft. Quantum. Intrinsic. H</span><span class="sxs-lookup"><span data-stu-id="c0e14-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)