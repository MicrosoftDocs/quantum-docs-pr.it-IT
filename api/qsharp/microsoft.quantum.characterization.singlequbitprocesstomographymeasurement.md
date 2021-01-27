---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operazione SingleQubitProcessTomographyMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839645"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="5c460-102">Operazione SingleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="5c460-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="5c460-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="5c460-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="5c460-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c460-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c460-105">Esegue una misurazione della tomografia del processo qubit singolo in base a Pauli, dato un canale specifico di interesse.</span><span class="sxs-lookup"><span data-stu-id="5c460-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="5c460-106">Input</span><span class="sxs-lookup"><span data-stu-id="5c460-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="5c460-107">preparazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="5c460-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="5c460-108">L'elemento di base di Pauli $P $ in cui deve essere preparato un qubit.</span><span class="sxs-lookup"><span data-stu-id="5c460-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="5c460-109">misurazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="5c460-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="5c460-110">L'elemento di base di Pauli $Q $ in cui è necessario misurare un qubit.</span><span class="sxs-lookup"><span data-stu-id="5c460-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="5c460-111">canale: [](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="5c460-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5c460-112">Un singolo canale qubit $ \Lambda $ il cui comportamento viene stimato con la tomografia del processo.</span><span class="sxs-lookup"><span data-stu-id="5c460-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5c460-113">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="5c460-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5c460-114">Risultato `Zero` con probabilità $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="5c460-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="5c460-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5c460-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="5c460-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="5c460-116">Remarks</span></span>

<span data-ttu-id="5c460-117">La distribuzione dei risultati restituiti da questa operazione è un caso speciale di tomografia a due qubit di stato.</span><span class="sxs-lookup"><span data-stu-id="5c460-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="5c460-118">Let $ \rho = J (\Lambda)/$2 è lo stato Choi-Jamiłkowski per $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="5c460-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="5c460-119">Quindi, la distribuzione precedente è identica a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ where $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 è la misura effettiva corrispondente a $P $ e $Q $.</span><span class="sxs-lookup"><span data-stu-id="5c460-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>