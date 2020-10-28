---
uid: Microsoft.Quantum.Intrinsic.T
title: Operazione T
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720855"
---
# <a name="t-operation"></a><span data-ttu-id="b3689-102">Operazione T</span><span class="sxs-lookup"><span data-stu-id="b3689-102">T operation</span></span>

<span data-ttu-id="b3689-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b3689-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b3689-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3689-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3689-105">Applica il controllo T a un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="b3689-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b3689-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3689-106">Description</span></span>

<span data-ttu-id="b3689-107">Questa operazione può essere simulata dalla matrice di unità \begin{align} T \mathrel{: =} \begin{Bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \Pi/4} \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="b3689-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="b3689-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b3689-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="b3689-109">Input</span><span class="sxs-lookup"><span data-stu-id="b3689-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="b3689-110">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b3689-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b3689-111">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="b3689-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b3689-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3689-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

