---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Operazione ApplyConditionallyIntrinsicCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 137168d7360842df18d1ed2893f7a1b2e9a548cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854211"
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




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onEqualOp: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) è ADJ + CTL




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onNonEqualOp: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) è ADJ + CTL





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

