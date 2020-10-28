---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Operazione RZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720867"
---
# <a name="rz-operation"></a><span data-ttu-id="be6c3-102">Operazione RZ</span><span class="sxs-lookup"><span data-stu-id="be6c3-102">Rz operation</span></span>

<span data-ttu-id="be6c3-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="be6c3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="be6c3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be6c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be6c3-105">Applica una rotazione sull'asse di $z $ da un angolo specificato.</span><span class="sxs-lookup"><span data-stu-id="be6c3-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="be6c3-106">\begin{align} R_z (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_z/2} = \begin{Bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="be6c3-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="be6c3-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="be6c3-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="be6c3-108">Input</span><span class="sxs-lookup"><span data-stu-id="be6c3-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="be6c3-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="be6c3-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="be6c3-110">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="be6c3-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="be6c3-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="be6c3-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="be6c3-112">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="be6c3-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be6c3-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be6c3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="be6c3-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="be6c3-114">Remarks</span></span>

<span data-ttu-id="be6c3-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="be6c3-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```