---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Operazione ApplyConditionallyCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230243"
---
# <a name="applyconditionallyca-operation"></a>Operazione ApplyConditionallyCA

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __non <Result> valido__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __non <Result> valido__[]




### <a name="onequalop--t--unit--is-adj--ctl"></a>onEqualOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL




### <a name="equalarg--t"></a>equalArg: t




### <a name="onnonequalop--u--unit--is-adj--ctl"></a>onNonEqualOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL




### <a name="nonequalarg--u"></a>nonEqualArg:' U





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U

