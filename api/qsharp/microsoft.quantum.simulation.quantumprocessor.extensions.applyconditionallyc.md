---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Operazione ApplyConditionallyC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720186"
---
# <a name="applyconditionallyc-operation"></a>Operazione ApplyConditionallyC

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Input

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __non <Result> valido__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __non <Result> valido__ []




### <a name="onequalop--t--unit-ctl"></a>onEqualOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)




### <a name="equalarg--t"></a>equalArg: t




### <a name="onnonequalop--u--unit-ctl"></a>onNonEqualOp:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)




### <a name="nonequalarg--u"></a>nonEqualArg:' U





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U
