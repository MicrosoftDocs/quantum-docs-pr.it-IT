---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725350"
---
# <a name="trotterstep-function"></a>TrotterStep (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


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



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione unitaria che si avvicina a un singolo passaggio di tempo-evoluzione per la durata `trotterStepSize` .

## <a name="remarks"></a>Commenti

Per altre informazioni sulla decomposizione Trotter-Suzuki, vedere [composizione ordinata](/quantum/libraries/control-flow#time-ordered-composition)in un momento specifico.