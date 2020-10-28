---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operazione R1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720918"
---
# <a name="r1-operation"></a><span data-ttu-id="07623-102">Operazione R1</span><span class="sxs-lookup"><span data-stu-id="07623-102">R1 operation</span></span>

<span data-ttu-id="07623-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="07623-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="07623-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07623-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07623-105">Applica una rotazione sullo {1} stato di $ \ket $ da un angolo specificato.</span><span class="sxs-lookup"><span data-stu-id="07623-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="07623-106">\begin{align} R_1 (\theta) \mathrel{: =} \operatorname{diag} (1, e ^ {i\theta}).</span><span class="sxs-lookup"><span data-stu-id="07623-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="07623-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="07623-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="07623-108">Input</span><span class="sxs-lookup"><span data-stu-id="07623-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="07623-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07623-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07623-110">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="07623-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="07623-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07623-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07623-112">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="07623-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07623-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07623-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07623-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="07623-114">Remarks</span></span>

<span data-ttu-id="07623-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="07623-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```