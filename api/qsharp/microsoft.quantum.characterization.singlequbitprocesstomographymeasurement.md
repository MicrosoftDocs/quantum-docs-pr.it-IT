---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operazione SingleQubitProcessTomographyMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714927"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="fb224-102">Operazione SingleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="fb224-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="fb224-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fb224-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="fb224-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb224-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb224-105">Esegue una misurazione della tomografia del processo qubit singolo in base a Pauli, dato un canale specifico di interesse.</span><span class="sxs-lookup"><span data-stu-id="fb224-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="fb224-106">Input</span><span class="sxs-lookup"><span data-stu-id="fb224-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="fb224-107">preparazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="fb224-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="fb224-108">L'elemento di base di Pauli $P $ in cui deve essere preparato un qubit.</span><span class="sxs-lookup"><span data-stu-id="fb224-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="fb224-109">misurazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="fb224-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="fb224-110">L'elemento di base di Pauli $Q $ in cui è necessario misurare un qubit.</span><span class="sxs-lookup"><span data-stu-id="fb224-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="fb224-111">canale: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="fb224-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fb224-112">Un singolo canale qubit $ \Lambda $ il cui comportamento viene stimato con la tomografia del processo.</span><span class="sxs-lookup"><span data-stu-id="fb224-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="fb224-113">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="fb224-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="fb224-114">Risultato `Zero` con probabilità $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="fb224-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="fb224-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="fb224-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="fb224-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="fb224-116">Remarks</span></span>

<span data-ttu-id="fb224-117">La distribuzione dei risultati restituiti da questa operazione è un caso speciale di tomografia a due qubit di stato.</span><span class="sxs-lookup"><span data-stu-id="fb224-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="fb224-118">Let $ \rho = J (\Lambda)/$2 è lo stato Choi-Jamiłkowski per $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="fb224-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="fb224-119">Quindi, la distribuzione precedente è identica a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ where $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 è la misura effettiva corrispondente a $P $ e $Q $.</span><span class="sxs-lookup"><span data-stu-id="fb224-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>