---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operazione RandomWalkPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846008"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="4d8c3-102">Operazione RandomWalkPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="4d8c3-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="4d8c3-103">Spazio dei nomi: [Microsoft. Quantum. Research. characteration](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="4d8c3-104">Pacchetto: [Microsoft. Quantum. Research. caratterizzazione](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="4d8c3-105">Esegue la stima della fase iterativa usando un percorso casuale per approssimare l'inferenza Bayes sui risultati di misurazione classici da un determinato Oracle e autostato.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="4d8c3-106">Input</span><span class="sxs-lookup"><span data-stu-id="4d8c3-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="4d8c3-107">initialMean: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d8c3-108">Media della distribuzione precedente normale iniziale su $ \Phi $.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="4d8c3-109">initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d8c3-110">Deviazione standard della distribuzione precedente normale iniziale su $ \Phi $.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4d8c3-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d8c3-112">Numero di misurazioni da accettare nella stima posteriore finale.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="4d8c3-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d8c3-114">Numero totale di misure che possono essere eseguite prima che l'operazione venga considerata non riuscita.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="4d8c3-115">rimozione: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d8c3-116">Numero di risultati da dimenticare quando le verifiche della coerenza hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="4d8c3-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="4d8c3-118">Operazione che rappresenta un $U unitario $ tale che $U (t) \ket{\Phi} = e ^ {i t \Phi}\ket{\Phi} $ per autostati $ \ket{\Phi} $ con la fase sconosciuta $ \Phi \in \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="4d8c3-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d8c3-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d8c3-120">Un registro su cui $U $ agisce.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="4d8c3-121">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d8c3-122">La stima finale $ \hat{\Phi} \mathrel{: =} \expect [\Phi] $, dove l'aspettativa è sul posteriore, dato tutti i dati accettati.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d8c3-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="4d8c3-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="4d8c3-124">Valutazione della fase iterativa e autostati</span><span class="sxs-lookup"><span data-stu-id="4d8c3-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="4d8c3-125">In generale, il registro `eigenstate` di input non deve essere un autostato $ \ket{\Phi} $ di $U $, ma può essere una superposizione su autostati.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="4d8c3-126">Si supponga che lo stato di input sia fornito da \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\Phi \_ j}, \end{align} dove $ \{ \Alpha \_ j \} $ sono coefficienti complessi in modo tale che $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 e Where $U \ket{\Phi \_ j} = \Phi \_ j\ket {\ Phi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="4d8c3-127">Quindi, l'esecuzione della stima della fase iterativa convergerà a un singolo autostato, come descritto nella [Guida di sviluppo](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="4d8c3-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="4d8c3-128">Progettazione dell'esperimento</span><span class="sxs-lookup"><span data-stu-id="4d8c3-128">Experiment Design</span></span>

<span data-ttu-id="4d8c3-129">I tempi di misurazione $t $ e gli angoli inversione $ \theta $ passati a `oracle` vengono scelti in base a *Particle ipotesi euristica*, \Begin{align} \theta \sim \Pr (\Phi), \quad t \approx \frac {1} {\variance{\Phi}}.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="4d8c3-130">\end{align} questa euristica è ottimale per ridurre la varianza posteriore prevista nella stima della fase iterativa secondo il presupposto di un normale priore.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="4d8c3-131">Validità</span><span class="sxs-lookup"><span data-stu-id="4d8c3-131">Optimality</span></span>

<span data-ttu-id="4d8c3-132">Questa operazione si avvicina allo strumento di stima ottimale per la fase $ \Phi $, come valutato con la perdita quadratica $L (\Phi, \hat{\Phi}) \mathrel{: =} (\Phi-\hat{\Phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="4d8c3-133">Per ulteriori informazioni sulle statistiche relative alla stima della fase iterativa, vedere la [stima della fase Bayes](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="4d8c3-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="4d8c3-134">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4d8c3-134">References</span></span>

- <span data-ttu-id="4d8c3-135">Ferriie *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="4d8c3-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="4d8c3-136">Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="4d8c3-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="4d8c3-137">Wiebe e granata 2018 *(in preparazione)*.</span><span class="sxs-lookup"><span data-stu-id="4d8c3-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>