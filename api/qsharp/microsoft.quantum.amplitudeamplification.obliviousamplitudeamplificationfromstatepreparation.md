---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721833"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation (funzione)

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Amplificazione dell'ampiezza ignara da parte di Oracle per riflessioni parziali.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="phases--reflectionphases"></a>fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fasi di riflessioni parziali


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle $A $ unitario che prepara lo stato di avvio ausiliario


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O $ di tipo `ObliviousOracle` che agisce congiuntamente sull'ausiliario e sul Registro di sistema


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indice per il registro del flag Single-qubit



## <a name="output--qubitqubit--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione che implementa l'amplificazione dell'ampiezza ignara basata su riflessi parziali.

## <a name="remarks"></a>Commenti

Questa operazione impone condizioni più restrittive sotto forma di Stati di avvio e di destinazione ausiliari rispetto a `AmpAmpObliviousByReflectionPhases` .
Si presuppone che $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {fa} $ prepara lo stato di avvio ausiliario $ \ket{\Text{Start}} \_ {fa} $ dalla base computazionale $ \ket {0} \_ f\ket {0} $.
Si presuppone che lo stato di destinazione sia contrassegnato da $ \ket {1} \_ f $.
Si presuppone che \begin{align} O\ket {\ text {Start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {Any}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} per alcuni Unity $U $.