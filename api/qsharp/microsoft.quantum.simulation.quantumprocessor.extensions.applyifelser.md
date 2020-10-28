---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: Operazione ApplyIfElseR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724773"
---
# <a name="applyifelser-operation"></a>Operazione ApplyIfElseR

Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacchetto [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a>Input

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __non <Result> valido__




### <a name="onresultzeroop--t--unit"></a>onResultZeroOp:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="zeroarg--t"></a>zeroArg: t




### <a name="onresultoneop--u--unit"></a>onResultOneOp:' U = [unità](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="onearg--u"></a>oneArg:' U





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U

