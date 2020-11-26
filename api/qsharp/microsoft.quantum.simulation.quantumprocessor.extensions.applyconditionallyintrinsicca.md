---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Operazione ApplyConditionallyIntrinsicCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 2dd7a9b6e281c62470defa64685dc58872694468
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230192"
---
# <a name="applyconditionallyintrinsicca-operation"></a>Operazione ApplyConditionallyIntrinsicCA

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __non <Result> valido__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __non <Result> valido__[]




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onEqualOp: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) è ADJ + CTL




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onNonEqualOp: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) è ADJ + CTL





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

