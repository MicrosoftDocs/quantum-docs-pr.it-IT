---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725672"
---
# <a name="applyifzeroca-operation"></a>Operazione ApplyIfZeroCA

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto [](https://nuget.org/packages/)




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a>Input

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __non <Result> valido__




### <a name="onresultzeroop--t--unit-ctl--adj"></a>onResultZeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ




### <a name="zeroarg--t"></a>zeroArg: t





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

