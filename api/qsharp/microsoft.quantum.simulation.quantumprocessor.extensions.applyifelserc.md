---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709467"
---
# <a name="applyifelserc-operation"></a>Operazione ApplyIfElseRC

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>Input

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __non <Result> valido__




### <a name="onresultzeroop--t--unit-ctl"></a>onResultZeroOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)




### <a name="zeroarg--t"></a>zeroArg: t




### <a name="onresultoneop--u--unit-ctl"></a>onResultOneOp:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)




### <a name="onearg--u"></a>oneArg:' U





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U

