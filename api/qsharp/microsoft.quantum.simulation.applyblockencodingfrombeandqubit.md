---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: Operazione ApplyBlockEncodingFromBEandQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: 616ca9a78918199057e203a825cdcde7aeb75de2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852804"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a>Operazione ApplyBlockEncodingFromBEandQubit

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Conversione di ((LittleEndian, qubit []) => () è ADJ + CTL) in BlockEncoding

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="op--littleendianqubit--unit--is-adj--ctl"></a>op: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL




### <a name="auxiliary--qubit"></a>ausiliario: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="system--qubit"></a>sistema: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

