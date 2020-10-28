---
uid: Microsoft.Quantum.Intrinsic.R
title: Operazione R
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720930"
---
# <a name="r-operation"></a><span data-ttu-id="7c45e-102">Operazione R</span><span class="sxs-lookup"><span data-stu-id="7c45e-102">R operation</span></span>

<span data-ttu-id="7c45e-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7c45e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7c45e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c45e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c45e-105">Applica una rotazione sull'asse di Pauli specificato.</span><span class="sxs-lookup"><span data-stu-id="7c45e-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="7c45e-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta sigma_ {\mu}/2}, \end{align} dove $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="7c45e-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7c45e-107">Input</span><span class="sxs-lookup"><span data-stu-id="7c45e-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7c45e-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7c45e-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7c45e-109">L'operatore Pauli ($ \mu $) deve essere exponentiated per formare la rotazione.</span><span class="sxs-lookup"><span data-stu-id="7c45e-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="7c45e-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c45e-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c45e-111">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="7c45e-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7c45e-112">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c45e-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c45e-113">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="7c45e-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c45e-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c45e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c45e-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="7c45e-115">Remarks</span></span>

<span data-ttu-id="7c45e-116">Quando viene chiamato con `pauli = PauliI` , questa operazione applica una *fase globale* .</span><span class="sxs-lookup"><span data-stu-id="7c45e-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="7c45e-117">Questa fase può essere significativa quando viene usata con il `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="7c45e-117">This phase can be significant when used with the `Controlled` functor.</span></span>