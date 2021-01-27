---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operazione ry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818274"
---
# <a name="ry-operation"></a><span data-ttu-id="56de6-102">Operazione ry</span><span class="sxs-lookup"><span data-stu-id="56de6-102">Ry operation</span></span>

<span data-ttu-id="56de6-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="56de6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="56de6-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="56de6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="56de6-105">Applica una rotazione sull'asse di $y $ da un angolo specificato.</span><span class="sxs-lookup"><span data-stu-id="56de6-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="56de6-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{Bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{Bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="56de6-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="56de6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="56de6-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="56de6-108">Input</span><span class="sxs-lookup"><span data-stu-id="56de6-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="56de6-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="56de6-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="56de6-110">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="56de6-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="56de6-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56de6-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56de6-112">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="56de6-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56de6-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56de6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="56de6-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="56de6-114">Remarks</span></span>

<span data-ttu-id="56de6-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="56de6-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```