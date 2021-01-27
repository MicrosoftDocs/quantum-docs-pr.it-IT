---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 4c0e7dd89b1beae9fb6a35ae5b8d16e09d355ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854713"
---
# <a name="trotterstep-function"></a>TrotterStep (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa un'unica fase temporale dell'evoluzione del sistema descritta in un oggetto `EvolutionGenerator` utilizzando una scomposizione Trotter-Suzuki.

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Descrizione completa del sistema da simulare.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordine di Trotter Integrator. Deve essere 1 o un numero pari.


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione unitaria che si avvicina a un singolo passaggio di tempo-evoluzione per la durata `trotterStepSize` .

## <a name="remarks"></a>Commenti

Per altre informazioni sulla decomposizione Trotter-Suzuki, vedere [composizione ordinata](/quantum/libraries/control-flow#time-ordered-composition)in un momento specifico.