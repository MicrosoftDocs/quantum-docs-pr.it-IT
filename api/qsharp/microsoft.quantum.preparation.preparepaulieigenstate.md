---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operazione PreparePauliEigenstate
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854347"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="b6c25-102">Operazione PreparePauliEigenstate</span><span class="sxs-lookup"><span data-stu-id="b6c25-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="b6c25-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b6c25-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b6c25-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6c25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6c25-105">Prepara un qubit nell'autostato positivo di un determinato operatore di Pauli.</span><span class="sxs-lookup"><span data-stu-id="b6c25-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="b6c25-106">Se viene specificato l'operatore di identità, il qubit viene preparato nello stato massimo misto.</span><span class="sxs-lookup"><span data-stu-id="b6c25-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b6c25-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6c25-107">Description</span></span>

<span data-ttu-id="b6c25-108">Se il qubit inizialmente si trovava nello stato $ \ket {0} $, questa operazione prepara il qubit in $ + $1 autostato di un determinato operatore Pauli oppure, per `PauliI` , nello stato massimo misto (vedere <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="b6c25-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="b6c25-109">Se il valore di qubit si trovava in uno stato diverso da $ \ket {0} $, questa operazione applica le seguenti attività di controllo: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ per `PauliZ` e <xref:microsoft.quantum.preparation.preparesinglequbitidentity> per `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="b6c25-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="b6c25-110">Input</span><span class="sxs-lookup"><span data-stu-id="b6c25-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="b6c25-111">base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b6c25-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b6c25-112">Un operatore Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="b6c25-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="b6c25-113">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b6c25-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b6c25-114">Qubit da preparare.</span><span class="sxs-lookup"><span data-stu-id="b6c25-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6c25-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6c25-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b6c25-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6c25-116">Example</span></span>

<span data-ttu-id="b6c25-117">Per preparare un qubit nello stato $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="b6c25-117">To prepare a qubit in the $\ket{+}$ state:</span></span>

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```