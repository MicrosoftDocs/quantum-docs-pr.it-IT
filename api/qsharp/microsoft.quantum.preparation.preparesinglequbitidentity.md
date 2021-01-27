---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operazione PrepareSingleQubitIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856859"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="783b5-102">Operazione PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="783b5-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="783b5-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="783b5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="783b5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="783b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="783b5-105">Prepara un qubit nello stato massimo misto.</span><span class="sxs-lookup"><span data-stu-id="783b5-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="783b5-106">Prepara il qubit specificato nello stato $ \boldone/$2 applicando il canale depolarizzato $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ Sum_ {\mu \In \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ where $ \sigma \_ i $ is the $i $ th operatore Pauli e Where $ \rho $ è un operatore di densità che rappresenta uno stato misto.</span><span class="sxs-lookup"><span data-stu-id="783b5-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="783b5-107">Input</span><span class="sxs-lookup"><span data-stu-id="783b5-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="783b5-108">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="783b5-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="783b5-109">Un qubit il cui stato deve essere depolarizzato nel modo descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="783b5-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="783b5-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="783b5-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="783b5-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="783b5-111">Remarks</span></span>

<span data-ttu-id="783b5-112">Lo stato misto $ \boldone/$2 che descrive il risultato dell'applicazione di questa operazione a uno stato descrive in modo implicito un valore previsto rispetto a scelte casuali eseguite in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="783b5-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="783b5-113">Pertanto, per ogni singola applicazione, questa operazione esegue il mapping degli Stati puri agli Stati puri, ma funziona come descritto in expecting.</span><span class="sxs-lookup"><span data-stu-id="783b5-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="783b5-114">In particolare, questa operazione può essere utilizzata nella tomografia del processo per misurare i componenti *non unitari* di un canale.</span><span class="sxs-lookup"><span data-stu-id="783b5-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>