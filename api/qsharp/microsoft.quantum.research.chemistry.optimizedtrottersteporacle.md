---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 04b1ea457277e0681596cb564fae3782a2d09db9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229818"
---
# <a name="optimizedtrottersteporacle-function"></a>OptimizedTrotterStepOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Restituisce l'operazione di passaggio Trotter ottimizzata e i parametri necessari per eseguirlo.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Input

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltoniana descritta dal `JordanWignerEncodingData` formato.


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Dimensioni del passaggio di Trotter Integrator.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordine di Trotter Integrator.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unit](xref:microsoft.quantum.lang-ref.unit)  is ADJ + CTL))

Tupla in cui: `Int` è il numero di qubits allocato, `Double` è `1.0/trotterStepSize` e l'operazione è il passaggio Trotter.