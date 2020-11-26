---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operazione MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216116"
---
# <a name="measureidentity-operation"></a>Operazione MeasureIdentity

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misura l'operatore di identità in un registro di qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Input

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Valore del risultato `Zero` .

## <a name="remarks"></a>Commenti

Poiché $ \boldone $ ha solo autovalore $1 $ e non ha un autovalore negativo, questa operazione restituisce sempre `Zero` , corrispondente a autovalore $ + 1 = (-1) ^ 0 $, e non provoca un collasso dello stato di `register` .

Da solo, questa operazione non è utile, ma è utile nel contesto della tomografia dei processi, poiché fornisce informazioni sulla conservazione delle tracce di un processo quantum.
In particolare, un computer di destinazione con misurazione con perdita di dati deve sostituire questa operazione con una misurazione effettiva di $ \boldone $.