---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Operazione RX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723502"
---
# <a name="rx-operation"></a><span data-ttu-id="a67ea-102">Operazione RX</span><span class="sxs-lookup"><span data-stu-id="a67ea-102">Rx operation</span></span>

<span data-ttu-id="a67ea-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a67ea-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a67ea-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a67ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a67ea-105">Applica una rotazione sull'asse di $x $ da un angolo specificato.</span><span class="sxs-lookup"><span data-stu-id="a67ea-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="a67ea-106">\begin{align} R_x (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_x/2} = \begin{Bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{Bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="a67ea-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="a67ea-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a67ea-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a67ea-108">Input</span><span class="sxs-lookup"><span data-stu-id="a67ea-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="a67ea-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a67ea-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a67ea-110">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="a67ea-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a67ea-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a67ea-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a67ea-112">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="a67ea-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a67ea-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a67ea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a67ea-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="a67ea-114">Remarks</span></span>

<span data-ttu-id="a67ea-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="a67ea-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```