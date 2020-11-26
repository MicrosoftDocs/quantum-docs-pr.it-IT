---
uid: Microsoft.Quantum.Intrinsic.R
title: Operazione R
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199030"
---
# <a name="r-operation"></a><span data-ttu-id="10851-102">Operazione R</span><span class="sxs-lookup"><span data-stu-id="10851-102">R operation</span></span>

<span data-ttu-id="10851-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="10851-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="10851-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="10851-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="10851-105">Applica una rotazione sull'asse di Pauli specificato.</span><span class="sxs-lookup"><span data-stu-id="10851-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="10851-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta sigma_ {\mu}/2}, \end{align} dove $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="10851-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="10851-107">Input</span><span class="sxs-lookup"><span data-stu-id="10851-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="10851-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="10851-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="10851-109">L'operatore Pauli ($ \mu $) deve essere exponentiated per formare la rotazione.</span><span class="sxs-lookup"><span data-stu-id="10851-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="10851-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10851-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="10851-111">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="10851-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="10851-112">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="10851-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="10851-113">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="10851-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10851-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10851-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="10851-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="10851-115">Remarks</span></span>

<span data-ttu-id="10851-116">Quando viene chiamato con `pauli = PauliI` , questa operazione applica una *fase globale*.</span><span class="sxs-lookup"><span data-stu-id="10851-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="10851-117">Questa fase può essere significativa quando viene usata con il `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="10851-117">This phase can be significant when used with the `Controlled` functor.</span></span>