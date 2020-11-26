---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operazione ApplyObliviousAmplitudeAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191517"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>Operazione ApplyObliviousAmplitudeAmplification

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplificazione dell'ampiezza ignara specificando riflessi parziali.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="phases--reflectionphases"></a>fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fasi di riflessioni parziali


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operatore di Reflection sullo stato di avvio del registro ausiliario


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operatore di Reflection sullo stato di destinazione del registro ausiliario


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O $ di tipo `ObliviousOracle` che agisce congiuntamente sui registri ausiliari e di sistema.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro ausiliario


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di sistema



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Osservazioni

Dato un particolare stato di avvio ausiliario $ \ket{\Text{Start}} \_ a $, un particolare stato di destinazione ausiliario $ \ket{\Text{target}} \_ a $ e qualsiasi stato del sistema $ \ket{\psi} \_ s $, si supponga che \begin{align} O\ket {\ text {Start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\Text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{target} ^ \perp} a\cdots \_ \end{align} per alcune unità $U $.
Con una sequenza di riflessioni sugli stati di inizio e di destinazione nel registro ausiliario Interleaved dalle applicazioni di `signalOracle` e del relativo contiguo, è possibile che venga modificata la probabilità di applicare U.

Nella maggior parte dei casi, `auxiliaryRegister` viene inizializzato nello stato $ \ket{\Text{Start}} \_ a $.

## <a name="references"></a>Riferimenti

Vedere

- [ *D.W. Berry, am Childs, r. Cleve, r. Kothari, R.D. somma*](https://arxiv.org/abs/1312.1414) per la versione standard.
  Vedere
- [ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) per una generalizzazione per riflessi parziali.