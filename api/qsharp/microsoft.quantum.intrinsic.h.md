---
uid: Microsoft.Quantum.Intrinsic.H
title: Operazione H
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6fa712b00a2745d8c0d8d3198cc9c5e6af3e2400
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818996"
---
# <a name="h-operation"></a><span data-ttu-id="2bbea-102">Operazione H</span><span class="sxs-lookup"><span data-stu-id="2bbea-102">H operation</span></span>

<span data-ttu-id="2bbea-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2bbea-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2bbea-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2bbea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2bbea-105">Applica la trasformazione Hadamard a un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="2bbea-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="2bbea-106">\begin{align} H \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2bbea-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="2bbea-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2bbea-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2bbea-108">Input</span><span class="sxs-lookup"><span data-stu-id="2bbea-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="2bbea-109">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2bbea-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2bbea-110">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="2bbea-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2bbea-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bbea-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

