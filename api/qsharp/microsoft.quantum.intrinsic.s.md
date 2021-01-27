---
uid: Microsoft.Quantum.Intrinsic.S
title: Operazione S
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817523"
---
# <a name="s-operation"></a><span data-ttu-id="4e5af-102">Operazione S</span><span class="sxs-lookup"><span data-stu-id="4e5af-102">S operation</span></span>

<span data-ttu-id="4e5af-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4e5af-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4e5af-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4e5af-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4e5af-105">Applica il controllo S a un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="4e5af-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4e5af-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e5af-106">Description</span></span>

<span data-ttu-id="4e5af-107">Questa operazione può essere simulata dalla matrice unitaria \begin{align} S \mathrel{: =} \begin{Bmatrix} 1 & 0 \\ \\ 0 & i \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4e5af-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="4e5af-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4e5af-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="4e5af-109">Input</span><span class="sxs-lookup"><span data-stu-id="4e5af-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="4e5af-110">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4e5af-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4e5af-111">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="4e5af-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e5af-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e5af-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

