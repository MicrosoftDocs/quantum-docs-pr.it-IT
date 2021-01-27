---
uid: Microsoft.Quantum.Intrinsic.R
title: Operazione R
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818724"
---
# <a name="r-operation"></a><span data-ttu-id="ea0d2-102">Operazione R</span><span class="sxs-lookup"><span data-stu-id="ea0d2-102">R operation</span></span>

<span data-ttu-id="ea0d2-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ea0d2-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ea0d2-105">Applica una rotazione sull'asse di Pauli specificato.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="ea0d2-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta sigma_ {\mu}/2}, \end{align} dove $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ea0d2-107">Input</span><span class="sxs-lookup"><span data-stu-id="ea0d2-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ea0d2-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ea0d2-109">L'operatore Pauli ($ \mu $) deve essere exponentiated per formare la rotazione.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ea0d2-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea0d2-111">Angolo per la rotazione del qubit.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ea0d2-112">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea0d2-113">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea0d2-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea0d2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea0d2-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea0d2-115">Remarks</span></span>

<span data-ttu-id="ea0d2-116">Quando viene chiamato con `pauli = PauliI` , questa operazione applica una *fase globale*.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="ea0d2-117">Questa fase può essere significativa quando viene usata con il `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="ea0d2-117">This phase can be significant when used with the `Controlled` functor.</span></span>