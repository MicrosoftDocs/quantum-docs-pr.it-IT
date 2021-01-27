---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operazione EstimateFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839922"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="42132-102">Operazione EstimateFrequencyA</span><span class="sxs-lookup"><span data-stu-id="42132-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="42132-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="42132-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="42132-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42132-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42132-105">Data una preparazione che è adjointable e la misura, stima la frequenza con cui la misurazione ha esito positivo (restituisce `Zero` ) eseguendo un determinato numero di prove.</span><span class="sxs-lookup"><span data-stu-id="42132-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="42132-106">Input</span><span class="sxs-lookup"><span data-stu-id="42132-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="42132-107">preparazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="42132-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="42132-108">Un'operazione adjointable $P $ che prepara un dato stato $ \rho $ al relativo registro di input.</span><span class="sxs-lookup"><span data-stu-id="42132-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="42132-109">misurazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="42132-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="42132-110">Operazione $M $ che rappresenta la misura di interesse.</span><span class="sxs-lookup"><span data-stu-id="42132-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="42132-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="42132-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="42132-112">Numero di qubits in cui ogni azione viene preparata e misurata.</span><span class="sxs-lookup"><span data-stu-id="42132-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="42132-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="42132-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="42132-114">Il numero di volte in cui deve essere eseguita la misurazione per stimare la frequenza di interesse.</span><span class="sxs-lookup"><span data-stu-id="42132-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="42132-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="42132-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="42132-116">Una stima $ \hat{p} $ della frequenza con cui $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ restituisce `Zero` , ottenuta utilizzando lo strumento di stima binomiale senza distorsione $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, dove $n \_ {\uparrow} $ indica il numero di `Zero` risultati osservati.</span><span class="sxs-lookup"><span data-stu-id="42132-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="42132-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="42132-117">Remarks</span></span>

<span data-ttu-id="42132-118">Per le operazioni adjointable, è possibile ipotizzare alcuni presupposti, ad esempio la chiamata dell'operazione, per preparare il qubits esattamente allo stesso stato, che consente ai computer di destinazione di apportare alcune ottimizzazioni delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="42132-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>