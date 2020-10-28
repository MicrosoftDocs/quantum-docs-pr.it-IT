---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operazione EstimateFrequency
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715084"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="f5022-102">Operazione EstimateFrequency</span><span class="sxs-lookup"><span data-stu-id="f5022-102">EstimateFrequency operation</span></span>

<span data-ttu-id="f5022-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f5022-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f5022-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5022-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5022-105">Data una preparazione e una misurazione, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.</span><span class="sxs-lookup"><span data-stu-id="f5022-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="f5022-106">Input</span><span class="sxs-lookup"><span data-stu-id="f5022-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="f5022-107">preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f5022-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f5022-108">Un'operazione $P $ che prepara un dato stato $ \rho $ al relativo registro di input.</span><span class="sxs-lookup"><span data-stu-id="f5022-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="f5022-109">misurazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="f5022-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="f5022-110">Operazione $M $ che rappresenta la misura di interesse.</span><span class="sxs-lookup"><span data-stu-id="f5022-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="f5022-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5022-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5022-112">Numero di qubits in cui ogni azione viene preparata e misurata.</span><span class="sxs-lookup"><span data-stu-id="f5022-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f5022-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5022-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5022-114">Il numero di volte in cui deve essere eseguita la misurazione per stimare la frequenza di interesse.</span><span class="sxs-lookup"><span data-stu-id="f5022-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="f5022-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5022-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5022-116">Una stima $ \hat{p} $ della frequenza con cui $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ restituisce `Zero` , ottenuta utilizzando lo strumento di stima binomiale senza distorsione $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, dove $n \_ {\uparrow} $ indica il numero di `Zero` risultati osservati.</span><span class="sxs-lookup"><span data-stu-id="f5022-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="f5022-117">Questa operazione è particolarmente importante nei computer di destinazione che rispettano le limitazioni fisiche, in modo che non sia possibile misurare le probabilità.</span><span class="sxs-lookup"><span data-stu-id="f5022-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>