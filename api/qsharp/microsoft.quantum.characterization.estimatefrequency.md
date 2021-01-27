---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operazione EstimateFrequency
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851892"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="7957b-102">Operazione EstimateFrequency</span><span class="sxs-lookup"><span data-stu-id="7957b-102">EstimateFrequency operation</span></span>

<span data-ttu-id="7957b-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7957b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="7957b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7957b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7957b-105">Data una preparazione e una misurazione, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.</span><span class="sxs-lookup"><span data-stu-id="7957b-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="7957b-106">Input</span><span class="sxs-lookup"><span data-stu-id="7957b-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="7957b-107">preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7957b-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7957b-108">Un'operazione $P $ che prepara un dato stato $ \rho $ al relativo registro di input.</span><span class="sxs-lookup"><span data-stu-id="7957b-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="7957b-109">misurazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="7957b-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="7957b-110">Operazione $M $ che rappresenta la misura di interesse.</span><span class="sxs-lookup"><span data-stu-id="7957b-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7957b-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7957b-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7957b-112">Numero di qubits in cui ogni azione viene preparata e misurata.</span><span class="sxs-lookup"><span data-stu-id="7957b-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="7957b-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7957b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7957b-114">Il numero di volte in cui deve essere eseguita la misurazione per stimare la frequenza di interesse.</span><span class="sxs-lookup"><span data-stu-id="7957b-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="7957b-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7957b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7957b-116">Una stima $ \hat{p} $ della frequenza con cui $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ restituisce `Zero` , ottenuta utilizzando lo strumento di stima binomiale senza distorsione $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, dove $n \_ {\uparrow} $ indica il numero di `Zero` risultati osservati.</span><span class="sxs-lookup"><span data-stu-id="7957b-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="7957b-117">Questa operazione è particolarmente importante nei computer di destinazione che rispettano le limitazioni fisiche, in modo che non sia possibile misurare le probabilità.</span><span class="sxs-lookup"><span data-stu-id="7957b-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>