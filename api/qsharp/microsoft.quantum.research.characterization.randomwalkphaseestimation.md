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
# <a name="randomwalkphaseestimation-operation"></a>Operazione RandomWalkPhaseEstimation

Spazio dei nomi: [Microsoft. Quantum. Research. characteration](xref:Microsoft.Quantum.Research.Characterization)

Pacchetto: [Microsoft. Quantum. Research. caratterizzazione](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)


Esegue la stima della fase iterativa usando un percorso casuale per approssimare l'inferenza Bayes sui risultati di misurazione classici da un determinato Oracle e autostato.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Input

### <a name="initialmean--double"></a>initialMean: [Double](xref:microsoft.quantum.lang-ref.double)

Media della distribuzione precedente normale iniziale su $ \Phi $.


### <a name="initialstddev--double"></a>initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)

Deviazione standard della distribuzione precedente normale iniziale su $ \Phi $.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da accettare nella stima posteriore finale.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero totale di misure che possono essere eseguite prima che l'operazione venga considerata non riuscita.


### <a name="unwind--int"></a>rimozione: [int](xref:microsoft.quantum.lang-ref.int)

Numero di risultati da dimenticare quando le verifiche della coerenza hanno esito negativo.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operazione che rappresenta un $U unitario $ tale che $U (t) \ket{\Phi} = e ^ {i t \Phi}\ket{\Phi} $ per autostati $ \ket{\Phi} $ con la fase sconosciuta $ \Phi \in \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro su cui $U $ agisce.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

La stima finale $ \hat{\Phi} \mathrel{: =} \expect [\Phi] $, dove l'aspettativa è sul posteriore, dato tutti i dati accettati.

## <a name="remarks"></a>Commenti

### <a name="iterative-phase-estimation-and-eigenstates"></a>Valutazione della fase iterativa e autostati

In generale, il registro `eigenstate` di input non deve essere un autostato $ \ket{\Phi} $ di $U $, ma può essere una superposizione su autostati. Si supponga che lo stato di input sia fornito da \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\Phi \_ j}, \end{align} dove $ \{ \Alpha \_ j \} $ sono coefficienti complessi in modo tale che $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 e Where $U \ket{\Phi \_ j} = \Phi \_ j\ket {\ Phi \_ j} $.

Quindi, l'esecuzione della stima della fase iterativa convergerà a un singolo autostato, come descritto nella [Guida di sviluppo](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Progettazione dell'esperimento

I tempi di misurazione $t $ e gli angoli inversione $ \theta $ passati a `oracle` vengono scelti in base a *Particle ipotesi euristica*, \Begin{align} \theta \sim \Pr (\Phi), \quad t \approx \frac {1} {\variance{\Phi}}.
\end{align} questa euristica è ottimale per ridurre la varianza posteriore prevista nella stima della fase iterativa secondo il presupposto di un normale priore.

### <a name="optimality"></a>Validità

Questa operazione si avvicina allo strumento di stima ottimale per la fase $ \Phi $, come valutato con la perdita quadratica $L (\Phi, \hat{\Phi}) \mathrel{: =} (\Phi-\hat{\Phi}) ^ 2 $.

Per ulteriori informazioni sulle statistiche relative alla stima della fase iterativa, vedere la [stima della fase Bayes](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .

## <a name="references"></a>Riferimenti

- Ferriie *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe e granata 2018 *(in preparazione)*.